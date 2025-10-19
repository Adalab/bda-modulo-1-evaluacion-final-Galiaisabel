                                 # Evaluación módulo 1 Data Analytics

 ## Estructura
    En principio tenemos 3 variables que almacenan diferentes tipos de datos.
        * **inventario_producto** *  --> Un atributo para almacenar los productos en el inventario. Cada
                                       producto es representado como un diccionario con las siguientes claves: 
                                       + 'nombre' 
                                       + 'precio'
                                       + 'cantidad'
            Iniciaremos inventario_producto como una lista vacía. 
            Esto es un ejemplo de como debería de ser:

                  [ {'nombre': 'Camisa', 'precio': 20, 'cantidad': 40},
                    {'nombre': 'Pantalón', 'precio': 30, 'cantidad': 30},
                    {'nombre': 'Zapatos', 'precio': 50, 'cantidad': 25},
                    {'nombre': 'Chaqueta', 'precio': 70, 'cantidad': 15},
                    {'nombre': 'Falda', 'precio': 25, 'cantidad': 20},
                    {'nombre': 'Gorra', 'precio': 10, 'cantidad': 50},
                    {'nombre': 'Bufanda', 'precio': 15, 'cantidad': 35},
                    {'nombre': 'Calcetines', 'precio': 5, 'cantidad': 100},
                    {'nombre': 'Cinturón', 'precio': 12, 'cantidad': 40},
                    {'nombre': 'Bolso', 'precio': 45, 'cantidad': 18}]

                           
        * **clientes** --> Un diccionario, con una clave que será nombre; email y compras serán los valores.

                Tendríamos que tener nuestro diccionario así:
                 { 'Ana García': {'email': 'ana.garcia@email.com', 'compras': []},
                    'Luis Fernández': {'email': 'luis.fernandez@email.com', 'compras':
                    []},
                    'María López': {'email': 'maria.lopez@email.com', 'compras': []},
                    'Carlos Ruiz': {'email': 'carlos.ruiz@email.com', 'compras': []},
                    'Elena Martín': {'email': 'elena.martin@email.com', 'compras': []},
                    'Javier Torres': {'email': 'javier.torres@email.com', 'compras': []},
                    'Lucía Sánchez': {'email': 'lucia.sanchez@email.com', 'compras': []},
                    'Sergio Díaz': {'email': 'sergio.diaz@email.com', 'compras': []},
                    'Patricia Ramos': {'email': 'patricia.ramos@email.com', 'compras': []}}     

        * **venta_totales** --> Variable de tipo float.
                                Iniciamos valor con 0.0

 ## Funciones
    
    7 funciones principales:
     * agregar_producto(nombre, precio, cantidad)
     * ver_inventario()
     * buscar_producto(nombre)
     * actualizar_stock(nombre, cantidad)
     * eliminar_producto(nombre)
     * calcular_valor_inventario()
     * realizar_compra()

 
 
  ### agregar_producto(nombre,precio,cantidad)
  Agrega un producto al inventario o actualiza la cantidad si ya existe.
  Para recorrer el inventario usamos el bucle *for*, usamos la condicional *if* para comparar el nombre del producto existente con el nuevo. Usamos 2 métodos para `nombre`:
        1. lower() -->para pasar todo el string a minúscula 
        2. strip() -->para quitar los espacios.
    Si existe el producto, sumamos la cantidad que ya teniamos con la cantidad pasada en parámetro.
    Si no agregamos un nuevo producto(primero creamos el producto y luego lo añadimos con appened() al inventario)
            producto_nuevo = {
                "nombre": nombre.lower().strip(),
                "precio" : precio,
                "cantidad" : cantidad
                }   
            *inventario_producto.appened(producto_nuevo)*
  Mostramos un mensaje en ambas situaciones.

  ### ver_inventario()
  Muestra el inventario productos con sus detalles, para esto usamos *for* para recorrer mi lista de productos con un print dentro de mi bucle para imprimar cada producto.
  No pasamos ningún dato por parámetro porque no lo necesitamos, lo que queremos es mostrar el inventario en general.
  *como extra* hemos comprobado si el inventario está vacío para que devuelva un mensaje si lo está.

  ### buscar_producto(nombre)
Esta función permite buscar un producto dentro de un inventario y devuelve sus detalles (nombre, precio y cantidad) si el producto existe. En caso contrario, indica que el producto no se encuentra en el inventario.

  ### actualizar_stock(nombre, cantidad)
Esta función permite actualizar la cantidad de stock de un producto en el inventario. Recibe el nombre del producto y la cantidad a agregar (o quitar si es negativa). Si el producto no existe, devuelve un mensaje informando.

Como en las funciones anteriores, y ya hemos mencionado anteriormente para recorrer una lista usamos *for*, con un *if* comprobamos si el producto está o no en el inventario(por el nombre), cremaos una variable(*cant*) para guardar el resultado de la operación suma o resta, *cant* lo usaremos para comprobar:
    - Si es menos a 0 --> cantidad no puede ser negativo.
    - Si no *cant* sería nuestra nueva cantidad del producto.

  ### eliminar_producto(nombre)
  La función elimina_producto(nombre) elimina un producto del inventario según el nombre proporcionado. Si el producto existe, se elimina del inventario; de lo contrario, se notifica al usuario.
  Recorre el inventario.
  Comparamos el nombre del producto(pasado por parámetro) con el nombre de los productos que hay en la lista.Si hay coincidencia:
   Elimina el producto del inventario.
  Si no eencuentra el producto en la lista, muestra un mensaje. 


  ### calcular_valor_inventario():
   La función recorre todos los productos del inventario y suma el total multiplicando el precio por la cantidad de cada producto.


   ### realizar_compra()


   ### procesar_pago()

   ### agregar_cliente(nombre, email)


   ### ver_clientes()