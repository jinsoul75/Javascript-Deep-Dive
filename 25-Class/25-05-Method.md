# 25-05-Method

- 클래스 몸체에는 0개 이상의 메소드만 선언할 수 있다. ⇒ 선언해도 되고 안해도 된다는 소리 아닌가?
- 클래스 몸체에  선언할 수 있는 메서드는
    1. contructor
    2. 프로토타입 매서드
    3. 정적 메서드

# 25-05-01 constructor

- constructor는 인스턴스를 생성하고 초기화 하기 위한 특수한 메서드
- constructor는 이름 변경 불가능

```jsx
class Animal {
	//생성자
	constructor(name){
		//인스턴스 생성 및 초기화
		this.name = name;
	}
}
```

- 클래스는 인스턴스를 생성하기 위한 생성자 함수

```jsx
console.log(typeof Animal); //function
console.dir(Animal); // class Person >prototype >constructor: class Animal
```

- 클래스 내부를 들여다보면 클래스는 평가되어 함수 객체가된다.
- 클래스도 객체 고유의 프로퍼티를 가지고 있다.
- 함수와 동일하게 프로토타입으로 연결되어있으며 자신의 스코프 체인을 형성한다.

- **모든 함수 객체가 가지고 있는 prototype 프로퍼티**가 가리키는
프로토타입 객체의 constructor 프로퍼티는 자기자신을 가리키고 있다. (위 코드블록)
which means 클래스가 인스턴스를 생성하는 생성자 함수라는것을 의미.
⇒ `new` 연산자와 함께 호출하면 클래스는 인스턴스를 생성한다.

- 클래스가 생성한 인스턴스의 내부를 살펴보자

```jsx
//인스턴스 생성
const myDog = new Animal('Yang');
console.log(myDog);
//Person {name: 'Yang'} 
//name: 'Yang' << 추가되었다!
//V__proto__
//> constructor: class Animal
//>__proto__
```

- Animal 클래스의 constructor 내부에서 this에 추가한 name 프로퍼티가
클래스가 생성한 인스턴스의 프로퍼티로 추가되었다.
- 생성자 함수와 마찬가지로 **costructor 내부에서 this에 추가한 프로퍼티**(name)는
**인스턴스 프로퍼티**가 된다.
- constuctor 내부의 this는 생성자 함수와 마찬가지로 **클래스가 생성한 인스턴스**를 가리킨다.