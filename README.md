# marketplace-analysis


Se propone un escenario en el que hay que realizar unos análisis sobre las ventas de determinado marketplace. En la carpeta compressedData está almacenada información en formato parquet de las ventas realizadas por distintos sellers en dicho marketplace.

-La información provista contiene el siguiente detalle: ●id: identificador del ítem vendido ●sellerId: identificador del vendedor 
●sales: cantidad de unidades vendidas del ítem 
●price: precio unitario del ítem vendido
●currency: moneda en que se realizó la transacción 
●category: categoría de productos a la que pertenece el ítem vendido 
●title: título de la publicación del ítem vendido

Suele suceder que la información no llega 100% completa y limpia. Es posible que no todos los schemas de las tablas sean iguales y/o que no todos los campos estén completos para todas las filas. Los campos que se aseguran están completos son "id", "sellerId", "sales", "price" y "currency".

A continuación hay un ejemplo de la tabla conformada por la lectura de la información en la carpeta compressedData: -El ítem con id "MLA123456" vendió en total 10 unidades (sales), con una facturación total (GMV) de 1.550 ARS (sales * price).

![image](https://github.com/user-attachments/assets/0dc3f81f-83cb-4e09-892f-c42c304f1727)


Dada la información alojada en la carpeta provista realizar un script que genere: 1.[OPERACIONES DE LECTURA] Lectura de los archivos de los primeros 7 días del mes. En caso de haber días faltantes en el período analizado, logear dichas fechas para identificar cuáles son los faltantes. 2.[OPERACIONES DE TABLA] Agregar una columna al dataframe leído en el punto 1 que calcule la facturación de cada venta (cada fila es una venta). 3.[OPERACIONES DE SUMARIZACIÓN] a- Calcular la facturación total de cada seller. b- Calcular el total de unidades vendidas por ítem. 4.Asignar un ranking a cada vendedor según los totales calculados en el punto 3 a. Cada vendedor debe obtener una posición en el ranking según el total facturado, siendo la posición 1 la de mayor facturación. Guardar el ranking en formato de un único CSV. 5.[OPERACIONES DE ESCRITURA] Guardar en formato parquet el dataframe del punto 2 de forma particionada por año, mes, seller.
