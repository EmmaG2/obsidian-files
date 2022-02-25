# Funciones MongoDB
Las funciones para Crear, consultar, actualizar y eliminar tienen la siguiente sintáxis:

**Nombre_basededatos.nombre_coleccion.funcionCRUD**

# Funcion insertMany

```cmd
db.movie.insertMany([{"Pelicula":"Thor","Duracion":120}])
``` 


# Funcion update

 db.movie.update({"Pelicula" : "StarsWars", "year" : true, "Duracion" : 990},{$set:{Pelicula : "NewMovie", Duracion : 634, "year" : 3012}},{multi:true})
 
 el parametro multi es para modificar muchos elementos a la vez, el parametro upsert es para añadir los cambios si o si en caso de que no se encuentren