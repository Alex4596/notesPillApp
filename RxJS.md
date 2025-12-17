- Reactive JavaScript kniznica
- Stream of Data

# KONCEPTY:
- ## Observable:
	- Objekt ktory emituje data
	- je zakladom celeho RxJS
	- ```
	  const observable = new Observable((x) => {
		  x.next("Data1");
		  x.next("Data2")
	  })
	  ```
- ## Subscription:
	- je Forma alebo methoda, cez ktoru vieme spracovat data
	- ```
	  observable.subscribe(data => {
		  console.log(data);
	  })
	  ```
- ## Observer:
	- je objekt, ktory je vlozeny do subcribu
	- urcuje ako sa spracuju rozne vysledky dat
	- ```
	  observable.subscribe({
		  next(data) {
			  console.log(data);
		  },
		  error(err) {
			  console.error(err);
		  },
		  completed() {
			  console.log("Kompletne!");
		  }
		})
	  ```
- ## Pipe:
	- methoda Observeblu
	- do ktorej sa daj dat operatory
	- stream of data pipeline
	- data prejdu cez operatory, ktore z nimi mozu nieco zpravit
	- ```
	  observable.pipe();
	  ```
- ## Operators:
	- su operatory ktore mozu vytvarat observably napr.
		- `const observable = of(1, 2, 3);`
	- alebo su to operatry v pipeline:
	- map(): ktora funguje podobne ako .map() pri poliach
	- filter(): podobne ako pri poliach
	- tap(): nemeni hodnotu ale ju len pouzije
	- atd...
	- ```
	  observable.pipe(
		map(x => x * 2)	  
	  ).subscribe(data => console.log(data));
	  ```