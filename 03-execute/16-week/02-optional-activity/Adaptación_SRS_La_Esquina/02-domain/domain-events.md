# Eventos del Dominio

**Estado:** 🟢 Estable  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina

---

## Eventos Identificados

Los eventos del dominio son hechos relevantes que ocurren dentro del sistema y que pueden desencadenar otras acciones.

| ID | Evento | Disparado cuando... | Efecto |
|----|--------|---------------------|--------|
| EV01 | `ProductoRegistrado` | El administrador guarda un nuevo producto | El producto queda disponible en el inventario y para la venta |
| EV02 | `ProductoActualizado` | El administrador edita un producto existente | Los cambios se reflejan en tiempo real en inventario y punto de venta |
| EV03 | `ProductoEliminado` | El administrador elimina un producto | El producto deja de estar disponible en el sistema |
| EV04 | `VentaRegistrada` | El cajero confirma una venta | Se descuenta el stock, se genera la factura |
| EV05 | `FacturaGenerada` | Se registra una venta | Se crea el documento de factura con el detalle de la transacción |
| EV06 | `StockActualizado` | Se registra una venta o el administrador modifica el inventario | El stock del producto cambia |
| EV07 | `AlertaStockBajo` | El stock de un producto cae por debajo del umbral mínimo | Se notifica al administrador / cajero |
| EV08 | `ReporteGenerado` | El administrador solicita un reporte | El sistema consolida los datos del rango de fechas y presenta el resultado |
| EV09 | `UsuarioCreado` | El administrador crea un nuevo usuario | El usuario puede acceder al sistema con sus credenciales |

## Referencias

- [Entidades y reglas](./entities-and-rules.md)
- [Casos de uso](../04-requirements/user-stories.md)
