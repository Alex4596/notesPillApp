#### var - stare, nepouziva sa, globalny scope / function scope
### let - nova, scope based
- ###### Variable Ghosting
- ```JavaScript
	let x = 5;
	  
	if(podmienka) {
		let x = 6;
		console.log(x); // -> 6 uprednostnuje local scope
	}
	
	console.log(x) // -> 5  global scope
  ```
### const - ako let nieje mozne reinicializovat

https://youtu.be/UgEaJBz3bjY?si=DDxVWk9ro-o3En0c

##### Spread Operator:
https://youtu.be/Ojps2FjHt5A?si=Da4fiBDAQeypqjA5
### pravidla:
- nesmu sa zacinat cislami
- camel case - dobryTextTuJe
- jedno slovo
