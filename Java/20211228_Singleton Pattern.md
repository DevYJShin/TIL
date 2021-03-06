# Singleton Pattern

## 정의

> 소프트웨어 디자인 패턴에서 싱글턴 패턴(Singleton pattern)을 따르는 클래스는, 
> 생성자가 여러 차례 호출되더라도 실제로 생성되는 객체는 하나이고 최초 생성 이후에 호출된 생성자는 최초의 생성자가 생성한 객체를 리턴한다. 
> 이와 같은 디자인 유형을 싱글턴 패턴이라고 한다. 주로 공통된 객체를 여러개 생성해서 사용하는 DBCP(DataBase Connection Pool)와 같은 상황에서 많이 사용된다.


## 사용 및 예제

```
    package kail.study.java.design.single;
    
    public class Printer {
    	private static Printer printer = null;
    
    	private Printer(){}
    
    	public static Printer getInstance() {
    		if(printer == null) {
    			printer = new Printer();
    		}
    		return printer;
    	}
    
    	public void print(String input) {
    		System.out.println(input);
    	}
    }
```

## 문제점

* Multi-Thread 환경에서 안전하지 않음
* 여러 쓰레드가 공유되고 있는 상황에서는 아래의 블럭에서 조건문이 동시에 두번 돌 수 있기때문에 하나의 인스턴스가 아닌 여러개의 인스턴스가 발생 할 위험이 있음
* 인스턴스가 상태를 유지해야하는 상황에서 싱글톤은 더 고려해야할 점이 많음

## 해결방법

멀티쓰레드 환경에서 싱글톤의 문제를 해결 할 수 있는 방법은 두가지가 있다.

* 정적 변수에 인스턴스를 만들어 바로 초기화 하는 방법
* 인스턴스를 만드는 메서드에 동기화하는 방법

## 싱글톤의 문제
* 싱글톤은 프로그램 전체에서 하나의 객체만을 공통으로 사용하고 있기 때문에 각 객체간의 결합도가 높아지고 변경에 유연하게 대처할 수 없다. 
싱글톤 객체가 변경되면 이를 참조하고 있는 모든 값들이 변경되어야 하기 때문에 멀티쓰레드 환경에서 대처가 어느정도 가능하지만 고려해야 할 요소가 많아 사용이 어렵고, 
프로그램 전반에 걸쳐서 필요한 부분에만 사용한다면 장점이 있다. 하지만 그 포인트를 잡기가 어렵다.

## 결론
적절한 형태로 싱글톤을 활용하면 좋지만 남용하게 될 여지가 많다. 

* 멀티 쓰레드 환경에서의 싱글톤
Synchronized를 통해 관리하면 되며 다양한 변화에 대응하기 위해 인터페이스의 형태로 관리하면 좋다.

* 단일쓰레드환경에서 싱글톤
정적 클래스의 형태로 사용하면 된다. (클래스 로딩단계에서 바로 초기화 되도록)
물론 이 경우에서도 테스트를 위한 모의객체를 만들고 혹은 다른 목적으로 사용한다면 멀티쓰레드 환경에서 싱글톤을 사용하듯이 사용하면 된다.

참고 : https://velog.io/@kyle/%EC%9E%90%EB%B0%94-%EC%8B%B1%EA%B8%80%ED%86%A4-%ED%8C%A8%ED%84%B4-Singleton-Pattern
https://elfinlas.github.io/2019/09/23/java-singleton/
