# Cascading Style Sheets

pouzivame na pridanie stylov 
menime vyzual stranky

## Pravidla:
- #### Cascading: 
	- Na poradi zavysi
- #### Specificity:
	- Styly, ktore su specificke napr. id prepise class a class prepise elementy
- Inheritance:
	- ak nema dany styl dedi ho z jeho rodicovskeho elementu

## Syntax:
```
<selector> {
	<property>: <value>;
}
```

- ### selector:
	- #### element: `div {}`
		- Pre vsetky div aplikuj styly
	- #### class: `.daco {}`
		- Pre vsetky elementy z classsou "daco" aplikuj styly
	- #### id: `#id {}`
		- Pre element z id "id" aplikuj styly
	- #### attribute: `input[type="text"] {}`
		- Pre vsetky elementy  input z atributom, ktoreho hodnota je "text"
	- #### pseudo class: `div:hover {}`
		- Styly sa aplikuju na vsetky div elementy len vtedy ak na nich podrzime misku
	- #### pseudo elements: `span::first-letter {}`
		- Styly sa aplikuju len na prve pismeno vsetkych span elementov
	- #### specificke styly:
		- `div p {}` : Vsetky p elementy, ktore sa nachadzaju v div elemente
		- `span > h3` : Vsetky h3 elementy, ktore su Priamy potomok (dieta) rodicovskeho elemnetu span

## Koncepty:
- ### Typography:
	- Uprava textu
- ### Coloring:
	- Uprava Farby
- ### Box Model:
	- Predstavuje ako je navrhnuty Kazdy viditelny element:
	- mame content: text/ine elementy
	- padding: ako daleko je okraj on contentu
	- border: okraj, da sa menit jeho rohy radius, farba, sirka, styl (Font)
	- margin: ako daleko su ostatne elementy od okraja
- ### Flex Box:
	- `display: flex;` - nastavy rozvrhnutie elementu podla flex boxu
	- `justify-content: <value>;` - ako elementy maju mat poziciu na main ose
		- center
		- start
		- end
		- space-around
		- space-evenly
		- space-between
	- `align-items: <value>;` - rozvrhnutie na cross ose, value su take iste ako pri prvom
	- `flex-direction: column;` - meni main os na vertikalnu a cross na horizontalnu a elementy sa snazia tlacit pod seba
- ### Grid Layout:
	- `display: grid;` - Nastavy rozvrhnutie na grid
	- `grid-template-row: <value>;` `grid-template-column: <value>;`
		- `<value>` - pocet hodnot znamena ako vela stalpcou alebo riadmkov sa vytvory a hodnoty samotne budu ake velke stlpce/riadky maju byt
		- `grid-template-column: 300px 200px 300px;
		- Vytvoria sa 3 stlpce: 1. = 300px, 2. = 200px, 3. = 300px
	- `repeat(<pocet>, <hodnota>)` - tato funkcia vytvory hodnoty podla \<hodnoty> a pocet hodnot je podla \<pocet>
	- `minmax(<min>, <max>)` - specialna funkcia, ktora sa vyskytuje len pri gride
		- vytvori sa velkost stlpca podla danych podmienok nemoze byt vecsie ako \<max> a ani mensie ako \<min>
- ### Variables:
	- mozeme zadefinovat globalne aj lokalne premenny:
	- ```
	  :root{
		  --farba: green;
	  }
	  ```
	- Potom mozeme zavolat premennu v cssku cez funkciu var():
	- ```
	  p {
		  color: var(--farba);
	  }
	  ```
- ## Queries
	- zacinaju sa z `@`
	- su specialne effekty css ka
	- napr. animacie, menenie, hodnot vlastnosti (stylov) pri inych velkostiach obrazovky
	- ```
	  // custom animacie:
	  @keyframes mymove {  0%   {top: 0px; left: 0px; background: red;}  
		  25%  {top: 0px; left: 100px; background: blue;}  
		  50%  {top: 100px; left: 100px; background: yellow;}  
		  75%  {top: 100px; left: 0px; background: green;}  
		  100% {top: 0px; left: 0px; background: red;}
	  }
	  div {
		  animation: mymove 5s infinite;
	  }
	  ```
	- #### Media Query: meni styl ak sa obrazovka zmensi nad velkost 800px
	- ```
	  // Zmena farby pozadia pri inej vecsej velkosti obrazovky
	  @media screen and (min-width: 800px) {
		  body {
			background-color: lavender;
		  }
	  }
	  ```