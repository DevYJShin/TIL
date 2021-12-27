# final

```
public class Ex01Abstarct {

	int age = 30;
	final String name = "Son";  // final 키워드는 상수를 이용할 때 사용함, 변하지 않는 값 지정할 때 사용
	final double PI = 3.14; 
	final int MAX_NUMBER = 99;
	
//	void print() {
//		System.out.println("출력");
//	}
	
	final void print() { // final이 되면 상속이 되더라도 값이 바뀔 수 없음
		System.out.println("출력");
	}
	
	
	public static void main(String[] args) {
		// Final
		Ex01Abstarct ex01 = new Ex01Abstarct();
		ex01.age = 31;
//		ex01.PI = 2.2;
//		ex01.name = "java";
		ex01.print();
```

참고 블로그 : 
https://advenoh.tistory.com/13

# abstract

```
abstract class A {
	abstract void help(); // abstract 형태를 고정해주는 역할이며, 클래스 상속에는 영향을 미치지 않음 
						  // abstract를 사용하게 되면 {} 코드 블럭을 사용하면 안된다.
}

class B extends A {
	void help() {
		System.out.println("B : help 메소드" );
	}
}

class C extends A {
	void help() {
		System.out.println("C : help 메소드" );
	}
}
```

추상클래스(Abstract Class)는 인터페이스의 역할도 하면서 실제 메소드도 가지고 있는 자바의 돌연변이 같은 클래스이다. 
혹자는 추상클래스는 인터페이스로 대체하는것이 좋은 디자인이라고도 얘기한다.

참고 : 
https://wikidocs.net/219

# Interface

	- 객체의 사용방법을 정의
	- 상속, 다중상속 가능
	- 상위 interface는 동시 여러개 구현 가능
	- 제약조건 : 하위 클래스에서는 미완성 메소드 재정의
	- 문법
		[public] interface 인터페이스명{...}
		
	- 구성요소
		1. 상수
			[public static final] 타입 상수명;
		
		2. 메소드
			[public abstract] 리턴타입 메소드명(...);
			abstract : 추상, 미완성
			{} 코드블럭 미존재
      
   ex) public class AI2022Java extends Printer implements Connector, Javaable{ // 인터페이스는 implements 키워드로 사용이 가능하다.
   
```
   	public static void main(String[] args) {
		AI2022Java ai2022Java = new AI2022Java(); // 2022Java 객체 생성
		ai2022Java.connectComputer();
		
//		Printable print = new Printable(); // 객체 생성 불가 : Interface 내에 미완성된 메소드가 있기 때문에
		Printable print2 = new AI18Printer(); // Interface 가져다가 사용하는 다른 클래스 객체는 사용이 가능함 (상속처럼 사용이 되는 것처럼 보임)
		
	}
```

# Exception

>프로그램을 만들다 보면 수없이 많은 오류가 발생한다. 
>물론 오류가 발생하는 이유는 프로그램이 오동작을 하지 않기 하기 위한 자바의 배려이다. 
>하지만 때로는 이러한 오류를 무시하고 싶을 때도 있고, 
>오류가 날 때 그에 맞는 적절한 처리를 하고 싶을 때도 있다. 
>이에 자바는 try ... catch, throw 구문을 이용해 오류를 처리 한다.


* 사용자 혹은 개발자의 잘못으로 발생하는 프로그램 오류, 처리 가능한 에러
	- 에러 발생시 지속적인 서비스 제공을 위함
	- 종류
		- 일반 예외 : 컴파일 계열(ClassNotFoundException, ...)
			- java.lang.RuntimeException외의 모든 예외 클래스
			- 제약조건 : try~catch 블록으로 처리 필수
			
		- 실행 예외 : 런타임 계열(NullPointerExeption, ClassCastException, ...)
			- java.lang.RuntimeException 상속받는 모든 예외 클래스
			- try~catch는 옵션
			
	- 문법
		- 예외 발생가능성 존재하는 library 사용시 문법
		- 문법 1
				try{								
					예외 발생 가능성 존재 수행 코드;	
				}catch(발생 가능성 예외 Exception변수){
					예외 처리 수행 코드;
				}
			
		- 문법 2
				try{
					예외 발생 가능성 존재 수행 코드;	
				}catch(발생 가능성 예외 Exception변수){
					예외 처리 수행 코드;
				}finally{							
					예외발생 여부와 무관, 무조건 실행되는 블럭
					**자원 반환 로직
					(ex DB접속 해제, IO 자원 해제, ..)
				}
			
		- 개발 상황에 따른 예외 발생 문법 
		    - body{}영역에 
				throw new 생성자명([..]); 구현
			
			- 메소드 선언구에 발생 가능성 예외 알림 표기	
				반환타입 메소드명([...]) throws~Exception[, ~Exception2] {}
		
		- 사용자 정의 예외 클래스
		- 상황에 맞는 클래스 이름 자체가 메세지가 되기 때문
			- 컴파일 계열
				java.lang.Exception 상속
				생성자 두개 다중정의
					- 기본 생성자
					- String 매개변수 존재 생성자
		
			- 런타입 계열
				java.lang.RuntimeException 상속
				생성자 두개 다중정의
				
				
참고 : https://wikidocs.net/229
