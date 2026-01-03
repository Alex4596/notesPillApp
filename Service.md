
Kod, ktory funguje ako 
balicek pre angular
napriklad ako suflik, ktory ma v sebe fieldy (state), methody (funkcie)
mozu byt pouzite v celej aplikacii na viacerych miestach pomocou Dependency Injection
- #### Cez Konstruktor v classe:
	- `constructor(private dacoService: DacoService) {}`
- #### Alebo cez funkciu v classe alebo v castiach kodu kde nieje classa:
	 - `private dacoSevice = inject(DacoService);`

### Cli kod: `ng g s <route>.service`
## Example:
``` TypeScript
@Injectable({
	providedIn: 'root'
})
export default class PillSevice {
	// Methoda, ktora vracia objekt Pill z vyplnenimi datami
	public createPill(name: string, description: string): Pill {
		return {
			id: Date.now,
			name,
			description,
			createdAt: new Date
		}
	}
	
}
```

#### Dokaze tak tiez riesit problem:
- komponenty su uzavrete, to im dodava bezpecnost ale niekedy chceme aby tieto casti kodu spolu komunikovali a dokazali zdielat informacie
#### Example: 
``` TypeScript
@Component({
	standalone: true,
	template: `<section>
		<p>{{ count() }}</p>
		<button (click)='increment()'>+</button>
	</section>`
})
export class Counter {
	public count = signal<number>(0);
	
	public increment(): void {
		this.count.update(c => c + 1);
	}
}
```
##### V tomto priklade ak pouzijeme Counter komponent 4 krat a stlacime tlacidlo + tak sa pripocita hodnota iba  v tom jednom komponente

#### Example 2:
``` TypeScript
@Component({
	standalone: true,
	template: `<section>
		<p>{{ counterService.count() }}</p>
		<button (click)='counterService.increment()'>+</button>
	</section>`
})
export class Counter {
	constructor(public counterService: CounterService) {}
}


// Service
@Injectable({
	providedIn: 'root'
})
export class CounterService {
	public count = signal<number>(0);
	
	public increment(): void {
		this.count.update(c => c + 1);
	}
}
```
#### Teraz kazdy Counter komponent zdiela ten isty state, cize ak klikneme na tlacidlo + teraz kazdy counter komponent sa refreshne a kazdy z nich bude ukazovat tu istu hodnotu a nezalezi, na ktory Counter komponent klikneme a vsetky meni hodnotu na tu istu 