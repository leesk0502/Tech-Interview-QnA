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
* Class Loader : java compiler에 의해 변환된 바이트 코드(.class)를 Runtime Data Area에 적재하는 기능
* Execution Engine : Class Loader에 의해 적재된 바이트 코드를 명령어 단위로 읽어서 실행
* Garbage Collector : 메모리 관리 수행
* Runtime Data Area : 운영체제에 의해 할당 받는 메모리 영역. Class Loader에서 준비한 데이터들을 보관하는 장소
  * Method (Static ) Area : JVM이 읽어들인 클래스와 인터페이스에 대한 Runtime Constant Pool, 멤버 변수, 클래스 변수(Static 변수), 생성자와 메소드를 저장하는 공간
    * Runtime Constant Pool
      * 클래스와 인터페이스 상수, 메소드와 필드에 대한 모든 레퍼런스를 저장
      * 이 공간을 통해 해당 메소드나 필드의 실제 메모리 상 주소를 찾아 참조
    * Method Area/Runtime Constant Pool 사용 기간 및 스레드 공유 범위 
      * JVM 시작시 생성, 프로그램 종료 시까지 유지
      * GC 대상
      * 모든 스레드에서 공유
  * Stack Area
    * 각 스레드마다 하나씩 존재, 스레드 시작시 할당
    * 메소드 정보, 지역변수, 매개변수, 연산 중 발생하는 임시 데이터 저장
    * 기본 타입 변수는 스택 영역에 직접 값을 가짐
    * 참조 타입 변수는 힙 영역이나 메소드 영역의 객체 주소를 가짐
  * PC Register
    * 현재 수행 중인 JVM 명령 주소를 가짐
  * Native Method Stack Area
    * 자바 외 언어로 작성된 네이티브 코드를 위한 Stack
    * JNI(Java Native Interface)를 통해 호출되는 C/C++ 등의 코드 수행을 위한 Stack
    * 네이티브 메소드의 매개변수, 지역변수 등을 바이트 코드로 저장
  * Head Area
    * JVM이 관리하는 프로그램 상에서 데이터 저장을 위해 런타임 시 동적으로 할당하여 사용하는 영역
    * new 연산자로 생성된 객체 or 배열을 저장
    * 여기에 생성된 객체와 배열은 스택 영역의 변수나 다른 객체의 필드에서 참조
    * 참조하는 변수나 필드가 없으면 GC의 대상이 됨
    * 힙 영역의 사용기간 및 스레드 공유 범위
      * 객체가 더이상 사용되지 않거나 명시적 null 선언 시 GC 대상
      * 모든 스레드에서 공유
    * Young Generation
      * 객체가 생성되자마자 저장되는 공간
      * 시간이 지나 우선순위가 낮아지면 Old 영역으로 옮겨짐
      * 이 영역에서 객체가 사라질 때 Minor GC 발생
    * Old Generation
      * Young Generation에서 넘어온 객체 저장
      * 객체가 사라질 때 Major GC(Full GC)가 발생
    * Permanent Generation
      * Class Loader에 의해 로드된 클래스, 메소드 등에 대한 메타 정보 저장
      * 리플렉션을 사용하여 동적으로 클래스가 로딩되는 경우 사용
        * 리플렉션 자주 쓰는 Spring Framework는 이 영역 고려 해야함.

### Q13. final vs static
* final
  * 변수 선언 : 변수를 상수로 이용하는 경우 사용
  * 함수 선언 : 오버라이딩이 불가능한 메소드를 정의할 때 사용
  * 클래스 선언 : 해당 클래스 상속 불가능
  * 단 한번 초기화 가능
* static : 
  * 클래스에 소속된 클래스 변수/메소드를 의미.

### Q14. 객체의 직렬화(Serialization)
* 객체 데이터를 연속적인 데이터로 변형하여 전송 가능하게 함.
* Serialize 인터페이스 상속으로 직렬화 가능한 클래스로 변경 가능.

### Q15. String vs StringBuffer vs StringBuilder
* String
  * 한번 생성되면 변경 불가능한 immutable 속성을 가지고 있음.
    * 변경이 적고 참조만 많은 경우
    * 여러 쓰레드에서 공유하는 경우 안전하게 사용
  * 문자열 변경시 새로운 객체를 생성하므로 메모리/속도면에서 비효율적임
  * 읽기 목적이 뚜렷한 경우 사용
* StringBuffer
  * mutable class.
  * 동기화 지원. Thread safe함.
* StringBuilder
  * mutable class.
  * 동기화 지원하지 않음.
    * StringBuffer보다 속도가 빠름.
  * jdk 1.5버전 이상에서 성능의 이슈로 string이 stringBuilder로 치환되어 컴파일 됨.

### Q16. 기본 자료형(Primitive data type) vs 참조 자료형(Reference data type)
* 기본 자료형(Primitive data type)
  * byte, short, int, long, float, double, char, boolean
  * 변수에 값 자체가 저장됨.
  * OS에 따라 자료형의 길이가 별하지 않음.
  * null 값을 가질 수 없음.
* 참조 자료형(Reference data type)
  * class, interface, array, enum
  * 변수에 객체의 주소값이 저장됨.
  * null 값을 이용해 해제 할 수 있음.

### Q17. JIT(Just In Time) 컴파일러에 대하여
* bytecode(.class) -> 기계어로 해석할 때 반복되는 내용을 한번만 컴파일함.
* 프로그램을 실행하는 시점에서 필요한 부분을 즉석에서 컴파일 하는 방식.
* 실행될 때 최초에 실행됨. 최초 실행시 느려질 수 있음.
* 컴파일 없이 Interpret만 하는 경우보다 반복적인 작업에서 성능을 높일 수 있음.

### Q18. Java 8 변경사항
* 람다(lamda) 표현식 추가
* 기본 메서드
  * 인터페이스에 새 기능이 추가될 경우 이를 상속받는 클래스 모두 구현해야 했으나 기본 메서드 추가로 구현하지 않을 경우 인터페이스에 구현된 메서드 사용.
* 날짜 API 개선 joda time 참조
