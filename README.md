                                 # Evaluación módulo 1 Data Analytics

 ## Estructura
    En principio tenemos 3 variables que almacenan diferentes tipos de datos.
 * **inventario_producto**  --> Un atributo para almacenar los productos en el inventario. Cada
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

                           
 * **clientes** --> Un diccionario, donde cada clave es el nombre y el valor es otro diccionario que almacena email y compras(será una lista).

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
    
    7 funciones :
 * agregar_producto(nombre, precio, cantidad)
 * ver_inventario()
 * buscar_producto(nombre)
 * actualizar_stock(nombre, cantidad)
 * eliminar_producto(nombre)
 * calcular_valor_inventario()
 * realizar_compra()
 * procesar_pago()
 * agregar_cliente(nombre,email)
 * ver_cliente()


 
 
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
   Para esta función crearemos 2 varibles, carro_comrpra[] y total_compra que la iniciaremos a 0.
   Utilizamos un bucle while(mientras que sea true) mostraremos un mensaje al cliente solicitando los productos que desea comprar, también le informamos que para salir escriba "salir" (esta opción saldrá sin más, como en una página de compra seria el botón cerrar) "terminar" para ver el resumen de sus productos seleccionados con el importe total a pagar y dar por terminado la compra.

   Si el cliente introduce un nombre de producto que tenemos en el inventario(recooremos con un *for* y con *if* comprobamos si el nombre introducido coincide con algún producto que tenemos) el programa le pedirá la cantidad a comprar; ahora verificamos:
   - La cantidad introducida es menor a 0(también usamos un *if*) si es así ignoramos el valor que nos dió(continue)y solicitamos otra vez la información.
   - La cantidad introducida es menor o igual a la cantidad que tenemos en stock(*if*) si cumple con esta condición añadimos un nuevo producto en el carro_compra con 4 atributos: nombre,precio->será el precio del producto que tenemos en nuestro inventario de productos, cantidad(la cantidad que inserte el cliente a comprar) y `total_producto` que será la cantidad por el precio de cada producto.
   Añadimos el producyo a nuestro carro con appened()
   Para actualizar nuestro stock restamos la cantidad que teniamos menos la cantidad del nuevo producto.
   Usamos aquí nuestra variable *total_compra* que sería un acumulador de *total_producto* de cada producto.
   - La cantidad introducida es mayor  a la cantidad del producto solicitado.(*else*)

   ### procesar_pago()
    Creo una variable local, interactuamos con el cliente para solicitar el total a pagar y la cantidad con la que hace el pago, 
    Si la cantidad a pagar tiene que ser menor a la cantidad con la que realiza el pago, si lo es hacemos la diferencia y lo guardamos en la cariable cambio, si el cambio es mayor que 0 el pago se habrá relizado, en caso contrario mostrará un mensaje que el monto es insuficiente. Usamos el try:...except por si el usuario no introduce números en las cantidades. 


   ### agregar_cliente(nombre, email)
   Agregamos un nuevo cliente, nombre es la clave y su valor será un diccionario que contendrá email y compras(lista que lo implementaremos más adelante).
   Teniendo en cuenta que la clave no se puede repetir no itero en el diccionario. Porque si intento agregar un cliente con el mismo nombre no me lo añadirá.


   ### ver_clientes()
    Iteremos ahora con el método .items(), para el cual deberemos generar dos iterables (clave, valor)
    Es decir, por cada item del diccionario clientes imprime su clave(nombre) y su valor(email)
   