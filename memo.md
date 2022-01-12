```yaml
# init
ng new angular-tour-of-heroes
cd angular-tour-of-heroes
ng serve --open
```

```yaml
# 콤포넌트 gen
ng generate component hero-detail

```

```yaml
# Add services
# https://poiemaweb.com/angular-service

서비스와 의존성 주입...안녕하세요 반ㅏ습니다 안녕하세요 반ㅏ스
디자인 패턴은 덤으로..ㅎㅎ



```


```yaml
서비스란?
- 콤포넌트가 할일 이외에 역할을 수행해주는 별개 프로그램
- 서비스는 의존성 주입(Dependency Injection)이 가능한 클래스이다.

@Injectable 데코레이터란?
- 자신의 아래에 정의된 클래스가 의존성 주입이 가능한(injectable) 클래스임을 나타낸다.
- 

@ providedIn 프로퍼티 란?
- ‘root’를 설정하면 루트 인젝터에게 서비스를 제공하도록 지시
- 애플리케이션의 모든 구성요소에 싱글턴 전역 서비스를 주입할 수 있도록 한다.


싱글턴이란?
- 객체의 인스턴스가 오직 1개만 생성되는 패턴을 의미한다. 
- 이미 생성된 인스턴스를 사용하기 떄문에, 메모리 , 속도 측면 이점
- 클래스간에 데이터 공유가 쉽다
- 동시 접근할때 , 동시접근 문제 발생가능하므로 유의



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
    // 서비스의 인스턴스를 직접 생성한다.
    this.greetingService = new GreetingService();
  }

  sayHi() {
    // 서비스의 사용
    this.greeting = this.greetingService.sayHi();
  }
}
```


