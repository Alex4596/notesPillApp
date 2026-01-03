https://youtu.be/X4URoPEFxmE?si=lak6l_aYMEa8GErP&t=215

#### IF - podmienka:
- // Pouzivame ak chcem vykonat kod alebo nie
- ```JavaScript
  if(podmienka) {
	 console.log(3)
  }
  ```
#### ELSE - ak podmienka je false
- // pouzivame s if alebo else if
- ```JavaScript
	else {
		console.log(5)
	}
  ```
#### ELSE IF - vetvenie kodu
- // Pouzivame ak chceme rozdelit kod nna viac ako 2 casti
- // ak je jedna podmienka v poradi true tak ostatne sa nepozeraju
- ```JavaScript
	else if (podmienka) {
		console.log("Daco") 
	}
  ```
#### SWITCH - vetvenie kodu
- // pouzivame podobne ako else if
- ```JavaScript
  switch(hodnota){
		case 1:
			console.log("je 1");
			break;
		case 2:
			console.log("je 2");
			break;
		default:
			console.log("Nie je nic");
			break;
	}
  ```
#### WHILE - loop bez pomocnej premenny
- ```JavaScript
  while(podmienka) {
	  console.log("while")
  } 
  ```
#### DO WHILE - to iste ako while len podmienka je na konci
- ```JavaScript
  do {
	  console.log("Do")
  } while(podmienka);
  ```
#### FOR - loop s pomocnou premennou
- `for(kod na zaciatku; podmienka; kod po kazdom loope) {}`
- `for(key of pole) { pole[key]; }`
- `for(value in pole) { value; }`