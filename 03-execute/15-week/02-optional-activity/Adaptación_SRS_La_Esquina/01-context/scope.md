# Alcance del Sistema

**Estado:** 🟢 Estable  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina

---

## ¿Qué incluye el sistema?

| Módulo | Descripción |
|--------|-------------|
| Gestión de productos | Registro, edición, eliminación y consulta de productos (nombre, precio, categoría, stock) |
| Control de inventario | Entradas y salidas automáticas; alertas de stock bajo |
| Registro de ventas | Registro de cada transacción realizada por el cajero |
| Generación de facturas | Factura automática con detalle de productos y totales |
| Reportes | Reportes diarios, semanales y mensuales de ventas e inventario |
| Gestión de usuarios | Creación y administración de cuentas: Administrador y Cajero |

## ¿Qué NO incluye el sistema?

- Venta en línea (e-commerce)
- Integración con bancos o pasarelas de pago digital
- Aplicación móvil

## Actores del Sistema

| Actor | Tipo | Rol |
|-------|------|-----|
| Administrador | Interno directo | Gestiona productos, precios, inventario, reportes y usuarios |
| Cajero | Interno directo | Registra ventas y genera facturas |
| Cliente | Externo indirecto | Recibe la atención del cajero y obtiene la factura; no interactúa directamente con el sistema |

## Referencias

- [Visión general](./overview.md)
- [Requerimientos funcionales](../04-requirements/functional.md)
- [Casos de uso](../04-requirements/user-stories.md)
