```yaml
# init
ng new angular-tour-of-heroes
cd angular-tour-of-heroes
ng serve --open
```

```yaml
# ������Ʈ gen
ng generate component hero-detail

```

```yaml
# https://v9.angular.io/tutorial/toh-pt2
  <li *ngFor="let hero of heroes"
    [class.selected]="hero === selectedHero" # class.Ŭ������ = "����" 
    (click)="onSelect(hero)">
    <span class="badge">{{hero.id}}</span> {{hero.name}}
  </li>
```


```yaml
# Create a feature component



```