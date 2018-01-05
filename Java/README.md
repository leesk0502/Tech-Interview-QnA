[Back to Contents](../README.md)
# Java Interview QnA
자바 면접 질문과 답

### Q1. Java의 장단점
* 장점
  * JVM을 이용한 플랫폼 독립
  * 객체지향 프로그래밍 완벽 지원
  * GC 사용으로 Memory Leak 걱정없이 Heap 메모리를 사용한다.
  * 다양한 API
    * 일반적인 Application을 위한 J2SE JDK
    * Enterprise 프로그램을 위한 J2EE JDK
    * 모바일 프로그램을 위한 J2ME JDk
    * 그 외 다양한 Open Source
  * 포인터 연산 지원하지 않아 안정성 향상
  * 구현과 Interface 분리
  * 엄격한 Type ( boolean이 Number type과 호환되지 않음 )
* 단점
  * JVM 사용으로 코드 -> 바이트 코드 -> 기계 코드의 과정을 거치기에 느리다.
  * OS의 System API를 바로 사용하지 않고 JVM을 통해 사용하므로 다른 언어에 비해 느리다.

### Q2. 객체지향 프로그래밍(Object-Oriented Programming)
* 프로그램을 어떻게 설계해야 하는지에 대한 개념이자 방법론
* 프로그램을 수많은 '객체'라는 기본 단위로 나누고 객체들의 상호작용으로 서술하는 방식
* 코드의 재사용성을 높이고 효율적인 유지보수가 가능해짐

### Q3. 객체지향 4가지 요소
* 캡슐화
  * 코드 수정 없이 재활용 하는 것이 목적
  * 은닉화 - 클래스 속성들을 private 설정해서 밖에서 건들지 못하도록 함.
* 상속
  * 부모의 특성을 그대로 이어 받고 필요에 따라 기능을 재정의 할 수 있음.
* 다형성
  * 하나의 변수명, 함수명이 상황에 따라 다른 의미로 해석 될 수 있다.
* 추상화
  * 객체들의 공통적인 특징(속성과 기능)을 뽑아내는 것.

### Q4. 클래스(Class)와 객체(Object)
* 클래스는 객체를 생성하기 위한 설계도
* 객체는 속성과 기능의 집합

### Q5. Java의 접근제어자(Access Modifier)
*    public : 접근을 제어하지 않음
*   default : 같은 패키지 내에서만 접근 가능
* protected : 같은 패키지 혹은 다른 패키지의 자식 클래스에서 접근 가능
*   private : 같은 클래스 내에서만 접근 가능

### Q6. 오버라이딩(Overriding) vs 오버로딩(Overloading)
* Overriding : 부모의 기능을 자식 클래스에서 재정의하는 것
* Overloading : 같은 이름의 메소드들이 매개변수의 유형과 개수가 다르도록 하는 기술

### Q7. interface vs abstract
* abstract
  * 하나 이상의 추상 메소드를 가지고 있음
  * 상속에 큰 의미를 두어 extends 키워드를 이용하여 사용.
  * 다중 상속의 모호성 때문에 하나만 상속함.
  * 자식 클래스는 반드시 추상 함수를 재정의해서 사용해야 함.
* interface
  * 모든 메소드가 추상 메소드이어야 함.
  * 기능의 재정의에 큰 의미를 두고 있음.
  * implements 키워드를 이용하여 구현. 다중 상속 가능.
  * 함수의 껍데기만 가지고 구현을 강제함으로써 구현 객체의 같은 동작을 보장.

### Q8. 기본형 정수 vs Wrapper 클래스
* 기본 자료형으로 표현된 데이터를 참조 자료형으로 만들어야 하는 경우 사용
  * 매개변수로 객체가 요구 될 때.
  * 기본형 값이 아닌 객체로 저장해야 할 때.
  * 객체간의 비교가 필요할 때.

### Q9. Collection 종류와 언제 써야 효과적인지
* List
  * 순차적인 데이터를 저장하며 중복을 허용
  * ArrayList : 랜덤 index에 접근하는 것에 유리, 동기화 보장하지 않음
  * LinkedList : 삽입, 삭제에 유리
  * Stack : 스택 자료구조
  * Vector : Java 2 이전 버전에서 사용, 동기화 보장
* Set
  * 순서를 보장하지 않으며 중복을 허용하지 않음
  * HashSet
  * TreeSet : 데이터가 정렬된 상태로 저장됨.
* Map
  * Key와 Value로 이루어짐.
  * 순서를 보장하지 않으며 key의 중복만 허용하지 않음.
  * HashMap : 동기화를 보장하지 않음
  * TreeMap : 데이터가 정렬된 상태로 저장됨.
  * HashTable : 동기화 보장
  * Properties : 설정 파일로부터 값을 읽을 때 많이 사용됨.

### Q10. JVM(Java Virtual Machine)의 메모리 구조

### Q11. GC(Garbage Collection)에 대하여

### Q12. final vs static

### Q13. 객체의 직렬화(Serialization)

### Q14. String vs StringBuffer vs StringBuilder

### Q15. 기본 자료형(Privitive data type) vs 참조 자료형(Reference data type)

### Q16. JIT(Just In Time) 컴파일러에 대하여

### Q17. Java 8 변경사항


