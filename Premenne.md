var - stare, nepouziva sa, globalny scope / function scope
let - nova, scope based
- Variable Ghosting
- let x = 5
- if(){
-   let x = 6
-   console.log(x) // -> 6 uprednostnuje local scope
- }
- console.log(x) // -> 5  global scope
const - ako let nieje mozne reinicializovat

### pravidla:
- nesmu sa zacinat cislami
- camel case - dobryTextTuJe
- jedno slovo
