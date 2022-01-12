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
# Add services
# https://poiemaweb.com/angular-service

���񽺿� ������ ����...�ȳ��ϼ��� �ݤ����ϴ� �ȳ��ϼ��� �ݤ���
������ ������ ������..����



```


```yaml
���񽺶�?
- ������Ʈ�� ���� �̿ܿ� ������ �������ִ� ���� ���α׷�
- ���񽺴� ������ ����(Dependency Injection)�� ������ Ŭ�����̴�.

@Injectable ���ڷ����Ͷ�?
- �ڽ��� �Ʒ��� ���ǵ� Ŭ������ ������ ������ ������(injectable) Ŭ�������� ��Ÿ����.
- 

@ providedIn ������Ƽ ��?
- ��root���� �����ϸ� ��Ʈ �����Ϳ��� ���񽺸� �����ϵ��� ����
- ���ø����̼��� ��� ������ҿ� �̱��� ���� ���񽺸� ������ �� �ֵ��� �Ѵ�.


�̱����̶�?
- ��ü�� �ν��Ͻ��� ���� 1���� �����Ǵ� ������ �ǹ��Ѵ�. 
- �̹� ������ �ν��Ͻ��� ����ϱ� ������, �޸� , �ӵ� ���� ����
- Ŭ�������� ������ ������ ����
- ���� �����Ҷ� , �������� ���� �߻������ϹǷ� ����



```



```ts
// greeting.service.ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class GreetingService {
  constructor() { }
}
```

```ts
// greeting.service.ts
import { Injectable } from '@angular/core';

@Injectable()
export class GreetingService {
  sayHi() { return 'Hi!'; }
}
```

```ts
// app.component.ts
import { Component } from '@angular/core';
import { GreetingService } from './greeting.service';

@Component({
  selector: 'app-root',
  template: `
    <button (click)="sayHi()">Say Hi</button>
    <p>{{ greeting }}</p>
  `
})
export class AppComponent {
  greeting: string;
  greetingService: GreetingService;

  constructor() {
    // ������ �ν��Ͻ��� ���� �����Ѵ�.
    this.greetingService = new GreetingService();
  }

  sayHi() {
    // ������ ���
    this.greeting = this.greetingService.sayHi();
  }
}
```


