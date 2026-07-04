# Matriz de Trazabilidad

**Estado:** 🟢 Estable  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina

---

> Esta matriz vincula los requerimientos funcionales con los casos de uso que los implementan.

## RF × Casos de Uso

| Requerimiento | Nombre | CU01 Registrar Venta | CU02 Gestionar Inventario | CU03 Generar Reportes |
|---------------|--------|:-------------------:|:-------------------------:|:---------------------:|
| RF01 | Registro de productos | | ✅ | |
| RF02 | Actualización de productos | | ✅ | |
| RF03 | Eliminación de productos | | ✅ | |
| RF04 | Consulta de productos | | | ✅ |
| RF05 | Gestión de inventario | ✅ | ✅ | |
| RF06 | Registro de ventas | ✅ | | |
| RF07 | Generación de factura | ✅ | | |
| RF08 | Control de usuarios | | | |
| RF09 | Reportes de ventas | | | ✅ |
| RF10 | Alertas de stock bajo | ✅ | | |

> **Nota:** RF08 (Control de usuarios) no tiene un caso de uso detallado aún — pendiente de documentar en próxima iteración.

## RNF × Módulos del Sistema

| Requerimiento | Nombre | Ventas | Inventario | Reportes | Usuarios |
|---------------|--------|:------:|:----------:|:--------:|:--------:|
| RNF01 | Usabilidad | ✅ | ✅ | ✅ | ✅ |
| RNF02 | Rendimiento < 2 seg | ✅ | ✅ | ✅ | |
| RNF03 | Autenticación | ✅ | ✅ | ✅ | ✅ |
| RN01 | Inventario en tiempo real | ✅ | ✅ | | |
| RN02 | Mejora en ventas | ✅ | | | |

## Referencias

- [Requerimientos funcionales](./functional.md)
- [Requerimientos no funcionales](./non-functional.md)
- [Casos de uso](./user-stories.md)
