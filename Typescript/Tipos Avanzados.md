## Iniciar un proyecto 
```zsh
npm i typescript --save-dev
#
npx tsc --init
```
#### Cambiar el directorio de transpilacion en tsconfig.json
```json
"outDir": "./dist",
```
#### Transpilar con Typescript Compiler
```zsh
npx tsc --watch
```
#### ts-node
```zsh
 # Locally in your project.  
 npm install -D typescript  
 npm install -D ts-node  
 # Or globally with TypeScript.  
 npm install -g typescript  
 npm install -g ts-node  
 # Depending on configuration, you may also need these  
 npm install -D tslib @types/node   

 # Ejecutar ts-node para ver la salida directamente
 npx ts-node <file dir>
```
## Enums
Define un conjunto de variables.
Enums permiten a un desarrollador definir un conjunto de constantes nombradas. El uso de enums puede facilitar la documentación de la intención, o crear un conjunto de casos distintos. TypeScript proporciona enums numéricos y basados en cadenas.
```typescript
enum ROLES {
  ADMIN = "admin",
  SELLER = "seller",
  CUSTOMER = "customer"
}

type User = {
  username: string;
  role: ROLES;
}

const alejoUser: User = {
  username: "Alejo",
  role: ROLES.ADMIN
}
```
## Tuplas
Una tupla en [TypeScript](http://www.manualweb.net/tutorial-typescript/) es un array de elementos que están tipados. De esta manera cada vez que haya que insertar un elemento se validará que dicho elemento coincida con el tipo de dato establecido en la tupla.
```typescript
// Ninguna posicion esta tipada en los arrays convencionales
const prices: (number | string)[] = [1, 2, 3, 4, 'asdf'];
prices.push(1);
prices.push('2');


// Typar las pocisiones de un array
const user: [string, number] = ['Alejo', 15]

// Destructuring de una tupla
user = ['Alejo', 21];
const [username, age] = user;
console.log(username); // output: Alejo
```
## Unknown type
Este tipo de dato es la mejora de `any`, ya que nos da la flexibilidad que en ocasiones queremos pero sin apagar por completo el análisis de código estático. Unknown nos fuerza a hacer una verificación de tipo.
```typescript
let anyVar: any;
anyVar = 1;
anyVar = true;
anyVar = [1, 2];
anyVar = { name: 'Alejo', age: 13 };

let unknowVar: unknown;
unknowVar = true;
unknowVar = 1;
unknowVar = 'Alejo';
unknowVar = [];

if (typeof unknowVar === 'string') {
  unknowVar.toUpperCase();
}

if (typeof unknowVar === 'boolean') {
  let isNewV2: boolean = unknowVar;
}

const parse = (str: string): unknown => {
  return JSON.parse(str);
}
```
## Never Type
El tipo `never` representa el tipo de valores que nunca ocurren. Por ejemplo, `never` es retornado por la expresión de una función que siempre lanza una excepción o alguna que nunca retorna valores.

El tipo `never` es un subtipo, que es asignable a cualquier tipo, sin embargo ningún tipo es un subtipo de `never`, un tipo `never` solo puede ser asignado con el valor `never`. Incluso `any` no puede ser asignado a `never`.
```ts
// esta funcion no tiene un punto final ya que dispara una excepcion
function error(mensaje: string): never {
    throw new Error(mensaje);
}

// esta funcion no tiene un punto final ya que dispara un error
function fallo(): never {
    return error("Reportar fallo");
}

// esta funcion no finaliza ya que posee un loop infinito
function loopInfinito(): never {
    while (true) {}
}
```
## Optional Types y Nullish Coalescing
Las propiedades de objeto opcionales son propiedades que pueden contener un valor o no estar definidas. En TypeScript hay algunas formas de declarar una propiedad de objeto opcional.
**Los valores Opcionales deben ser declarados al final.**
```ts
export const createProduct = (
  id: string | number,
  isNew?: boolean,
  stock?: number,
) => {
  return {
    id,
    stock: stock ?? 10,
    isNew: isNew ?? true,
  }
}

// 0 === false
// '' === false
// false === false
// Nullish coalescing: ??

const p1 = createProduct(1, false, 12);
console.log(p1);

const p2 = createProduct(1, true);
console.log(p2);
```
## Default params
Es una forma de asignar valores por defecto si estos no son pasados en el llamado de la funcion.
```ts
export const createProduct = (
  id: string | number,
  isNew: boolean = true, // <-- Default Param
  stock: number = 100,   // <-- Default Param
) => {
  return {
    id,
    stock: stock,
    isNew: isNew,
  }
}

// 0 === false
// '' === false
// false === false
// Nullish coalescing: ??

const p1 = createProduct(1, false, 12);
console.log(p1);

const p2 = createProduct(1, true);
console.log(p2);
```
## REST Params
Los parametros REST nos permiten enviar un numero indefinido de parametros a una funcion sin que esta arroje un errror por estar definida con un numero determinado de parametros.
```ts
// Forma comun de enviar varios parametros usando arrays
export const checkRoleV2 = (roles: string[]) => {
  if (roles.includes(currentUser.role)) {
    return true;
  }
  return false;
}

const rta3 = checkRoleV2([ROLES.ADMIN, ROLES.CUSTOMER]);
console.log('CheckAdminRole', rta3);

//Forma REST de enviar parametros a una funcion
export const checkRoleV3 = (...roles: string[]) => {
  if (roles.includes(currentUser.role)) {
    return true;
  }
  return false;
}

const rta4 = checkRoleV3(ROLES.ADMIN, ROLES.CUSTOMER, ROLES.SELLER);
console.log('CheckAdminRole', rta4);
```
## Interfaces
Las interfaces, en las palabras más simples, describen la estructura del objeto, lo que significa que describe cómo debería verse el objeto. En **Mecanografiado**, podemos trabajar con “**Interfaces**”. En TypeScript, una interfaz solo contiene la definición de métodos y propiedades, no su implementación. Es la funcionalidad de la clase que realiza la conexión entre la interfaz proporcionando la conexión con todos los parámetros de la interfaz.
Una interface a diferencia de los types se puede extender y agregar mas atributos
```ts
// El type solo define un unico atributo
type Sizes = 'S' | 'M' | 'L' | 'XL';
type userId = string | number

// Con interface no podemos definir solo una atributo, debemos definir una estructura completa
interface Product {
  id: string | number;
  title: string;
  createdAt: Date;
  stock: number;
  size?: Sizes;
}

const product: Product[] = [];

product.push({
  id: 1,
  title: 'T-shirt',
  createdAt: new Date(),
  stock: 90,
  size: 'S'
});
```