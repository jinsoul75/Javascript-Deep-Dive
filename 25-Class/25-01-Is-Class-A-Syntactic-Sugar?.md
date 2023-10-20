# 25-01-Is-Class-A-Syntactic-Sugar?

- JS는 프로토타입 기반 객체지향 언어이다.
    - 특징 : 클래스가 필요 없다.
    - ES5까지는 생성자 함수와 프토로타입을 통해 객체 지향 언어의 **상속 구현 가능** 했다.
    
    ```jsx
    //ES5 생성자 함수
    var Animal = (function() {
    //생성자 함수
    function Animal(name) {
    this.name = name;
    )
    
    //프로토타입 매서드
    Person.prototype.sayHello = function(){
    	console.log('Hello '+ this.name + '!');
    };
    
    //생성자 함수 반환
    return Animal
    }());
    
    //인스턴스 생성
    var myDog = new Animal('YangE');
    myDog.sayHello(); // Hello YangE!
    ```
    
- 기존 개발자들은 프로토타입보다 클래스 기반 언어에 익숙해서 위 같이 코드를 작성하는게 힘들었다고 한다.
- ES6에서 도입된 클래스는 클래스 기반 객체지향 프로그래밍에 익숙한 개발자가
익숙하게 느낄만한 객체 생성 메커니즘을 따른다. (배려미쳤따)
- 클래스는 사실 클래스기반 객체지향 모델처럼 보이는 프로토타입기반 객체지향 모델이다.
    - 이렇게 그럴싸 하게 보인다고 해서 `문법적 설탕` 이라고 한다.

- 클래스 vs 생성자 함수