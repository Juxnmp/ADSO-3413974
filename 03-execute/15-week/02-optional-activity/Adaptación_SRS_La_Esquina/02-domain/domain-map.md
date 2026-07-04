# Mapa de Dominio

**Estado:** 🟢 Estable  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina

---

## Contexto del Dominio

El dominio del sistema abarca la operación interna de un supermercado pequeño: gestión del catálogo de productos, control de inventario, registro de transacciones de venta y generación de reportes operativos.

## Subdominios

| Subdominio | Tipo | Descripción |
|------------|------|-------------|
| **Inventario** | Core | Control en tiempo real de la existencia de productos |
| **Ventas** | Core | Registro de transacciones y generación de facturas |
| **Catálogo de Productos** | Supporting | Gestión del maestro de productos con precios y categorías |
| **Reportes** | Supporting | Consolidación y presentación de información operativa |
| **Gestión de Usuarios** | Generic | Autenticación y control de acceso por roles |

## Relaciones entre Subdominios

```
[Catálogo de Productos] ──── alimenta ────► [Inventario]
[Inventario] ──────────── es consultado por ► [Ventas]
[Ventas] ──────────────── genera ───────────► [Factura]
[Ventas] ──────────────── actualiza ────────► [Inventario]
[Inventario + Ventas] ──── son analizados por ► [Reportes]
[Gestión de Usuarios] ──── controla acceso a ► [todos los subdominios]
```

## Actores del Dominio

| Actor | Acceso |
|-------|--------|
| Administrador | Catálogo, Inventario, Reportes, Gestión de Usuarios |
| Cajero | Ventas, Catálogo (consulta), Inventario (consulta) |
| Cliente | Externo — no accede directamente al sistema |

## Referencias

- [Entidades y reglas](./entities-and-rules.md)
- [Eventos del dominio](./domain-events.md)
- [Alcance del sistema](../01-context/scope.md)
