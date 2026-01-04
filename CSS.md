# Cascading Style Sheets

pouzivame na pridanie stylov 
menime vyzual stranky
https://youtu.be/OEV8gMkCHXQ?si=aZ_cRQtlUkdKsX0s

## Pravidla:
- #### Cascading: 
	- Na poradi zavysi
- #### Specificity:
	- Styly, ktore su specificke napr. id prepise class a class prepise elementy
- Inheritance:
	- ak nema dany styl dedi ho z jeho rodicovskeho elementu

## Syntax:
``` CSS
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
		- https://youtu.be/kpXKwDGtjGE?si=6qbv2DM0s0TQNGGI
	- #### pseudo elements: `span::first-letter {}`
		- Styly sa aplikuju len na prve pismeno vsetkych span elementov
		- https://youtu.be/e1KpKBHJOrA?si=-13-w-o9gWhPv7g4
	- #### specificke styly:
		- `div p {}` : Vsetky p elementy, ktore sa nachadzaju v div elemente
		- `span > h3` : Vsetky h3 elementy, ktore su Priamy potomok (dieta) rodicovskeho elemnetu span

## Koncepty:
- ### Typography:
	- Uprava textu
	- https://youtu.be/9-oefwZ6Z74?si=Z4btT9CiLuxOcgFq
- ### Coloring:
	- Uprava Farby
	- Rozne zapisi:
	- `green`
	- `rgb(0, 50, 255)` / `rgba()`
	- `hsl(200, 20%, 40%)` / `hsla()`
	- https://youtu.be/vvPklRN0Tco?si=uk_LOT2RQ15_dJsf
- ### Box Model:
	- Predstavuje ako je navrhnuty Kazdy viditelny element:
	- mame content: text/ine elementy
	- padding: ako daleko je okraj on contentu
	- border: okraj, da sa menit jeho rohy radius, farba, sirka, styl (Font)
	- margin: ako daleko su ostatne elementy od okraja
	- ![[Pasted image 20260102141834.png]]
	- https://youtu.be/Sm1ORyc2Qao?si=MCbfiHM55yTb6H_n
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
	- https://youtu.be/K74l26pE4YA?si=OviqdDXgmKu3gKVF
	- https://youtu.be/rPlwsRJZ_EM?si=EkdsCo2zvy2DBr0C
- ### Grid Layout:
	- `display: grid;` - Nastavy rozvrhnutie na grid
	- `grid-template-row: <value>;` `grid-template-column: <value>;`
		- `<value>` - pocet hodnot znamena ako vela stalpcou alebo riadmkov sa vytvory a hodnoty samotne budu ake velke stlpce/riadky maju byt
		- `grid-template-column: 300px 200px 300px;
		- Vytvoria sa 3 stlpce: 1. = 300px, 2. = 200px, 3. = 300px
	- `repeat(<pocet>, <hodnota>)` - tato funkcia vytvory hodnoty podla \<hodnoty> a pocet hodnot je podla \<pocet>
	- `minmax(<min>, <max>)` - specialna funkcia, ktora sa vyskytuje len pri gride
		- vytvori sa velkost stlpca podla danych podmienok nemoze byt vecsie ako \<max> a ani mensie ako \<min>
	- https://youtu.be/uuOXPWCh-6o?si=px3Cg3FVRS5pO4_A
	- https://youtu.be/E3wWl725tMQ?si=De_HetF4YU-sEv-9
- ### Variables:
	- mozeme zadefinovat globalne aj lokalne premenny:
	- ```CSS
	  :root{
		  --farba: green;
	  }
	  ```
	- Potom mozeme zavolat premennu v cssku cez funkciu var():
	- ``` CSS
	  p {
		  color: var(--farba);
	  }
	  ```
	- https://youtu.be/NtRmIp4eMjs?si=AKA-jChpxyL2qlCz
- ## Queries
	- zacinaju sa z `@`
	- su specialne effekty css ka
	- napr. animacie, menenie, hodnot vlastnosti (stylov) pri inych velkostiach obrazovky
	- https://youtu.be/HZHHBwzmJLk?si=NmUd2h1SM5XvCEnL
	- ```CSS
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
	- ```CSS
	  // Zmena farby pozadia pri inej vecsej velkosti obrazovky
	  @media screen and (min-width: 800px) {
		  body {
			background-color: lavender;
		  }
	  }
	  ```
	- https://youtu.be/n9yI6fjkrfE?si=M-x6GYt-ouJXXCzc