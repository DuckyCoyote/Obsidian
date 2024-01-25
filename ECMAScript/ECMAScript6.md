![[Pasted image 20240110151224.png]]
## Diferencias entre ES6 Y ES6
### Funciones Flecha (Arrow Functions)
Una **expresión de función flecha** es una alternativa compacta a una `expresión de función` tradicional, pero es limitada y no se puede utilizar en todas las situaciones.

**Diferencias y limitaciones:**

- No tiene sus propios enlaces a `this` o `super` y no se debe usar como [métodos](https://developer.mozilla.org/es/docs/Glossary/Method).
- No tiene `argumentos` o palabras clave `new.target`.
- No apta para los métodos `call`, `apply` y `bind`, que generalmente se basan en establecer un [ámbito o alcance](https://developer.mozilla.org/es/docs/Glossary/Scope)
- No se puede utilizar como [constructor](https://developer.mozilla.org/es/docs/Glossary/Constructor).
- No se puede utilizar `yield` dentro de su cuerpo.
```js
// ES5
var add = function(number1, number2) {
	return number1 + number2;
}

// ES6
var add = (number1, number2) => number1 + number2;
```
## Template Literals
```js
let hello = 'Hello';
let world = 'World';

// ES5
let epicPhrase = hello + ' ' + world;

console.log("ES5: " + epicPhrase);

// ES6
let tlPhrase = `${hello} ${world}`

console.log("Template Literal(ES6):  " + tlPhrase);
```
## Default Params
```js
// ES5
function newUser(name, age, country) {
  var name = name || 'Alejandro';
  var age = age || 23;
  var country = country || 'MX';

  console.log(`My name is ${name} and i am ${age} years old. I'm from ${country}`);
}

newUser();

newUser('David', 90);

// ES6
function otherUser(name = 'Alejandro', age = 23, country = 'MX') {
  console.log(`My name is ${name} and i am ${age} years old. I'm from ${country}`);
}

otherUser();
otherUser('Juan');
```
![[Pasted image 20240110154339.png]]

## Destructuring assignment
```js
// Array Destructuring
let fruits = ['Apple', 'Bannana', 'Coco'];
let [a, b] = fruits;

console.log(a + " " + b);
// output: Apple Bannana

// Objects Destructuring
let user = { username: 'Alejo', age: 23 };

let { username, age } = user;

console.log(username + " " + age);
// outpot: Alejo 23
```
### Sintaxis Spread

**La sintaxis extendida o spread** **syntax** permite a un elemento iterable tal como un arreglo o cadena que permite ser expandido en lugares donde cero o más argumentos (para llamadas de función) o elementos (para [Array literales](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Grammar_and_types#literales_array)) son esperados, o a un objeto ser expandido en lugares donde cero o más pares de valores clave (para [literales Tipo Objeto](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Grammar_and_types#literales)) son esperados.
```js
// Spread Operator
let person = { name: 'Alejandro', age: 23 };
let country = 'MX';

let data = { ...person, name: 'Juan', country };
console.log(data);
// output: { name: 'Juan', age: 23, country: 'MX' }
```
### Parametros Rest
El último parámetro de una función se puede prefijar con `...`, lo que hará que todos los argumentos restantes (suministrados por el usuario) se coloquen dentro de un array de javascript "estándar".

Sólo el último parámetro puede ser un "parámetro rest".
```js

// rest
function sum(num, ...values) {
  console.log(values);
  console.log(num + values[0]);

  return num + values[1];
}

sum(1, 2, 3, 4);
// output: [ 2, 3, 4 ]
// 3
```
## Object Literals
Los literales de objetos son una de las estructuras de datos más utilizadas en JavaScript. Se utilizan para almacenar recopilaciones de datos, y pueden ser utilizados para representar estructuras de datos complejas como objetos, matrices, funciones e incluso expresiones regulares. Los literales de objetos también se utilizan para almacenar información sobre una instancia particular de un objeto, como su estado o comportamiento.

Los literales de objetos se escriben en forma de pares de valor de clave, donde cada clave es una cadena y cada valor puede ser cualquier tipo de datos JavaScript válido. Por ejemplo, el siguiente objeto literal almacena información sobre una persona:
```javascript
const person = {
  name: 'John Doe',
  age: 30,
  address: '123 Main Street'
};

function newUser(user, age, country) {
  return {
    user,
    age,
    country,
    id: uId
  }
}
```
## Promises
Una [`Promise`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Promise) (promesa en castellano) es un objeto que representa la terminación o el fracaso de una operación asíncrona. Dado que la mayoría de las personas consumen `promises` ya creadas, esta guía explicará primero cómo consumirlas, y luego cómo crearlas.
```js
const datos = [
  {
    id: 1,
    title: 'Iron Man',
    year: 2008
  },
  {
    id: 2,
    title: 'Spiderman: Homecoming',
    year: 2017
  },
  {
    id: 3,
    title: 'Avengers: EndGame',
    year: 2018
  }
]

// Crear la promesa
const getDatos = () => {
  return new Promise((resolve, reject) => {
    if (datos.length === 0) {
      reject(new Error('No existen datos'));
    }

    setTimeout(() => {
      resolve(datos);
    }, 1500);
  })
}

// Obtener data con Promises
getDatos()
  .then(response => console.log(response))
  .catch(err => console.error(err));

// Objeter data con async-await
(async () => {
  const datosPromise = await getDatos();
  console.log(datosPromise);
})()
```