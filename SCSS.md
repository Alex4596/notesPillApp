podobne ako [[CSS]]
 ale je to super set [[CSS]]ka
 https://youtu.be/akDIJa0AP5c?si=1snMk7ir7-fyyn3Y

# Koncepty:
- ## Variables:
	- V scss mozeme pouzivat klasicek premenne alebo specialne scss premenne:
		- ``` SCSS
		  $farba: green;
		  
		  p {
			  color: $farba;
		  }
		  ```
- ## Nesting:
	- v css kody su dlhe preto lebo niekedy sa specifikuje ake styly maju patrit na konktretny element:
	- vieme tiez zapisat kratsie aj efektivnejsie:
		- ``` SCSS
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
	- ``` SCSS
	  @mixin greenAndRed {
		  color: red;
		  background-color: green;
	  }
	  
	  p {
		  @include greenAndRed;
	  }
	  ```
	- `@if podmienka {}`
	- `@else {}`
	- ``` SCSS
	  // Array and Loop
	  $sizes: 40px, 50px, 80px
	  @each $size in $sizes {
		  .icon-#{$size} {
			  font-size: $size;
		  }
	  }
	  ```
	- #### Function:
	- ``` SCSS
	  @function sum($numbers) {
		  @each $number in $numbers {
			  $sum: $sum + $number;
		  }
		  
		  @return $sum;
	  }
	  ```