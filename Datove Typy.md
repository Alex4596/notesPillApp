## Primitivne:
string - text, index (text\[0]), + concat;
number - artimetiku (+, - , * ,  /), binary, octan, hex, int, float, negative,  2000  = 2e3;
BigInt - velke int cisla;
boolean - (true, false), >, <, == , === , !=, !== , <=, >=/ &&, ||, !,  if (podmienka);
undefined - (undefined) ( let prem = fun(); ), defaultna hodnota js;
null - (null), nic;

## Neprimitivne:
Object - ( { name:  "Dakto", hobbys: \["Futball", "PRogramovanie"] } ) - properties, obj.name, 
	obj\["name"]
Array: - ( \[1, 2, 3] ) \[0], property = length = 3
- for(let i = 0; i < array.length; i++)
- for(let x of array) - key = index
- for(let x in array) - value 

Truly:
- string - *
- number - *
- Object - { name: null }
- Array - \[0]
Falsy:
- string - "" - prazdny string
- number - 0, NaN (Not a Number +> pretypovanie "x" => cislo)
- undefined
- null
- Object - { }
- Array - \[ ]
