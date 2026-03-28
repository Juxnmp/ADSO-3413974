# Manual básico para realizar commits en Git

## 1. ¿Qué es un commit?

Un **commit** es un registro de los cambios realizados en un proyecto
controlado con Git. Cada commit guarda una "foto" del estado del
proyecto en un momento específico, permitiendo llevar control de
versiones, rastrear modificaciones y colaborar con otros
desarrolladores.

------------------------------------------------------------------------

## 2. Requisitos previos

Antes de realizar commits, es necesario:

-   Tener **Git instalado** en el sistema.
-   Haber **inicializado un repositorio** o clonado uno existente.
-   Tener archivos modificados o nuevos dentro del proyecto.

Ejemplo para inicializar un repositorio:

``` bash
git init
```

------------------------------------------------------------------------

## 3. Flujo básico para hacer un commit

El proceso estándar para registrar cambios en Git consta de tres pasos:

### 1. Revisar los cambios

Permite ver qué archivos fueron modificados.

``` bash
git status
```

### 2. Agregar archivos al área de preparación (staging)

Se seleccionan los archivos que harán parte del commit.

Agregar un archivo específico:

``` bash
git add archivo.txt
```

Agregar todos los archivos modificados:

``` bash
git add .
```

### 3. Crear el commit

Se registra oficialmente el cambio con un mensaje descriptivo.

``` bash
git commit -m "Descripción clara del cambio realizado"
```

Ejemplo:

``` bash
git commit -m "Se agrega validación de datos en el formulario de registro"
```

------------------------------------------------------------------------

## 4. Buenas prácticas al hacer commits

Para mantener un historial claro y organizado, se recomienda:

-   Escribir **mensajes claros y específicos**.
-   Realizar **commits pequeños y frecuentes**.
-   No incluir archivos innecesarios o temporales.
-   Mantener una **estructura consistente en los mensajes**.

Ejemplo de buen mensaje:

    Corrige error en cálculo de totales del carrito

Ejemplo de mal mensaje:

    arreglos

------------------------------------------------------------------------

## 5. Estructura recomendada (Conventional Commits)

Una forma común de escribir commits es usar un prefijo que indique el
tipo de cambio:

  Tipo       Uso
  ---------- --------------------------------------------
  feat       Nueva funcionalidad
  fix        Corrección de errores
  docs       Cambios en documentación
  style      Cambios de formato
  refactor   Mejora de código sin cambiar funcionalidad
  test       Agregar o modificar pruebas

Ejemplos:

    feat: se implementa módulo de autenticación
    fix: se corrige error en validación de contraseña
    docs: se actualiza manual de usuario

------------------------------------------------------------------------

## 6. Ver historial de commits

Para consultar los commits realizados en el proyecto:

``` bash
git log
```

Versión resumida:

``` bash
git log --oneline
```

------------------------------------------------------------------------

## 7. Recomendaciones en proyectos colaborativos

Cuando se trabaja en equipo:

-   Hacer commits antes de subir cambios al repositorio remoto.
-   Mantener mensajes entendibles para otros desarrolladores.
-   Evitar subir código sin probar.
-   Usar ramas para nuevas funcionalidades.

Ejemplo:

``` bash
git checkout -b nueva-funcionalidad
```

------------------------------------------------------------------------

## 8. Conclusión

El uso correcto de commits permite mantener un historial claro del
desarrollo del software, facilita la colaboración entre desarrolladores
y permite recuperar versiones anteriores del proyecto en caso de
errores. Aplicar buenas prácticas en la escritura de commits contribuye
a una mejor organización y mantenimiento del código a largo plazo.
