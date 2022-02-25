# Dom
## Qué es el dom?
El Dom es el **Document Object Model** 
que representa toda la estructura de la página HTML en forma de nudos.
![[Screenshotter--YouTube-CursodeJAVASCRIPTdesdeCEROCompleto-NivelJUNIOR-465’50”.jpg]]

<hr>

## Métodos de selección de elementos
| Método | Función |
|-----------|------------|
| getElementByID| *Selecciona el elemento por ID* |
| getElementByTagName | *Selecciona todos los elementos que coincidan con el nombre de la etiqueta especificada* |
| querySelectol | *Devuelve el primer elemento que coincida con el grupo especificado de selectores* |
| querySelectorAll |  *Devuelve todos los elementos que coincidan con el grupo específicado* |

<hr>

## Métodos para Definir, Obtener y Eliminar valores de atributos

| Método | Función |
|-----------|------------|
| setAttribute | Modifica el valor de un atributo|
| getAttribute | Obtiene el valor de un atributo |
| removeAttribute | Remueve el valor de un atributo|

<hr>


## Inputs atributos
GG ez.

##  Clases, classList y Metodos de classList
| Método | Función |
|-----------|------------|
| .add | añade una clase a un elemento|

```js
let hola = parseInt(prompt("Dime tu edad"));

if (hola >= 18) {
  let tittle = document.querySelector(".titulo");
  tittle.classList.add("elPepe"); //add, añade una clase
  document.writeln("<br><br>" + "<h1 class = 'elPepe'>" + "Eres mayor de edad" + "</h1>");
} else {
  let tittle = document.querySelector(".titulo");
  tittle.classList.add("menorDeEdad");
  document.writeln("<br><br>" + "<h1 class = 'menorDeEdad'>" + "Eres menor de edad" + "</h1>");
};
```
![[Pasted image 20210818160742.png]]

![[Pasted image 20210818160755.png]]

![[Pasted image 20210818160813.png]]

![[Pasted image 20210818160824.png]]

<hr>

| Método | Función |
|-----------|------------|
| .remove | elimina una clase a un elemento|

Tiene la clase
![[Pasted image 20210818161052.png]]

```js
let tittle = document.querySelector(".titulo")

tittle.classList.remove("titulo");
```


No tiene la clase
![[Pasted image 20210818161121.png]]

<hr>

| Método | Función |
|-----------|------------|
| .contains | lo que hace es decirnos si una clase existe o no|

```js 
let tittle = document.querySelector(".titulo")

let valor = tittle.classList.contains("titulo");

if (valor == true) {
  document.writeln(`<span class="true">La clase SI existe</span>`);
} else {
    document.writeln(`<span class="false">La clase NO existe</span>`)
};
```

| Método | Función |
|-----------|------------|
| .toggle | Si no tiene la clase especificada, la agrega, si ya la tiene, la elimina. |
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="../cap4/style.css">
    <title>Cap 6</title>
</head>
<body>
	<h1 class="titulo grande">titulo fachero</h1>
<script src="font.js"></script>
<script src="index.js"></script>
</body>
</html>
```

```js
const titulo = document.querySelector(".titulo");

nombreDeClase = "grande";
let valor = titulo.classList.contains(nombreDeClase);

titulo.classList.toggle("grande");
```

![[Pasted image 20210819144040.png]]

Pero si le damos true, la deja igual.

```js
const titulo = document.querySelector(".titulo");

nombreDeClase = "grande";
let valor = titulo.classList.contains(nombreDeClase);

titulo.classList.toggle("grande",true);
```

Pero si le damos false, la va a sacar siempre.

```js
const titulo = document.querySelector(".titulo");

nombreDeClase = "grande";
let valor = titulo.classList.contains(nombreDeClase);

titulo.classList.toggle("grande",false);
```


## Obtención y modificación de elementos
| Método | Función |
|-----------|------------|
| .textContent | Devuelve el texto de cualquier nodo |
| .innerText | devuelve el texto visible de un node element|
| .innerHTML | devuelve el contenido de un elemento|
| .outerHTML | devuelve el codigo HTML completo del elemento|

<hr>

textContent nos muestra **todo** el texto del nodo aunque esté invisible, pero no nos muestra las etiquetas 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="../cap4/style.css">
    <title>Cap 6</title>
</head>
<body>

    <p class="titulo">Esto es un texto muy <b>Fachero</b></p>

<script src="font.js"></script>
</body>
</html>
```

```css
body {
    background-color: rgb(37, 37, 37);
    color: white;
    font-size: 34px;
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
    margin-top: 24px;
}

b {
  visibility: hidden; /*el contenido esta invisible, pero textContent lo muestra*/
}

h5 {
    color: rgb(27, 230, 162);
}
```

```js
const titulo = document.querySelector(".titulo");

let resultado = titulo.textContent;

document.write(resultado);
```

![[Pasted image 20210819154000.png]]

<hr>

innerText, solo muestra el contenido visible, pero ya no se usa porque se creo solo para una funcionalidad de internet explorer, como ya sabemos, Internet Explorer está mas muerto y sin esperanzas que el matrimonio los papás de Gerardo.<br>
*Pd: consume muchos recursos al utilizarse*
```js
const titulo = document.querySelector(".titulo");

let resultado = titulo.innerText;

document.write(resultado);
```

![[Pasted image 20210819154158.png]]

```js
const titulo = document.querySelector(".titulo");

let resultado00 = titulo.textContent; //esta etiqueta la usaremos mucho
let resultado01 = titulo.outerHTML; //esta otra tambien
let resultado02 = titulo.outerHTML;

alert(resultado00);
alert(resultado01);
alert(resultado02);
```

## Creación de elementos
| Metodo | Funcion |
|-------------|-------------|
| createElement() | lo que hace es crear elementos|
| createTextNode | Lo que hace es crear un nodo de text|
| appendChild() | No se que hace XDDDD

Esta es la forma correcta de crear muchos elementos en javascript

```js
const  container  = document.getElementById('ul'); // assuming ul exists

const fragmento = document.createDocumentFragment();

for (i = 0; i < 5; i++) {
  const item = document.createElement('LI');
  item.innerHTML = "este es un item de la lista";
  fragmento.appendChild(item);
}

container.appendChild(fragmento);
```

## Obtención y modificacion de childs

| Propiedades | Funcion |
|-------------|-------------|
| firstChild | lo que hace es obtener el primer hijo |
| lastChild | lo que hace es darnos el último hijo |
| firstChildElement | lo que hace es darnos el primer hijo nodo |
| lastElementChild | lo que hace es darnos el último hijo nodo |
| childNotes | lo que hace es mostrarnos todos los nodos |
| children | lo que hace es mostrarnos 
|

```html
    <div class="noMeLaContainer"><h1>Un titulo común</h1> // el primer hijo va al lado del inicio dle div
      <h5>H5 común</h5>
      <p>Un párrafo común</p>
      <span>un span común</span></div> // el ultimo hijo va al lado izquierdo del final
```

```js
const container = document.querySelector(".noMeLaContainer");

const primerHijo = container.lastChild;

console.log(primerHijo);
```

La forma correcta de solucionarlo es usando [[firstElementChild]] y [[lastElementChild]]

Los nodulos hijos no se pueden recorrer con funciones para arrays, pero si se pueden usar bucles

```js
const container = document.querySelector(".noMeLaContainer");

const hjs = container.childNodes;

hjs.forEach(hijo => console.log(hijo));

console.log(hjs);
```

Escribiendo children, se accede a todos los nodulos hijos sin contar el texto 

```js
const container = document.querySelector(".noMeLaContainer");

const hjs = container.children;

console.log(hjs);
```

## Métodos de childs (hijos)
### replaceChild
*replaceChild()* nos reemplaza el primer nodulo hijo que especificamos en el primer parametro, con el segundo nodo que especificamos en el segundo parametro.

```js
const contenedor = document.querySelector(".noMeLaContainer");

const parrafo = document.createElement('P');
const h2_nuevo = document.createElement('H2');
h2_nuevo.innerHTML = 'Titulo';

h2_antiguo = document.querySelector('.h2');

contenedor.replaceChild(h2_nuevo,h2_antiguo);
```

```html
<div class="noMeLaContainer">
      <h2 class="h2">Un titulo común</h2>
      <h4>H5 común</h4>
      <p>Un párrafo común</p>
    </div>
```
	
![[Pasted image 20210822025104.png]]

### removeChild
Lo que hace removeChild, es remover el hijo que especificamos.
```js
const contenedor = document.querySelector(".noMeLaContainer");

const parrafo = document.createElement('P');
const h2_nuevo = document.createElement('H2');
h2_nuevo.innerHTML = 'Titulo';

h2_antiguo = document.querySelector('.h2');

contenedor.removeChild(h2_antiguo);
```

![[Pasted image 20210822025713.png]]

### hasChildNodes 
hasChildNodes nos retorna un booleano true o false en caso de que un elemento tengo nodulos hijos
```js 
const contenedor = document.querySelector(".noMeLaContainer");

const parrafo = document.createElement('P');
const h2_nuevo = document.createElement('H2');
h2_nuevo.innerHTML = 'Titulo';

h2_antiguo = document.querySelector('.h2');

let result = h2_nuevo.hasChildNodes();

if  (result) {
    document.write("El elemento tiene hijos");
    console.log(parrafo);
} else {
    document.write("El documento No tiene hijos")
};
```

### parentElement
Este es muy fácil, lo que hace es devolvernos el nodulo padre de un elemento

```js
const contenedor = document.querySelector(".noMeLaContainer");

const parrafo = document.createElement('P');
const h2_nuevo = document.createElement('H2');
h2_nuevo.innerHTML = 'Titulo';

h2_antiguo = document.querySelector('.h2');

let result = h2_nuevo.parentElement;

console.log(contenedor.parentElement)
```

## propiedades de siblings (hermanos)
Los hermanos son los nodos que estan al lado.
```html
<div class="noMeLaContainer">
      <h2 class="h2">Un titulo común</h2> <!-- Este es hermano del de abajo -->
      <h4>H5 común</h4> <!-- este es hermano del de abajo-->
      <p>Un párrafo común</p>
    </div>
```

En resumen, los que estan en el mismo rango son hermanos.

| propiedad | funcion |
|-----------------|------------|
| nextElementSibling | lo que hace es mostrarnos el **siguiente** elemento hermano de un nodo |

```js
h2_nuevo.innerHTML = 'Titulo';

h2_antiguo = document.querySelector('.h2');

let result = h2_nuevo.parentElement;

console.log(h2_antiguo.nextElementSibling); //toma como referencia el codigo html anterior
```

| propiedad | funcion |
|-----------------|------------|
| previousElementSibling | lo que hace es mostrarnos el elemento **anterior** del hermano de un nodo |

```js
h2_nuevo.innerHTML = 'Titulo';

h2_antiguo = document.querySelector('.h2');

let result = h2_nuevo.parentElement;

console.log(h2_antiguo.previousElementSibling); // aqui está la diferencia entre previous y next
```

| propiedad | funcion |
|-----------------|------------|
| nextElementSibling | El método `**closest()**` de la interfaz [`Element`](https://developer.mozilla.org/es/docs/Web/API/Element) devuelve el ascendiente más cercano al elemento actual (o el propio elemento actual) que coincida con el selector proporcionado por parámetro. Si no existe dicho ascendiente, devuelve `null`. |

```js
const div = document.querySelector('.div3');
const divClosest = div.closest('.div')

console.log(divClosest);
```

