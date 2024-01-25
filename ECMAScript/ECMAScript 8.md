## Object values y Object entries

```js
// Object values
const countries = { MX: 'Mexico', USA: 'United States', CO: 'Colombia' }
console.log(Object.values(countries));
// output: [ 'Mexico', 'United States', 'Colombia' ]

// Object entries
const countries = { MX: 'Mexico', USA: 'United States', CO: 'Colombia', CL: 'Chile' }
console.log(Object.entries(countries));
/* output: [
  [ 'MX', 'Mexico' ],
  [ 'USA', 'United States' ],
  [ 'CO', 'Colombia' ],
  [ 'CL', 'Chile' ]
]
*/
```
