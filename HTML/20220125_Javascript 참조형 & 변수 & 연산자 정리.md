# 

first child
last child

next sibling
previous sibling


class

.class명{}

class="class명"

부트 스트랩

cdn ( content derevery network) ? 링크를 걸어서 쓰는 방식

css pseudo-classes 중요 

:checked

:first-child

:not(selector) 

:nth-child(n)



window.onload=function(){
		console.log("head태그안에서 p태그:", document.getElementById("userid"));
	};


window.onload=function(){};
=> 실행 시점은 html의 dom tree가 모두 생성된 후에 실행

# 자바스크립트 데이터형

5가지 기본 데이터형  정리

NaN (Not a Number)



# 자바스크립트 참조형

json - 모든 프로그램 언어에 표준화된 포맷
java script object notation

킹왕짱임

top - 표준화된 포맷 !!

# 자바스크립트 변수

var 변수명 = 값;
var x(변수명); -> 아직 초기화 안됨, undefined가 저장됨
x = 10;
var y(변수명) = null; -> y 변수 값이 없음
commision  ( salesman이 

//1. 기본형
	 console.log("수치(정수):", 20);
	 console.log("수치(실수):", 3.14);
	 
	 console.log("문자(하나의 문자):", 'A', "A");
	 console.log("문자(문자열):", 'ABC', "ABC");
	 
	 console.log("논리데이터:", true, false);
	 console.log("undefined(초기화되지 않는상태)", undefined);
	 console.log("null(값이 없음):", null);
	 console.log("NaN(Not a Number):", NaN);



//ES6
     class Person{
    	 //생성자
    	 constructor(name,age){
			this.name = name;
			this.age = age;
		}
     }
     
     var p = new Person();


# 자바스크립트 변수


data type이 없음 

var 변수명;
let 변수명;

변수 scope 정리

블록 scope : 블록 안에서 갇힘 / 블록 밖에서 사용 불가 
함수 scope : 함수에서만 갇힘 / for & if는 사용 가능

# 데이터 자동 형변환

const

값 변경 안됨


# 연산자 

## 동등 비교 연산자

== equal 연산자로서 값만 비교한다.
=== identical 연산자로서 값과 데이터 타입까지 비교한다.


## 논리연산자, 증감연산자, 3항 연산자 스킵 

spread 연산자 -> vue.js에서 할 예정
