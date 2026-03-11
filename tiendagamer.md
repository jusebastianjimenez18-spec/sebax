**TIENDA GAMER**

Una tienda que se basa en la venta de dispositivos hardware , La cual se compone principalmente de PC gamers. La tienda también tiene segmentos de otros segmentos donde se encuentra los demás periféricos gamers. Esta tienda tiene un apartado para armar tu propia PC a tu propio presupuesto si no puedes para las PC´S que ya vienen preensambladas. Todos los componentes tienes su propio precio en su apartado con su respetivo carrito para acumular tus compras.

**HISTORIA DE USUARIO**

**TITULO:**

Tener registro de ganancias y también tener una cuenta de ventas.

**COMO:**

Administrar la tienda y cada uno de sus parámetros.

**QUIERO:**

Registrar la cantidad de ganancias de los periféricos o PC´s y tener la cuenta de ventas totales diariamente.

**PARA:**

Calcular de manera automáticamente las ganancias mensuales de la tienda.

**DESCRIPCION:**

Ser una app que facilite las tediosas tomas de decisiones y que registre las ventas de las PC´s , periféricos o los componentes que cliente pida con sus respectivos precios.

Con esto la app calcula de manera automática la ganancia y el numero de venta del día y guardándola en una base de datos que la guarde y esta posteriormente calcule mensualmente

**REQUISITOS:**

- El sistema debe permitir ingresar:
  - Cantidad de ventas de la PC´s o de los componentes .
  - Precio unitario de las PC´s y de sus componentes.
  - Cantidad de periféricos .
  - Precio unitario de periféricos.
- El sistema debe calcular automáticamente:
  - Total diario.
  - Total mensual.
- El sistema debe permitir consultar reportes mensuales.

**Criterios de aceptación**

- El sistema permite mostrar los productos que ofrece la tienda.
- Cuando el usuario está en el sistema y seleccione un producto el sistema debe permitir continuar con la dicha compra.
- El sistema debe mostrar el total a pagar en su totalidad por el pedido de los productos seleccionados del carrito.

**DIAGRAMA UML**


**Registro y cálculo de ganancias de la tienda**

Sistema Tienda

Admin.de la

tienda

**Caso de uso extendido**

Nombre: Calcular costo total de productos

Actor: Dueño de la tienda

**Propósito**

Registrar la selección de productos y calcular el costo total de la compra para realizar su debido cobro a cada cliente.

**Curso de eventos:**

- El usuario ingresa al sistema la venta del producto.
- El sistema muestra los productos disponibles.
- El usuario selecciona los productos que desea comprar.
- El usuario ingresa la cantidad requerida de cada producto.
- El sistema calcula el costo total mediante la operación:

Total = precio del producto\*cantidad

- Se muestra en la pantalla el valor total a pagar.

**Postcondición**

El costo total de la compra ha sido calculado y mostrado al usuario para proceder con su debido cobro.

Pseudocódigo:
Algoritmo Gestion_Tienda_Gamer
    // Definición de variables globales
    Definir total_diario, total_mensual Como Real
    Definir venta_actual, precio_unitario Como Real
    Definir cantidad, opcion, i Como Entero
    Definir nombre_producto Como Cadena
    
    total_mensual <- 0
    
    Escribir "--- SISTEMA DE GESTIÓN TIENDA GAMER 2026 ---"
    
    Repetir
        total_diario <- 0
        Escribir ""
        Escribir "Menú Principal:"
        Escribir "1. Registrar ventas del día"
        Escribir "2. Consultar Reporte Mensual"
        Escribir "3. Salir"
        Leer opcion
        
        Segun opcion Hacer
            1:
                Escribir "Iniciando registro de ventas diarias..."
                Repetir
                    Escribir "Ingrese nombre del producto (o 'fin' para cerrar el día):"
                    Leer nombre_producto
                    
                    Si nombre_producto <> "fin" Entonces
                        Escribir "Ingrese precio unitario de ", nombre_producto, ":"
                        Leer precio_unitario
                        Escribir "Ingrese cantidad vendida:"
                        Leer cantidad
                        
                        // Cálculo según el curso de eventos del UML
                        venta_actual <- precio_unitario * cantidad
                        total_diario <- total_diario + venta_actual
                        
                        Escribir "Venta registrada: $", venta_actual
                        Escribir "-----------------------------------"
                    FinSi
                Hasta Que nombre_producto = "fin"
                
                // Actualización de la base de datos (simulada)
                total_mensual <- total_mensual + total_diario
                Escribir "CIERRE DEL DÍA: El total diario es: $", total_diario
                
            2:
                Escribir "--- REPORTE MENSUAL ---"
                Escribir "Ganancias acumuladas hasta hoy: $", total_mensual
                Escribir "-----------------------"
                
            3:
                Escribir "Saliendo del sistema..."
            De Otro Modo:
                Escribir "Opción no válida."
        FinSegun
        
    Hasta Que opcion = 3
    
FinAlgoritmo

