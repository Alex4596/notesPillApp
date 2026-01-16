#### su nadizajnovane ako TypeScriptovske classy s Decoratorom @Component(), ktore ma ako parameter objekt, ktory prebera
meta data:
- template: html
- style: css/scss/sass/less
- standalone: true

## cli kod:
`ng g c <route/name>`

### state:
- field classy sa da pouzit ako premenna v html
### functionality:
- methody classy sa daju pouzit ako funkcie v html

## Koncepty: 
- citatelnost:
 - ked rozdelime UI user interface na viac casti stane sa kod prehladnejsi a citatelnejsi
- performance: 
 - rozdelenim komponentov docielime ze ak sa state zmeni v nejakom komponente tak sa refreshne ten konkretny komponent
- security:
 - kazda kopia komponentu ma vlastny state, ktory je vnutorne v komponente, teda ine kpmponenty k nemu nemaju pristup
- reuseability:
 - ak zadefinujeme komponent tak ho vieme opakovane pouzivat na viacerich miestsch v aplikacii
- spliting:
 - kod mozeme rozdelit na mensie problemi pomocou komponentov

#### Input / Output:
- ##### Input:
	- Nastavenie hodnot
	- ``` TypeScript
	  // Definicia:
	  class Component {
		  public name = input("Anonymous");
		  public surrName = input.required();
	  }
	  ```
	- ``` Html
	  <!-- Volanie: -->
	  <app-component
		  [name]="'Foo'"
		  [surrName]="'Bar'"
	  ></app-component>
	  ```
- ##### Output:
	- Vyuzitie eventu
	- ```TypeScript
	  // Definicia:
	  class Component {
		  public recieve = output<void>();
		  
		  ngOnInit() {
			  this.recieve.emit();
		  }
	  }
	  ```
	- ```Html
	  <!-- Volanie: -->
	  <app-component
		  (recieve)="log()"
	  ></app-component>
	  ```