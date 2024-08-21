# Proyecto de API de Gestión de Ventas

Este proyecto es una API RESTful desarrollada en .NET 8 utilizando Entity Framework Core para gestionar una base de datos con las tablas de `Productos`, `Clientes`, `Ventas` y `DetallesVenta`. La API permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en estas entidades y proporciona un endpoint para obtener el esquema de la base de datos.

## Tecnologías Utilizadas

- .NET 8
- Entity Framework Core
- SQL Server

## Estructura del Proyecto

### Modelos

1. **Producto**: Representa los productos disponibles para la venta.
   - `IdProducto` (int)
   - `NombreProducto` (string)
   - `Descripcion` (string)
   - `Precio` (decimal)
   - `Stock` (int)
   - `FechaCreacion` (DateTime)
   - `FechaModificacion` (DateTime)

2. **Cliente**: Representa los clientes que realizan compras.
   - `IdCliente` (int)
   - `NombreCliente` (string)
   - `Correo` (string)
   - `Telefono` (string)
   - `Direccion` (string)
   - `FechaRegistro` (DateTime)

3. **Venta**: Representa las ventas realizadas a los clientes.
   - `IdVenta` (int)
   - `IdCliente` (int)
   - `FechaVenta` (DateTime)
   - `TotalVenta` (decimal)

4. **DetalleVenta**: Representa los detalles de cada venta, incluyendo los productos vendidos.
   - `IdDetalleVenta` (int)
   - `IdVenta` (int)
   - `IdProducto` (int)
   - `Cantidad` (int)
   - `PrecioUnitario` (decimal)
   - `Total` (decimal) [Calculado]

### Configuración del Proyecto

1. **Conexión a la Base de Datos**

   Asegúrate de configurar la cadena de conexión en `appsettings.json`:

   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=your_server;Database=your_database;User Id=your_user;Password=your_password;"
     }
   }