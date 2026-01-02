https://youtu.be/zQnBQ4tB3ZA?si=Krwimcv6lS5mDREK
# Pridelovanie Typov:
- ## Premenna:
	- `let prem: string;`
- ## Funkcia:
	- `function fun(): string {}`


# Basic Types:
- string
- number
- boolean
- null
- undefined
- void - pre funkciu
# Value Types:
- Namiesto typov vieme vlozit aj samotne hodnoty
- string -> "DAco" // Teraz je typ limitovany len ta toto "DAco"
- number -> 1 

# Union Types:
- jeden typ moze byt zostaveny z viac typov
- `: 50 | 10` // Teraz hodnota moze nadobudnut 50 alebo 10
- mozeme prideli kolko | chceme
- `: 10 | 20 | 30 | 40 | 50` 
# Object Types
- ak vieme ze potrebijeme objekt ta mozeme pouzit
- `: object` // toto je neefektivne lebo typescript nevie o aky objekt iide
- zmenime ho na presnejsiu verziu
- `: { name: string, age: number, isStudent: boolean }`
- ak mame vytvorenu class vieme pouzit ju namiesto tohto zapisu
- `: Person`
# Special Types:
- `: any` // TypeScript nepozera na typ
- `: unknown` // TypeScript nepozna typ a nedovoli nam ho priradit k premennej z typom napr `: string`
- `: never` // Typ, ku ktoremu by nemalo dvojst referuje vecsinou na errory
# Array:
- Dlhsi zapis `: Array<string>`
- kratsi zapis `: string[]`
- tiez vieme urobit tuple:
- `: [number, string, boolean]`
- `const graph: [x: number, y: number] = [55.2, 41.3];`
# Type Keyword:
- namiesto toho aby sme dookola vypisovali ten isty typ
- vieme ho zadefinovat
- `type nullableString = string | null;
# Interface: 
- Ak chceme dat objekt ako typ do type keywordu
- je lepsie a ma viac vyhod ak ho zadefinujeme ako interface
- ```
  interface Person {
	  name: string;
	  age: number;
	  isStudent: boolean;
  }
  ```
  - Interface sa da vyuzit aj na implementovanie pri definovani classy
  - aby sme zaistili ze urcita methoda bude zadefinovana v classe

# Casting:
- pretypovanie:
- ak chceme nieco pretypovat za definiciu toho dame AS keyword
# Intersection Types:
- Zvycajne pouzivane pri kombinacii objektov
- `type PersonWithGender = Person & { gender: string }`
# Generics & Diamond Operator:
- ked definujeme funkciu alebo classu
- vyme pridat generics
- ```
  function daco<T>(x: T): T {
	  return x;
  }
  ```
  - V tejto funkciii ak je zavolana takto `const prem = daco(5)`
  - je datovy typ T je flexibilny a teda vsetko co je T musi mat taky isty datovy typ
  - `const prem = daco<number>(5)`
  - Aj je v Diamantovom operatore zadefinovany typ explicitne plati ze T = number