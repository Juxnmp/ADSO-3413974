# Backlog de Producto

**Estado:** 🟡 En progreso  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina

---

> Las historias de usuario están priorizadas por impacto en el negocio y urgencia según el SRS.

## Épicas

| ID | Épica | Descripción |
|----|-------|-------------|
| EP01 | Catálogo de Productos | CRUD completo de productos con nombre, precio, categoría y stock |
| EP02 | Control de Inventario | Movimientos de stock en tiempo real y alertas automáticas |
| EP03 | Punto de Venta | Registro de ventas y emisión de facturas |
| EP04 | Reportes | Generación y consulta de reportes operativos |
| EP05 | Gestión de Usuarios | Autenticación y administración de roles |

## Ítems del Backlog

| ID | Épica | Historia | Prioridad | RF relacionado |
|----|-------|----------|-----------|---------------|
| PBI-01 | EP01 | Como administrador, quiero registrar productos con nombre, precio, categoría y stock | Alta | RF01 |
| PBI-02 | EP01 | Como administrador, quiero editar la información de productos existentes | Alta | RF02 |
| PBI-03 | EP01 | Como administrador, quiero eliminar productos del inventario | Media | RF03 |
| PBI-04 | EP01 | Como cajero, quiero buscar productos por nombre o categoría | Alta | RF04 |
| PBI-05 | EP02 | Como administrador, quiero que el stock se actualice automáticamente al registrar ventas | Alta | RF05 |
| PBI-06 | EP02 | Como administrador, quiero recibir alertas cuando un producto tenga stock bajo | Alta | RF10 |
| PBI-07 | EP03 | Como cajero, quiero registrar cada venta realizada | Alta | RF06 |
| PBI-08 | EP03 | Como cajero, quiero que el sistema genere automáticamente la factura al confirmar una venta | Alta | RF07 |
| PBI-09 | EP04 | Como administrador, quiero generar reportes de ventas diarios, semanales y mensuales | Alta | RF09 |
| PBI-10 | EP05 | Como administrador, quiero crear y gestionar usuarios del sistema (admin y cajero) | Media | RF08 |

## Referencias

- [Visión de producto](./vision.md)
- [Requerimientos funcionales](../04-requirements/functional.md)
