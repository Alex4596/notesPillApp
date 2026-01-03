
## Promises:
- https://youtu.be/RvYYCGs45L4?si=3iHPtTmAaSUTQY3E
- https://youtu.be/Qx8Xx4djxqs?si=5YvNvC9XV-oMk5II
- // sluzi na vytvorenie kodu ktory neblokuje sposteni dalsieho kodu
- // Requesty, timer, atd..
- `new Promise((resolve, reject) => { resole("Sprava") });`
- // Co sa stane ak je resolve:
- `.then(msg => cosnoel.log(msg));`  
- // Co sa stane ak je reject:
- `.then(msg => cosnoel.log(msg), error => console.error(error)));`
- `.catch(error => console.error(error));`
- // Co sa stane ak je Resolve/Reject
- `.finally(msg => console.log(msg));`

## Async/Await
- https://youtu.be/H9nFFE5_VS4?si=imqXfiSsID-m9OdK
- // Funkcie z async automaticky returnuju Promise object
- ```JavaScript
  async function daco() {
	  console.log("Sprava");
	  // je asynchronna funkcia v asynku potrejujeme na nu pockat keywordom await
	  
	  const response = await fetch("http://localhost:4200/pill");
  }
  ```
- https://youtu.be/vn3tm0quoqE?si=LCdbBLprhbOf1rxf