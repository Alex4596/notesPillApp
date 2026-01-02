
## Sposob ako prepinat medzi podstrankami bez Refreshu celej stranky

### RouterOutlet komponent:
- specialny komponent, ktory funguje ako placeholder pre ine komponenty, ktore su napisane v Routes objekte
- `<router-outlet></router-outlet>` - Komponent v html
### Router Objekt:
- ### Path:
	- `path: 'home'`
	- vyjadrujje ze nieco sa ma stat na route /home
- ### Component:
	- `component: Couter`
	- nacita Counter komponent namiesto router-outlet
- ### Children: 
	- ```
	  { 
		  path: 'pill',
		  component: Pill,
		  children: [
			{
				path: '',
				component: Counter
			},
			{
				path:'idk',
				component: Daco
			}
		]
	  }
	  ```
	- Na Ceste /pill sa nacita komponent Pill a komponent Counter
	- na Ceste /pill/idk sa nacita Pill a Daco

### Route:
	- specialny Directive sa napise pri napr. anchor elemente 
	- `<a routerLink="/pill">Klikni a prejdes na pill page</a>`
	- ak stalcime element prepene nas na /pill route, kde sa nacitaju elementy podla routera