#### html: https://youtu.be/ok-plXXHlWw?si=aXcLfY9-XNGIFD6q
## Ui frame work na vytavranie frontendovych aplikacii
https://youtu.be/Ata9cSC2WpM?si=LUOpOCYhbLKdFZ-K

#### Package instalacia (CLI): `npm i -g @angular/cli`
#### Cli kody:
- ##### Vytovrenie Projektu: `ng new <Nazov>`
- ##### Generovanie: `ng generate <Generovana vec> <nazov/cesta>`
- ##### Instalacia Angularovskych Package:  `ng add <Package>`
- ##### Verzia: `ng version`
- ##### Spustenie aplikacie v dev mode: `ng serve`
- ##### Kompilovanie aplikacie: `ng build`

## Koncepty:
- #### Signal:
	- `public state = signal<Type>(/* pociatocna hodnota */)`
	- *state*: nazov fieldy/premenny
	- *Type*: Optional, je typ akeho moze byt state
	- *pociatocna hodnota*: hodnota, ktora je nastavena ako prva pri spusteni programu
- #### Life Cycle Hooks:
	- su specialne funkcie/methody, ktore sa vykonavaju za urcitych podmienok
	- `onInit` interface ma v sebe deklaraciu methody `ngOnInit: void`
		- Ktora, sluzi na spustenie kodu ked sa dana vec (komponent, service) nacita
	- `onDestroy` interface, deklaracia `ngOnDestroy: void`
		- Sluzi na vykonanie kodu ked sa (komponent) maze, napr. prepneme na inu stranku
		- vecsinou sa pouziva na  uvolnenie pamate ked mame pripojene nejake pripojenie, ktore, moze zatazovat pamat
	- `effect(() => { console.log(count()); })`
		- funkcia, kotra berie callBack funkciu ako parameter
		- tento presny priklad Vypise hodnotu count signalu stale ked sa jeho hodnota zmeni


[[TypeScript]]
[[Component]]
[[SCSS]]
[[Service]]
[[RxJS]]
[[HttpClient]]
[[Interceptors]]
[[Router]]
[[AngularMaterial]]