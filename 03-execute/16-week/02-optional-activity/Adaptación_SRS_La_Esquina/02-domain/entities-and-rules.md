# Entidades y Reglas de Negocio

**Estado:** 🟢 Estable  
**Última actualización:** 2025-06  
**Autor:** Equipo La Esquina

---

## Entidades Principales

### Producto
| Atributo | Tipo | Descripción |
|----------|------|-------------|
| id | identificador único | Código del producto |
| nombre | texto | Nombre descriptivo |
| precio | decimal | Precio de venta al público |
| categoría | texto | Clasificación del producto |
| stock | entero | Unidades disponibles en inventario |
| stock_mínimo | entero | Umbral que dispara la alerta de stock bajo |

### Venta
| Atributo | Tipo | Descripción |
|----------|------|-------------|
| id | identificador único | Número de transacción |
| fecha_hora | fecha/hora | Momento en que se registró la venta |
| cajero | Usuario | Quien registró la venta |
| líneas_de_venta | lista | Productos vendidos con cantidad y precio |
| total | decimal | Suma de todos los productos de la venta |

### Factura
| Atributo | Tipo | Descripción |
|----------|------|-------------|
| id | identificador único | Número de factura |
| venta | Venta | Venta a la que corresponde |
| detalle | lista | Productos, cantidades y precios unitarios |
| total | decimal | Total a pagar |

### Usuario
| Atributo | Tipo | Descripción |
|----------|------|-------------|
| id | identificador único | Código del usuario |
| nombre | texto | Nombre completo |
| rol | enumerado | `Administrador` o `Cajero` |
| credenciales | auth | Usuario y contraseña |

---

## Reglas de Negocio

| ID | Regla | Entidad afectada |
|----|-------|-----------------|
| RB01 | Al registrar una venta, el stock del producto se descuenta automáticamente | Producto, Venta |
| RB02 | Si el stock de un producto cae por debajo del stock_mínimo, se genera una alerta | Producto |
| RB03 | No se puede registrar una venta si el stock del producto es 0 | Venta, Producto |
| RB04 | Toda venta registrada debe generar automáticamente una factura | Venta, Factura |
| RB05 | No se pueden guardar productos con datos incompletos (nombre, precio, stock obligatorios) | Producto |
| RB06 | No se puede registrar un producto duplicado (mismo nombre) | Producto |
| RB07 | Solo el Administrador puede crear, editar o eliminar productos y usuarios | Usuario, Producto |
| RB08 | El Cajero solo puede registrar ventas y consultar productos | Usuario |
| RB09 | El acceso al sistema requiere autenticación obligatoria | Usuario |

## Referencias

- [Mapa de dominio](./domain-map.md)
- [Eventos del dominio](./domain-events.md)
- [Requerimientos funcionales](../04-requirements/functional.md)
