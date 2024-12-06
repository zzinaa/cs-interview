# OOP

## OOP의 5대 원칙

SOLID   
S:Single Responsibilty
O:Open Closed Principle
L:Liskov Substitution Principle
I:Interface Segregation Principle
D:Dependency Inversion Principle


**단일 책임 원칙 (SRP:Single Responsibility Principle)**

하나의 클래스는 하나의 원칙만 가져야 한다.  
단일 책임 원칙을 잘 지키면, 변경이 필요할 때 수정할 대상이 명확해진다. 단일 책임원칙의 장점은 시스템이 커질수록 유용하다. 서로 많은 의존성을 가진 상황에서 변경 요청이 오면 딱 한가지만 수정하면 되기 때문이다.  


**개방 폐쇠의 원칙 (OCP:Open Closed Principle)**
자신의 확장에는 열려있고 주변의 변화에는 닫혀있어야 한다.
기존의 코드를 변경하지 않고 새로운 기능을 추가할 수 있어야한다.

ex) JDBC 인터페이스 
JDBC인터페이스를 통해 DB를 바꿀 필요가 있을 때, Connectoin을 설정하는 부분만 해당 드라이버로 수정해 주면 DB를 교체할 수 있다.

**리스코프 치환 원칙(LSP:Liskov Substitution Principle)**
자식 클래스는 부모 클래스의 역할을 모두 할 수 있어야 한다.
쉽게 말해 부모 Class가 들어갈 자리에 자식 Class를 넣어도 잘 구동이 되어야 한다.

**인터페이스 분리 원칙(ISP:Interface Segregatoin Principle)**
하나의 일반적인 인터페이스보다는 여러개의 구체적인 인터페이스를 사용해야 한다.

**의존 역전 원칙(DIP:Dependency Inversion Principle)**
의존관계를 맺을 때 변화하기 쉬운것보다, 거의 변화하지 않는 것에 의존해야 한다.
