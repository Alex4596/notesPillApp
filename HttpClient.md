
## Je alternativa Fetch funkcie prisposobena pre angular

### Tradicna Fetch funkcia:
- ```
  let jsonData = null;
  fetch("http:localhost:8080/pill")
	  .then(response => response.json())
	  .then(data => jsonData = data)
	  .catch(error => console.log(error));
  ```

#### Funkcia fetch pouziva http protokol na posielanie requestov 
- Navratova hodnota je Promise Objekt teda bud pouzijeme .then() methodu alebo async/await syntax 
- A ked chceme specifikovat aku http methodu chceme  poslat mozeme pridat objekt: `fetch("http:localhost:8080/pill", { method: "POST" })`
- Ak chceme spracovat data musime pouzit methodu `.json()`

### HttpClient:
```
const http = inject(HttpClient);
const jsonData = signal<any>(null);

http.post("http:localhost:8080/pill").subscribe({
	next: data => jsonData.set(data),
	error: error => console.log(error)
});
```

#### HttpClient je nahrada za fetch funkciu
- Navratova hodnota je RxJs Observable
- Http methoda sa meni z methodu HttpClientu
- ak chceme spracovat data tak su uz spracovane v spravnej forme lne su v Observable to znamena ze ich vieme konzumovat pomocou methody subscribe, to ktorej mozeme dat Observer Objekt aby spracoval data
- ##### Benefity:
	- Ekosystem z RxJS Kniznicou
	- Jednoduche spracovatelne data a ich uprava 
	- Nemusime riesit async a promise Observable sa o to postara pretoze moze byt asynchronny
	- Daja sa pouzit [[Interceptors]]