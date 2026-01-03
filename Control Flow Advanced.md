

#### TRY - Pouziva sa ak je kod citlivy alebo moze spadnut:
#### CATCH - je potrebny ak sa pouziva s *try*
```JavaScript
try {
  daco();
} catch(error) {
  console.log(error);
}
```

#### FINALLY - je optional block of code, ktory moze byt pouzity pry *try catch*
- // kod sa vykona aj ked je error aj ked nieje
- // ak je vo funkcii return tak sa musi pockat na finally block aby sa vykonal
-  ```JavaScript
	try {
		daco();
	} catch(error) {
		console.log(error);
	} finally {
		daco2();
	}
	```
