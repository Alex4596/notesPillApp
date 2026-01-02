
## Promises:
- https://youtu.be/RvYYCGs45L4?si=3iHPtTmAaSUTQY3E
- // sluzi na vytvorenie kodu ktory neblokuje sposteni dalsieho kodu
- // Requesty, timer, atd..
- new Promise((resolve, reject) => { resole("Sprava") })
- // Co sa stane ak je resolve:
- .then(msg => cosnoel.log(msg))  
- // Co sa stane ak je reject:
- .then(msg => cosnoel.log(msg), error => console.error(error)))
- .catch(error => console.error(error))
- // Co sa stane ak je Resolve/Reject
- .finally(msg => console.log(msg))

## Async/Await
- // Funkcie z async automaticky returnuju Promise object
- async function daco() {
-   console.log("Sprava");
- 
-   // je asynchronna funkcia v asynku potrejujeme na nu pockat keywordom await
-   const response = await fetch("http:\//localhost:4200");
- }
- https://youtu.be/vn3tm0quoqE?si=LCdbBLprhbOf1rxf