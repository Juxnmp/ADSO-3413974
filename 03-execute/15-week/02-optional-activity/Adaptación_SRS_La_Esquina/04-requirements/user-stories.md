# Casos de Uso

**Estado:** 🟢 Estable  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina  
**Fuente:** SRS Supermercado La Esquina

---

## CU01 — Registrar Venta

| Campo | Detalle |
|-------|---------|
| **Actor principal** | Cajero |
| **Precondiciones** | Sistema activo, cajero autenticado, productos registrados en el sistema |
| **Postcondiciones** | Venta registrada, inventario actualizado, factura generada |
| **Requerimientos relacionados** | RF05, RF06, RF07 |

### Flujo Normal

1. El cajero selecciona "Nueva venta"
2. Ingresa o escanea los productos
3. El sistema muestra precios y calcula el total automáticamente
4. El cajero confirma la venta
5. El sistema registra la venta y genera la factura automáticamente

### Flujos de Excepción

| Situación | Respuesta del sistema |
|-----------|----------------------|
| Producto inexistente | El sistema muestra un mensaje de error |
| Stock insuficiente | El sistema genera una alerta al cajero |

---

## CU02 — Gestionar Inventario

| Campo | Detalle |
|-------|---------|
| **Actor principal** | Administrador |
| **Precondiciones** | Administrador autenticado, sistema operativo |
| **Postcondiciones** | Inventario actualizado correctamente en la base de datos |
| **Requerimientos relacionados** | RF01, RF02, RF03, RF05 |

### Flujo Normal

1. El administrador accede al módulo "Inventario"
2. Consulta la lista de productos disponibles
3. Agrega, edita o elimina productos según la necesidad
4. Guarda los cambios
5. El sistema actualiza la base de datos

### Flujos de Excepción

| Situación | Respuesta del sistema |
|-----------|----------------------|
| Datos incompletos | El sistema no permite guardar; indica los campos faltantes |
| Producto duplicado | El sistema genera una alerta de duplicado |

---

## CU03 — Generar Reportes

| Campo | Detalle |
|-------|---------|
| **Actor principal** | Administrador |
| **Precondiciones** | Administrador autenticado, ventas registradas en el sistema |
| **Postcondiciones** | Reporte generado y disponible para consulta o descarga |
| **Requerimientos relacionados** | RF04, RF09 |

### Flujo Normal

1. El administrador entra al módulo "Reportes"
2. Selecciona el tipo de reporte (ventas o inventario)
3. Define el rango de fechas (diario, semanal, mensual)
4. El sistema genera el reporte consolidado
5. El administrador visualiza o descarga el reporte

### Flujos de Excepción

| Situación | Respuesta del sistema |
|-----------|----------------------|
| Sin datos en el período | El sistema muestra un mensaje informativo |
| Fechas inválidas | El sistema solicita la corrección del rango de fechas |

---

## Referencias

- [Requerimientos funcionales](./functional.md)
- [Entidades y reglas](../02-domain/entities-and-rules.md)
- [Matriz de trazabilidad](./traceability-matrix.md)
