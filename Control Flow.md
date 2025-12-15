
IF - podmienka:
- // Pouzivame ak chcem vykonat kod alebo nie
- if(*podmienka*) {
-   console.log(3)
- }
ELSE - ak podmienka je false
- // pouzivame s if alebo else if
- else {
-   console.log(5)
- }
ELSE IF - vetvenie kodu
- // Pouzivame ak chceme rozdelit kod nna viac ako 2 casti
- // ak je jedna podmienka v poradi true tak ostatne sa nepozeraju
- else if (*podmienka*) {
-   console.log("Daco")
- }
SWITCH - vetvenie kodu
- // pouzivame podobne ako else if
- switch(*hodnota*){
-   case 1:
-     console.log("je 1");
-     break;
-   case 2:
-     console.log("je 2");
-     break;
-   default:
-     console.log("Nie je nic");
-     break;
- }

WHILE - loop bez pomocnej premenny
- while(*podmienka*){
-   console.log("while")
- } 
DO WHILE - to iste ako while len podmienka je na konci
- do {
-   console.log("Do")
- } while(*podmienka*);
FOR - loop s pomocnou premennou
- for(*kod na zaciatku*; *podmienka*; *kod po kazdom loope*) {}
- for(*key* of *pole*) {}
- for(*value* in *pole*) {}