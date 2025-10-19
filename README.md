<picture>
 <source media="(prefers-color-scheme: dark)" srcset="YOUR-DARKMODE-IMAGE">
 <source media="(prefers-color-scheme: light)" srcset="YOUR-LIGHTMODE-IMAGE">
 <img alt="YOUR-ALT-TEXT" src="YOUR-DEFAULT-IMAGE">
</picture> 
# Evaluación módulo 1 Data Analytics

 ## Estructura
    En principio tenemos 3 variables que almacenan diferentes tipos de datos.
        * **inventario_producto** *  --> Un atributo para almacenar los productos en el inventario. Cada
                                       producto es representado como un diccionario con las siguientes claves: 
                                       +'nombre'
                                       +'precio'
                                       +'cantidad'
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
     *  agregar_producto(nombre, precio, cantidad)
     * ver_inventario()
     * buscar_producto(nombre)
     * actualizar_stock(nombre, cantidad)
     * eliminar_producto(nombre)
     * calcular_valor_inventario()
     * realizar_compra()

 
 
  if cantidad > 0 or cantidad < 0:
                producto["cantidad"] = cantidad + producto["cantidad"]
            else:
                producto["cantidad"] = cantidad

                #actualizar stock
                def actualizar_stock(nombre,cantidad):
    for producto in inventario_producto:
        if producto["nombre"] == nombre: 
         #if cantidad ==0:
          #   producto["cantidad"]=0    
         #else: 
             producto["cantidad"] += cantidad 
        #return producto         
    return "Producto no está en el inventario"   


    def actualizar_stock(nombre,cantidad):
    for producto in inventario_producto:
        if producto["nombre"].strip().capitalize() == nombre.strip().capitalize():  
            producto["cantidad"] += cantidad 
            return f"'Producto actualizado con éxito' {producto}"         
    return f"{nombre} no está en el inventario"


    ef realizar_compra():
 carro_compra=[]
 venta_totales = 0
 ver_inventario() 
 producto_encontrado =True

 while True :
   
    producto_compra=input("Escribe el nombre del producto que deseas comprar , SALIR si deseas abandonar la compra o TERMINAR cuando finalices de elegir los productos")
    if producto_compra == "SALIR":
         print("Hemos salido de la compra")
         break
    
    producto_encontrado=False
    for producto in inventario_producto:          
           if  producto["nombre"].strip().capitalize() == producto_compra.strip().capitalize():
            producto_encontrado=True
            cantidad_comprar=int(input("Cuántas unidades quieres"))

            if cantidad_comprar<=0:
             print("La cantidad tiene que ser mayor a 0")
             continue
              
            if cantidad_comprar <= producto["cantidad"]:
                producto_a_comprar ={
                  "nombre": producto_compra,
                  "precio":producto["precio"],
                  "cantidad": cantidad_comprar,
                  "total_producto":producto["precio"]*cantidad_comprar
               }
                carro_compra.append(producto_a_comprar)
               #actualizo stock
                producto["cantidad"] =producto["cantidad"]-cantidad_comprar
               #sumar el total de cada producto
                venta_totales = venta_totales +producto_a_comprar["total_producto"]
                print(venta_totales)
            else:
                print("Nos falta stock")  

    if  producto_encontrado==False  and producto_compra!="SALIR" and producto_compra !="TERMINAR":        
             print("Producto no enconrado vuelve a intentarlo")
    if producto_compra =="TERMINAR":                 
      print(f"Compra terminada, el coste total de su compra es de: {venta_totales}")  
      break
 
