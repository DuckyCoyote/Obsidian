## Type e Interfaces
```typescript
type Cat = {  
  name: string;  
  legs: number;  
  isDogFriendly: boolean;  
}

interface Cat {  
  name: string;  
  legs: number;  
  isDogFriendly: boolean;  
}
```
### type
A un type no le podemos extender ni aumentar sus capacidades, pero con un type puedes **añadir tipos personalizados,** que habríamos creado previamente y que asignaríamos a nuestro nuevo type.
```typescript
type Cat = {  
    name: string;  
}
type DogFriendly = {  
    isDogFriendly: boolean;  
}
type CatAndDogFriendly = Cat & DogFriendly;
```
### interface
Una característica muy cool de las _interface_ es que **podemos extenderlas**. En el siguiente caso extenderíamos la interfaz Cat añadiendo el tipo de raza del gato en cuestión:
```typescript
interface Cat {  
 name: string;  
 legs: number;  
 isDogFriendly: boolean;  
}
interface Breed extends Cat {  
 breed: string;  
}
```
X