# JsonServer

Software JsonServer 
https://github.com/typicode/json-server



1=> Terminal Code Open
2=>npm init -y   //We were get package.json
3=>npm i json-server //This install Module and dependencie
4=>Create file db.json	//Va a simular la BD
5=>{Insert data we will use}
Example=>{
    "products":[
        {
            "id": 1,
            "name": "laptop",    
            "price": 1599.99,
            "description": "HP Laptop",
            "categoryId":1
        }
    ],
    "categories":[

    ]
}
6=> Go to de packege.json for init in the propertie
"test" we could change the name for "server"
7=> "server":"json-server --wath db.json(file simultor BD)"

 (this execute Module json-server)
With it, we restart BD when we changed in the Base datos
8=> Run the server in the terminal
9=> npm run server	
	this gives us the URLs/ENDPOINT that we can consult
	example:
	Resources
	http://localhost:3000/products
  	http://localhost:3000/categories
	Home
  	http://localhost:3000

//Con todo esto tenemos una REST-API
//usamos la extension para el chrom JSONVIVER
Comando utiles
http://localhost:3000/db => toda la BD en el archivo JSON
http://localhost:3000/products/2 => filtro por el ID=2
http://localhost:3000/categories/2/productos =>"" de categoria 2 TODOS los PRODUCTOS(RELACION)
http://localhost:3000/products?_limit=2  =>limita a 2 datos
http://localhost:3000/products?price_gte=1000   => cuyo precio sea mayor a 1000
http://localhost:3000/products?price_lte=100   => cuyo precio sea menor a 100
--Convinacion!!
http://localhost:3000/products?price_lte=20&price_gte=20  => Rango de precios
-----Filtro por nombre
CONSULTAS RAPIDAS
http://localhost:3000/products?q=keyboard
http://localhost:3000/products?q=laptop
http://localhost:3000/products?q=1399.99
----
Paginacion
limite 2 elementos por PAGINA
http://localhost:3000/products?_page=1&_limit=2  => en la pagina 1 indicamos que tenga 2 elementos
http://localhost:3000/products?_page=2&_limit=2  => en la pagina 2 indicamos que tenga 2 elementos
----
Ordenamientos
http://localhost:3000/products?_sort=name  =>los busca por el atributo name
http://localhost:3000/products?_sort=name&_order=desc  =>los busca y los ordenamos por el atributo/propiedad name
http://localhost:3000/products?_sort=name&_order=asc  =>los busca y los ordenamos por el atributo name

--Chequiamos con el CLIENTE REST POSTMAN

Para insert datos
1=> Headers
2=>key= Content-Type-----------value =application/json
3=> POST	{
   		"name":"keyboard two",
    		"price": 499.99,
    		"description":"gaming keyboard corsair",
    		"categoryId":2
		}
//El servidor automaticamente le agrega el ID increment
PUT => Tenemos que actualizar todos los campos
PATCH=> Actualizamos las propiedades que queremos
	=>http://localhost:3000/products/5   actualizamos el ID 5

---Delete 
		http://localhost:3000/products/5
