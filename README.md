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
 