# Typescript
- Typescript añade tipado estático. Se transpila a Javascript.

- Las propiedades por lo general siempre privadas. Si hay que devolver su valor, mejor a través de un método.

- Everyday types:
	- The primitives: string, number and boolean
	- Arrays: `Array<string>`
	- Any
	- Union Type: `let aTextOrNumber: number|string = 5;`
    - Generic types: `function identity<Type>(arg: Type): Type { return arg; }`

- Interfaz: "el contrato que tenemos que cumplir"
```typescript
interface Animal {
  type: string;
  name?: string;
}
class Cat implements Animal {
    constructor(public type: string) {}
    ...
}
```
```typescript
class Pokemon {
	constructor(private nombre: string) {}
}
```

```typescript
/* Encadenamiento opcional u optional chaining (?.)
El operador ?. funciona de manera similar a el operador de encadenamiento .,
excepto que en lugar de causar un error si una referencia es casi-nula (null o undefined),
la expresión hace una evaluación de circuito corto con un valor de retorno de undefined.
Puedes saber más en: https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-7.html#optional-chaining */
const getName = (animal?: Animal) => animal?.name;
```

## "Tell, don't ask"
A una clase le tengo que pedir el nombre (`getName()`), no preguntarle por el nombre (`this.name`).
