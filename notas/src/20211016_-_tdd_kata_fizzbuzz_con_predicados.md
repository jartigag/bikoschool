# Predicados y reglas
[`git clone -b predicates-rules-openclose https://github.com/540/fizzbuzz-ts.git`](https://github.com/540/fizzbuzz-ts/tree/predicates-rules-openclose)

**Predicado**: función que devuelve un booleano

Si tenemos una torre de `if`s, será mejor convertirlo a una tabla (= conjunto de reglas), porque será más mantenible.

```javascript
import { otherwise, and, contains, isDivisibleBy, or } from './predicate';
import { Rule } from './rule';

export const createFizzBuzz = () => {
    const ruleSet: Rule[] = [
        {predicate: and(isDivisibleBy(3), isDivisibleBy(5)), trans: () => 'FizzBuzz'},
        {predicate: ..., trans: () => ...},
        ...
        {predicate: otherwise, trans: n => n.toString()},
    ];

    return fizzBuzz(ruleSet);
};

export const fizzBuzz = (ruleSet: Rule[]) => (n: number) =>
    ruleSet.find(rule => rule.predicate(n))!.trans(n);
    /*                                     ^ no permite que el find devuelva null,
	                        aunque en este caso tenemos el otherwise en las reglas 
							así que no haría falta.
    */
```

```javascript
export interface Rule {
    predicate: Predicate
    trans: (n: number) => string
}
```

```javascript
export type Predicate = (n: number) => boolean
```
