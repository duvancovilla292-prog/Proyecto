# Sistema de Gestión para Restaurante/POS (Python)

## Descripción Técnica
Este proyecto implementa un sistema modular de facturación y gestión de recursos (Productos, Mesas, Clientes, Ventas) utilizando Python puro y operaciones nativas de I/O sobre archivos CSV. El sistema garantiza la persistencia de datos relacionales sin requerir motores de bases de datos externos.

## Arquitectura de Archivos y Módulos
El proyecto está estructurado en un modelo de importación para separar la lógica de presentación de la lógica de negocio:

*   `codigo.py`: Actúa como el punto de entrada (Entry Point) del sistema. Contiene el bucle principal de interfaz de usuario (menú interactivo) e importa las rutinas desde el módulo de funciones.
*   `funcionees.py` / `codigo_gestin.py`: Contiene el núcleo lógico y las definiciones de los submódulos. Maneja la lectura, escritura y el enrutamiento de datos hacia los archivos CSV correspondientes.
*   **Almacenamiento Persistente (CSV):** `Productos.csv`, `Mesas.csv`, `Clientes.csv`, y `Ventas.csv`.

## Módulos de Negocio Implementados
1.  **Gestión de Entidades (CRUD Básico):** Submenús independientes para crear y listar **Productos** (Código, Nombre, Valor, IVA), **Mesas** (Código, Nombre, Puestos) y **Clientes** (ID, Nombre, Teléfono, Email).
2.  **Motor de Facturación:** 
    *   Valida la existencia de la Mesa y el Cliente.
    *   Permite el ingreso iterativo de múltiples productos verificando su existencia y calculando subtotales dinámicos (Valor + IVA).
    *   Genera un comprobante físico (`Factura_{cod_m}_{id_c}.txt`) y registra la transacción consolidada en `Ventas.csv`.
3.  **Generación de Reportes:** Extrae las métricas diarias filtrando las transacciones de `Ventas.csv` por fecha, consolidando Venta Bruta, Total IVA y Venta Final. Permite exportar el resumen a un nuevo archivo CSV.

## Autores
* Duvan Steven Covilla
* Javier Alfonso Suarez
* Julio Cesar Panqueva
