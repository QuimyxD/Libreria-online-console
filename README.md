# Librería Online (CLI)

Sistema de gestión y venta de libros en consola (CLI) desarrollado en **Python** con persistencia de datos en **JSON** y arquitectura modular.

---

## Características Principales

* **Gestión de Usuarios y Roles:**
  * Registro e inicio de sesión de usuarios.
  * El primer usuario registrado obtiene automáticamente el rol de **Administrador**.
  * Modificación de datos personales (nombre, correo, dirección, contraseña).
  * Gestión de permisos por parte del Administrador.

* **Gestión de Catálogo (CRUD de Libros):**
  * Alta, modificación y desactivación lógica (*soft delete*) de libros.
  * Búsqueda por palabra clave (título, autor o categoría).
  * Filtrado por categoría.
  * Control y actualización automática de stock tras cada compra.

* **Carrito de Compras y Pedidos:**
  * Carrito de compras en memoria durante la sesión activa.
  * Validación estricta de stock disponible antes y durante la confirmación del pedido.
  * Generación de órdenes de compra con historial persistente por usuario y vista general para administradores.

---

## Estructura del Proyecto

```text
libreria_online/
│
├── main.py                          # Punto de entrada de la aplicación y navegación principal
├── README.md                        # Documentación del proyecto
├── datos/                           # Base de datos basada en archivos JSON
│   ├── libros.json                  # Catálogo e inventario de libros
│   ├── usuarios.json                # Registro de cuentas y roles
│   └── pedidos.json                 # Historial de transacciones y pedidos
├── servicios/                       # Lógica de negocio modularizada
│   ├── __init__.py
│   ├── servicio_autenticacion.py    # Login, registro, gestión de usuarios
│   ├── servicio_libros.py           # Operaciones CRUD sobre el catálogo
│   ├── servicio_carrito.py          # Gestión del carrito de compras en memoria
│   └── servicio_pedidos.py          # Confirmación de compra, actualización de stock e historial
|__ Reporte/
|   |___ Reporte.pdf                 # Reporte de código y trabajo en pdf
|
└── utilidades/                      # Módulos auxiliares
    ├── __init__.py
    └── utilidades_json.py           # Lectura y escritura de archivos JSON
```

---

## Requisitos Previos

* **Python 3.8** o superior (no requiere la instalación de librerías externas de terceros).

---

## Instrucciones de Ejecución

1. **Clonar el repositorio o descargar el proyecto:**
   ```bash
   git clone https://github.com/tu-usuario/libreria-online.git
   cd libreria-online
   ```

2. **Ejecutar la aplicación:**
   ```bash
   python main.py
   ```

---

## Notas de Uso e Inicio Rápido

1. **Primer Administrador:**  
   Al ejecutar el sistema por primera vez, el **primer usuario que registres** adquirirá automáticamente el rol de **Administrador**.
2. **Registro de Clientes:**  
   Los registros posteriores se asignarán con el rol estándar de **Cliente**.
3. **Persistencia:**  
   Los archivos `.json` dentro de la carpeta `datos/` se crearán automáticamente al realizar las primeras operaciones.
