# Typescript
- Typescript añade tipado estático. Se transpila a Javascript.

- Las propiedades por lo general siempre privadas. Si hay que devolver su valor, mejor a través de un método.

- Everyday types:
	- The primitives: string, number and boolean
	- Arrays: `Array<string>`
	- Any
	- Union Type: `let aTextOrNumber: number|string = 5;`
	
- Interfaz: "el contrato que tenemos que cumplir"
```typescript
class Cat implements Animal 
```
```typescript
class Pokemon {
	constructor(private nombre: string) {}
}
```

## "Tell, don't ask"
A una clase le tengo que pedir el nombre (`getName()`), no preguntarle por el nombre (`this.name`).

- [ ] #to-do: Tipos genéricos