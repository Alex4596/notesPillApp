
### su template

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

## Volanie:

// Instancia classy = object
const car = new Car("Ford', Mustang);
// volanie methody na object
car.drive()
// volanie statickeho fieldu nie z objectu ale z classy
console.log(Car.daco);

car = object premenna
Car = class

### Keyword
- #### static:
	- fieldy a methody ktore patria class, nie objektu;
	- // bez instancie
	- static *field* = *value*;
	- `Class.field;`
	- `Class.method();`
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




