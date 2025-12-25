
### su template
blueprint
je to navrh ako ma nieco vyzerat a fungovat
snazime sa pouzivat pre preddefinovanie kodu
aby sme menej pisali
ale musime viac naplanovat

```
class Car {
	static daco = 5;
	constructor(brand, model) {
		this.brand = brand;
		this.model = model;
	}
	drive() {
		console.log("Driving...")
	}
}
```


## Volanie:

// Instancia classy = object
`const car = new Car("Ford', Mustang);`
// volanie methody na object
`car.drive()`
// volanie statickeho fieldu nie z objectu ale z classy
`console.log(Car.daco);`

`car = object premenna`
`Car = class`

### Keyword
- #### this:
	- robi referenciu na aktualnu referenciu classy alebo na dany objekt
	- ```
		class Car {
			static daco = 5;
			constructor(brand, model) {
				this.brand = brand;
				this.model = model;
			}
			displayInfo() {
				console.log(this.brand + ": " + this.model);
			} 
		}
		
		const car1 = new Car("Renault", "Clio");
		car1.displayInfo();
		// OUTPUT: "Renault: Clio"
		// "This" v tomto pripade referuje na objekt ulozeny v premenne car1 
		
		const car2 = new Car("Porsche", "963");
		car2.displayInfo();
		// OUTPUT: "Porsche: 963" 
		// "This" v tomto pripade referuje na objekt ulozeny v premenne car2
	  ```
- #### static:
	- fieldy a methody ktore patria class, nie objektu;
	- // bez instancie
	- static *field* = *value*;
	- `Class.field;`
	- `Class.method();`
- #### #:
	- field, ktory sa da pouzit len v ramci classi
	- neda sa zavolat niekde inde
	- `#count`
- #### constructor:
	- specialna methoda classy
	- spusti sa pri vytvarani instancie
	- zvycajne sa pouziva na zapisanie hodnot do objektu
	- constructor(*params*) {*body*}
- #### getter:
	- methoda ktora sa vola ako field ktora vracia hodnotu
	- zvycajne sa ta hodnota = hodnote fieldu
	- teda robi operaciu read
	- ```
		class Car {
		  name;
		  get name() {
			  return this.name;
		  }
		}
		
		// Volanie
		const car1 = new Car();
		console.log(car1.name);  
		```
- #### setter:
	- podobne ako getter
	- ale namiesto read 
	- robi write
	- ```
	  	class Car {
		  name;
		  set name(meno) {
			  this.name = meno;
		  }
		}
		
		// Volanie
		const car1 = new Car();
		car1.name = "Ford";
	  ```
- #### new:
	- vytvara instanciu
	- alokuje pamat
	- class => objekt
	- `const car1 = new Car()`
- #### extends:
	- inheritance / dedenie
	- rozsirenie existujucej class
	- class Van je trieda, ktora pouziva vlastnosti a methody z triedy Car
	- napr:
	- ``` 
	  class Van extends Car {
		  constructor(brand, model, weight) {
			  super(brand, model);
			  this.weight = weight;
		  }
	  }
	  ```
- #### super:
	- Je referencia na Parent class teda Van class
	- podobne ako "this"
### TypeScript Keyword:
- #### public:
	- znamena ze field alebo methoda sa daju pouzit/zavolat mimo classy
	- `public count: number;`
- #### private:
	- tento field alebo methoda sa da pouzit len v ramci classy
- #### protected:
	- sa Sprava podobne ako private 
	- ale ak sa rozhodneme ze classa bude dedit, tento field alebo methoda bude viditelna v ramci classy ale aj v ramci classy, ktora ju zdedila

### Koncepty:
- #### Inheritance:
	- Rozsirenie classy pomocou `extends`
	- napr. mame Human class
	- chceme vytvorit SuperHuman class
	- vlastnosti, ktore ma Human bude mat aj SuperHuman takze ju iba rozsirime nepotrebujeme pisat ten isty kod
- #### Composition:
	- Je technika pri objektovom programovani, kedy napr. mame Human class a Monster class a chceme aby mali nejake vlastnosti alebo funkcie spolocne napr. funkcia utok a obrana
	- mozeme mat viac tychto vlastnosti
	- ```
	  class BasicCombat {
		  constructor(dmg, def) {
			  this.dmg = dmg;
			  this.def = def;
		  }
		  
		  attack(hp) {
			  return hp - this.dmg;
		  }
		  
		  defence(damage) {
			  return damage - this.def;
		  }
	  }
	  
	  class Monster {
		  constructor(name, hp, dmg, def) {
			  this.name = name;
			  this.hp = hp;
			  this.combatProperties = new BasicCombat(dmg, def);
		  }
		  
		  attack(hp) {
			  return this.combatProperties.attack(hp);
		  }
		  
		  defence(hp) {
			  return this.combatProperties.defence(hp);
		  }
		  
		  takeDamage(damage) {
			this.hp -= damage;
		  }
	  }
	  
	  class Human {
		  constructor(name, hp, dmg, def) {
			  this.name = name;
			  this.hp = hp;
			  this.combatProperties = new BasicCombat(dmg, def);
		  }
		  
		  attack(hp) {
			  return this.combatProperties.attack(hp);
		  }
		  
		  defence(hp) {
			  return this.combatProperties.defence(hp);
		  }
		  
		  takeDamage(damage) {
			this.hp -= damage;
		  }
	  }
	  
	  
	  
	  // Realny Kod, v ktorom sa vsetko deje:
	  const human1 = new Human("Dezo", 100, 3, 1);
	  const monster1 = new Monster("Rado", 110, 2, 2);
	  
	  
	  human1.takeDamage(
		  human1.defence(
			  monster1.attack(human1.hp)
		  )
	  );
	  
	  // monster1 ubera utoci na hp human1 a human1 obranuje a dostava poskodenie
	  ```
- #### Overload:
	- Mozeme mat viac menej parametrov a podla toho urcit ako sa bude methoda menit
	- methoda attack ma viac parametrov ak zadame len jeden zavola sa 1. methoda
	- ak dame 2 parametre zavola sa 2 methoda
	- ```
	  class BasicCombat {
		  constructor(dmg, def) {
			  this.dmg = dmg;
			  this.def = def;
		  }
		  
		  attack(hp) {
			  return hp - this.dmg;
		  }
		  
		  attack(hp, bonusovyDef) {
			  const novyHp = this.attack(hp) - this.bonusovyDef;
			  
			  if (novyHp < 0) return 0;
			  
			  return novyHp;
		  }
	  }
	  ```
- #### Override:
	- v tejto situacii pouzivame existujucu methodu attack ktoru prepisujeme aby odpovedala na taku situaciu aku potrebujeme
	- ```
	   class BasicCombat {
		  constructor(dmg, def) {
			  this.dmg = dmg;
			  this.def = def;
		  }
		  
		  attack(hp) {
			  return hp - this.dmg;
		  }
		  
		  defence(damage) {
			  return damage - this.def;
		  }
	  }
	  
	  class EnhancedCombat extends BasicCombat{
		  constructor(dmg, def, bonus) {
			  this.bonus = bonus;
			  super(dmg, def);
		  }
		  
		  attack(hp) {
			  return super.attack(hp) + this.bonus;
		  }
	  } 
	  ```
- #### Polymorphism:
	- je ked sa meni z dedenia methoda
### TypeScript Koncepty:
- #### Abstraction:
	- ak pridame pred classu keyword `abstract`
	- hovorime ze class nema mat instanciu
	- takato trieda sa pouzije pri dedeni
	- akysi blueprint pre blueprint
	- ```
		  abstract class Vehicle {
			  ...
		  }
	
		  class Car extends Vehicle {
				...
			}
	  ```
- #### Implementation:
	- keyword `implements`
	- vyuziva `interface` a jeho deklaracie
	- tvori pravidla pre classu
	- napr.
	- ```
		  interface CounterRules {
			  count: number;
			  increment(): void;
		  } 
		  
		  class Counter implements CounterRules {
			  public count: number; // Toto musi exitovat
			  
			  public increment(): void { // Toto tiex musi byt zadefinovane
				  this.count++;
			  }
			  
			  public decrement(): void { // NEmusi byt zadefinovane
				  this.count--;
			  }
		  }
	  ```


