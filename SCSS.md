podobne ako [[CSS]]
 ale je to super set [[CSS]]ka

# Koncepty:
- ## Variables:
	- V scss mozeme pouzivat klasicek premenne alebo specialne scss premenne:
		- ```
		  $farba: green;
		  
		  p {
			  color: $farba;
		  }
		  ```
- ## Nesting:
	- v css kody su dlhe preto lebo niekedy sa specifikuje ake styly maju patrit na konktretny element:
	- vieme tiez zapisat kratsie aj efektivnejsie:
		- ```
		  // Scss
		  form {
			  backgroud-color: green;
			  
			  div {
				  background-color: red;
				  
				  input {
					  border-color: yellow;
				  }
			  }
		  }
		  
		  // Css
		  form {
			  backgroud-color: green;
		  }
		  form div {
			  background-color: red;
		  }  
		  form input {
			  border-color: yellow;
		  }
		  ```
- ## Mixins: 
	- Podobne ako funkcie v programiovacych jazykoch, ale toto replikuje existujuce styly aby sa dali opakovane pouzivat
	- ```
	  @mixin greenAndRed() {
		  color: red;
		  background-color: green;
	  }
	  
	  p {
		  @include greenAndRed;
	  }
	  ```