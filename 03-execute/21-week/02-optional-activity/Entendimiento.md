# Análisis Panel Aprendiz MockUp (Sistema de Gestión de Horarios)

El sistema busca apoyar la gestión de horarios del SENA, reuniendo en un solo lugar la información relacionada con la programación académica. De esta manera, los usuarios pueden consultar, crear, modificar y actualizar los horarios de una forma más fácil.

La idea principal es mejorar la organización y la comunicación entre los diferentes usuarios del sistema, permitiendo consultar rápidamente la información actualizada de las formaciones. El sistema no busca reemplazar las plataformas que ya utiliza el SENA, sino servir como un apoyo para estas.

---

## Rol: Aprendiz

Para entender cómo funciona el sistema, primero se debe revisar el rol del aprendiz, ya que es uno de los usuarios principales. Este rol permite identificar varias de las necesidades que el sistema busca solucionar.

### Alcance

El aprendiz cuenta con 4 pantallas:

25. Mi horario - semana
26. Notificaciones
27. Detalle de clase
28. Detalle de notificación

El aprendiz puede utilizar estas pantallas principalmente para consultar su horario de manera rápida y sencilla. También puede revisar las notificaciones para enterarse de los cambios que se hagan en sus formaciones.

**Todas las pantallas se adaptan a diferentes tamaños de pantalla.**

### Flujograma Principal

El proceso que sigue el aprendiz para consultar su horario es el siguiente:

1. Ingresar al sistema con sus credenciales.
2. Revisar las formaciones que tiene programadas.

   * Puede ver información de cada clase, como la competencia, el instructor, el ambiente, la ubicación, la fecha, la hora y una nota de la sesión.
3. Revisar las notificaciones desde el apartado correspondiente o desde la barra superior para conocer los cambios realizados.

En general, el proceso es sencillo y permite que el aprendiz encuentre rápidamente la información que necesita.

### Entendimiento de UI / UX

1. **Qué entiende rápido:** El aprendiz puede encontrar fácilmente su horario, las notificaciones y la información adicional de cada clase.
2. **Qué no queda claro:** No se identifica fácilmente cuál es la próxima formación que tiene ni cuáles notificaciones todavía no ha revisado.
3. **Qué botones o textos sobran:** La información está presentada de manera clara y no se observan botones o textos que sean innecesarios.
4. **Qué información falta:** Sería útil mostrar el día y la fecha actual, además de información sobre quién es el líder de la ficha.
5. **Qué error podría cometer:** El aprendiz podría pensar que ya revisó una notificación cuando en realidad todavía no la ha visto.
6. **Qué consecuencia tendría:** Podría pasar por alto un cambio importante en su horario, como una cancelación o un cambio de fecha.

### Comparación con SIGA

El MockUp tiene un objetivo parecido al de SIGA, ya que permite al aprendiz consultar información relacionada con su proceso académico, especialmente su horario y sus novedades.

La diferencia principal es que el MockUp reúne la información de una manera más sencilla y visual, haciendo que sea más fácil consultar las clases.

Sin embargo, todavía se podrían mejorar algunos aspectos, como mostrar claramente cuál es la próxima formación, diferenciar las notificaciones que ya fueron revisadas y las que están pendientes, y agregar información sobre la ficha del aprendiz.

### Reingeniería

Para mejorar el sistema se debería mantener su diseño sencillo, pero organizar mejor la información. Algunas mejoras serían:

* Mostrar de forma más visible la próxima formación.
* Diferenciar las notificaciones leídas de las que todavía no se han revisado.
* Mostrar el día y la fecha actual.
* Agregar información sobre el líder de la ficha.
* Resaltar los cambios importantes, como cancelaciones o reprogramaciones.
* Utilizar los términos que normalmente usa el SENA.

Con estos cambios, el aprendiz podría revisar su horario más fácilmente y tendría menos posibilidades de perder información importante.

---

## Rol: Instructor

El instructor también es uno de los usuarios principales del sistema. Además de revisar su horario, puede administrar su disponibilidad y realizar el seguimiento de las fichas que tiene a cargo.

### Alcance

El instructor cuenta con 6 pantallas:

19. Mi horario - semana
20. Detalle de sesión
21. Mi disponibilidad
22. Modal crear excepción
23. Seguimiento de ficha
24. Registrar seguimiento

Estas pantallas permiten que el instructor consulte su horario, revise sus sesiones, indique cuándo está disponible, registre excepciones y haga seguimiento a las fichas que tiene asignadas.

**Todas las pantallas se adaptan a diferentes tamaños de pantalla.**

### Flujograma Principal

El proceso principal del instructor es el siguiente:

1. Ingresar al sistema con sus credenciales.
2. Revisar las formaciones que tiene programadas.
3. Seleccionar una sesión para consultar sus detalles.
4. Revisar su disponibilidad y registrar una excepción cuando sea necesario.
5. Consultar el seguimiento de sus fichas.
6. Registrar el seguimiento correspondiente, ya sea académico, de bienestar, proyecto o etapa productiva.

A diferencia del aprendiz, el instructor no solo consulta información, sino que también puede realizar cambios y registrar información relacionada con sus actividades.

### Entendimiento de UI / UX

1. **Qué entiende rápido:** El instructor puede encontrar fácilmente su horario, revisar una sesión, consultar su disponibilidad y acceder al seguimiento de sus fichas.
2. **Qué no queda claro:** No se entiende completamente cómo una excepción o cambio en la disponibilidad afecta las sesiones que ya están programadas.
3. **Qué botones o textos sobran:** Las opciones principales están organizadas de manera sencilla y no se observan elementos que sobren.
4. **Qué información falta:** Sería bueno mostrar más claramente el estado de las sesiones. También sería útil poder adjuntar un documento cuando se registre una excepción y tener un resumen del avance de cada ficha.
5. **Qué error podría cometer:** El instructor podría registrar mal una excepción o hacer un seguimiento sin tener claro a qué ficha o sesión corresponde.
6. **Qué consecuencia tendría:** Esto podría generar problemas o errores en el horario y en la información relacionada con el seguimiento de las fichas.

### Comparación con SIGA

El MockUp complementa algunas de las funciones que ya existen en los sistemas del SENA para manejar horarios y hacer seguimiento académico.

Una de sus ventajas es que reúne varias funciones en un mismo lugar. Así, el instructor puede revisar su horario, manejar su disponibilidad y registrar seguimientos sin tener que realizar estos procesos por separado.

Aun así, sería importante mejorar la relación entre la disponibilidad del instructor, las sesiones programadas y el seguimiento, para que los cambios realizados sean más fáciles de entender.

### Reingeniería

Para mejorar el sistema se propone mantener la idea de tener todo en un mismo lugar, pero haciendo más clara la relación entre las diferentes funciones. Algunas mejoras serían:

* Mostrar claramente cómo la disponibilidad afecta el horario.
* Mostrar las excepciones directamente en la sección de **Mi horario**.
* Indicar claramente la ficha y la sesión antes de registrar un seguimiento.
* Crear una vista general para conocer el avance de una ficha.
* Permitir adjuntar documentos que sirvan como soporte de las excepciones.

Con estas mejoras, el instructor podría organizar mejor su horario y hacer el seguimiento de sus fichas de una manera más sencilla, reduciendo errores y evitando tener que repetir procesos.
