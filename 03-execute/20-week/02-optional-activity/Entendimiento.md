# Entendimiento del Caso — Venta y Control de Tiquetes Aéreos 

## Entendimiento General del PRD

La aerolínea necesita un sistema para vender y controlar tiquetes aéreos de
principio a fin: desde que un pasajero hace una reserva, hasta que sube al
avión. En el camino hay que controlar asientos, equipaje y pagos, y al
final se necesita saber quiénes compraron tiquete pero nunca viajaron.

## ¿Qué problema resuelve?

Hoy la aerolínea necesita tener control sobre:

- Quién es el pasajero que compró el tiquete
- Para qué vuelo es (número + fecha)
- Qué asiento le corresponde en ese vuelo
- Si ya pagó o si el tiquete quedó pendiente de pago
- Qué equipaje registró
- Si finalmente abordó o no

El punto más importante: el sistema debe poder decir, para un vuelo dado,
qué pasajeros tenían tiquete pero **no abordaron** (no-show).

## Flujo Principal

El caso describe una única secuencia de trabajo para el agente:


1. Iniciar sesión
2. Registrar pasajero
3. Crear reserva
4. Emitir tiquete (a partir de la reserva)
5. Crear vuelo
6. Asignar asiento
7. Registrar pago       (opcional)
8. Registrar equipaje   (opcional)
9. Registrar embarque   (opcional)
10. Consultar reporte de no-show


## ¿Quién usa el sistema?

Solo hay un tipo de usuario en el MVP: el **agente de la aerolínea**. Este
mismo agente hace todo — vende, asigna, cobra, y consulta reportes — no hay
un rol distinto para supervisores ni acceso directo para pasajeros. El
sistema arranca con un agente administrador ya creado (seed).

Acciones que puede hacer el agente:

- Iniciar sesión
- Crear y listar pasajeros
- Crear y listar reservas
- Emitir tiquetes
- Crear vuelos
- Asignar asientos
- Registrar pagos y equipaje
- Registrar embarques
- Consultar el reporte de no-show

## Entidades del Sistema

| Entidad | Qué representa |
|---|---|
| Passenger | La persona que viaja |
| Reservation | El paso previo a tener un tiquete |
| Ticket | Lo que autoriza a viajar |
| Flight | Un vuelo en una fecha específica |
| Airport | Origen o destino de un vuelo |
| Aircraft | El avión que cubre el vuelo |
| Seat | Un asiento físico del avión |
| Seat Assignment | Qué pasajero tiene qué asiento en qué vuelo |
| Payment | El pago de un tiquete (si existe) |
| Baggage | Equipaje asociado al tiquete |
| Boarding | Evidencia de que el pasajero sí abordó |

## Reglas de Negocio que No se Pueden Pasar por Alto

**1. Un vuelo no se identifica solo por su número**

Se identifica por **número de vuelo + fecha de salida**, porque el mismo
número de vuelo se repite todos los días.

**2. El aeropuerto es una sola entidad con dos roles**

Un vuelo tiene un aeropuerto de origen y uno de destino, pero ambos salen
de la misma tabla `Airport`. No se crean dos tablas distintas para esto.

**3. Un asiento no existe sin su avión**

`Seat` depende de `Aircraft`; su identificador incluye el número de asiento
y la matrícula del avión.

**4. El mismo asiento se puede repetir entre vuelos distintos, pero no dentro del mismo vuelo**

Válido:

Vuelo A → asiento 12A → Juan
Vuelo B → asiento 12A → Pedro


No válido:

Vuelo A → asiento 12A → Juan
Vuelo A → asiento 12A → María


**5. El embarque es opcional, y de eso depende el reporte de no-show**

- Si hay registro de `Boarding` → el pasajero viajó.
- Si no hay registro → no-show.

Esta es la regla que hace posible el reporte que pide el PRD.

## Glosario de Términos

**PRD (Product Requirements Document)**
Documento de requisitos del producto. Es el documento base (`case-1.md`)
donde el negocio describe qué necesita el sistema: contexto, entidades,
requisitos funcionales y no funcionales, y criterios de aceptación.

**No-Show**
Pasajero que compró un tiquete pero no abordó el vuelo. Se identifica
porque tiene `Ticket` pero no tiene `Boarding` registrado para ese vuelo.

**MVP (Minimum Viable Product)**
Producto Mínimo Viable. Es la versión más pequeña del sistema que ya
resuelve el problema completo del negocio: un solo rol (agente), un flujo
de punta a punta (login → pasajero → reserva → tiquete → vuelo → asiento →
reporte no-show), sin funciones extra que no pidió el PRD.

**Docker Compose**
Herramienta que permite levantar varios servicios (backend, frontend, base
de datos) al mismo tiempo con un solo comando (`docker compose up`),
usando un archivo de configuración. Aquí se usa para que el sistema quede
arriba y navegable con un solo paso, con el agente administrador ya
sembrado.

**CRUD (Create, Read, Update, Delete)**
Las cuatro operaciones básicas sobre una entidad: crear, leer/consultar,
actualizar y eliminar. En el PRD no todas las entidades tienen las cuatro
(por ejemplo, no se pide "eliminar" tiquetes o vuelos); lo mínimo que se
pide para la mayoría es **crear** y **listar/consultar**.

### Glosario de Entidades

| Entidad | Significado |
|---|---|
| **Passenger** | Pasajero. Persona que viaja; se identifica por su documento. |
| **Reservation** | Reserva. Solicitud previa a que exista un tiquete; tiene fecha y estado. |
| **Ticket** | Tiquete. Documento que autoriza a viajar; se genera a partir de una reserva. |
| **Flight** | Vuelo. Se identifica por número de vuelo + fecha de salida (no solo por el número). |
| **Airport** | Aeropuerto. Una sola entidad que cumple doble rol en un vuelo: origen y destino. |
| **Aircraft** | Aeronave. El avión asignado a un vuelo, con su matrícula, modelo y capacidad. |
| **Seat** | Asiento. Asiento físico de una aeronave; no existe sin ella (entidad débil). |
| **Seat Assignment** | Asignación de asiento. Relaciona asiento + pasajero + vuelo; un asiento no se repite en el mismo vuelo. |
| **Payment** | Pago. Registro opcional del pago de un tiquete. |
| **Baggage** | Equipaje. Registro opcional (0 a N) de equipaje asociado a un tiquete. |
| **Boarding** | Embarque. Registro opcional de que el pasajero sí abordó; su ausencia define el no-show. |
