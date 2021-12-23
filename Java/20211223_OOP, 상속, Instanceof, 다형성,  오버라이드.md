# OOP (Object-Oriented Programming) 

OOP (Object-Oriented Programming)란 객체 지향적인 프로그래밍이다.

C언어와 같은 절차 지향적인 프로그래밍이 아닌 객체의 관점에서 프로그래밍을 한다는 것을 의미한다.

* OOP는 객체의 관점에서 프로그래밍 하는 것을 의미한다.
* OOP는 절차지향에 비해서 사람의 사고방식과 더 가깝다.
* OOP는 객체들의 유기적인 관계를 통해서 프로세스가 진행된다.
* 애플리케이션을 구성하는 요소들을 객체로 바라보고, 객체들을 유기적으로 연결하여 프로그래밍 하는 것을 말한다.


# 상속 (IInheritance) 
	* 부모(Parent/Super)가 자식(Child/Sub)에게 물려주는 행위
	* 클래스 구성요소 "변수"와 "메소드"만 상속
	* java.lang.Object : 모든 class 최상위

	* 필요성 : 코드의 재사용성 -> 개발 속도 향상
	* 제약 : 자식 = 부모 관계에서만 성립

참고 링크 
https://ko.wikipedia.org/wiki/%EC%83%81%EC%86%8D_(%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
http://www.tcpschool.com/java/java_inheritance_concept



# Instanceof 

## 객체의 타입 확인(instanceof)
 
 * 다형성으로 인한 타입과 객체 혼란 야기 가능
 * 문법 : 객체 instanceof 타입 // 왼쪽은 확인할 대상, 오른쪽은 왼쪽이 오른쪽으로 객체가 바뀔 수 있는지 확인
 * 결과 : boolean (true or false)
 
 
```
package step03.oop;

class A {} 	     // 부모 클래스 A
class B extends A {} // A를 상속 받는 B 클래스
class C extends A {} // A를 상속 받는 C 클래스

public class Instanceof {
	public static void main(String[] args) {
		A a1 = new A();
		A a2 = new B();
		A a3 = new C();
		
		System.out.println(a1 instanceof A); // true
		System.out.println(a1 instanceof B); // false
		System.out.println(a1 instanceof C); // false 
		
		System.out.println();
		
		System.out.println(a2 instanceof A); // true
		System.out.println(a2 instanceof B); // true
		System.out.println(a2 instanceof C); // false
		
		System.out.println();
		
		System.out.println(a3 instanceof A); // true
		System.out.println(a3 instanceof B); // false
		System.out.println(a3 instanceof C); // true
		
		B b1 = new B();
		System.out.println(b1 instanceof A); // true
		System.out.println(b1 instanceof B); // true
//		System.out.println(b1 instanceof C); // false 에러! 
	}
}
```

# 다형성 (Polymorphism)

## 상속 전제 조건
* 속성(데이터)들이 일치하는 존재 클래스(super/parent/부모)를 기반으로 하위 클래스 개발
* 문법
상위타입 변수 = 모든 자식 객체;
자식타입 변수 = (자식타입)상위타입변수;
		
public void method(Object v){
객체 타입이면 처리 가능한 로직의 재사용성 극대화 메소드
}
	  
## 다형성 필요성
```
		class A{} -> class A extends Object{}
		class B{} extends A{}
		class C{} extends B{}
		class D{} -> class D extends Object{}
		
		Object o = new Object(); O
		= new A(); O
		= new B(); O
		= new C(); O
		= new D(); O

		A o = new Object();  X
		= new A();  O
		= new B();  O
		= new C();  O
		= new D();  X
	
		B o = new Object(); X (부모가 자식타입으로 안됨)
		= new A();  X (부모가 자식타입으로 안됨)
		= new B();  O
		= new C();  O (자식 객체는 부모 타입으로 만들어 질 수 있다) 
		= new D();  X
		
		C o = new Object(); X (부모가 자식타입으로 안됨)
		= new A();  X
		= new B();  X
		= new C();  O
		= new D();  X (관계가 없음)
	
		D o = new Object(); X (부모가 자식타입으로 안됨)
		= new A(); X
		= new B(); X
		= new C(); X
		= new D(); O
```

# 오버로드(Overload)와 오버라이드(Override)의 차이점

## 오버로드(Overload)
메서드의 이름은 같고 파라메터의 갯수나 타입이 다른 함수를 정의하는 것을 의미한다.
(리턴값만을 다르게 갖는 오버로드는 작성 할 수 없다.)


## 오버라이드(Override)
상위 클래스의 메서드를 재정의 하는 것이다.
메서드의 이름은 물론 파라메터의 갯수나 타입도 동일해야 하며, 주로 상위 클래스의 동작을 상속받은 하위 클래스에서 변경하기 위해 사용된다.


오버로딩(Overloading)은 기존에 없던 새로운 메서드를 정의하는 것이고
오버라이딩(Overriding)은 상속 받은 메서드의 내용만 변경 하는 것이다.


출처: https://myspm.tistory.com/11

