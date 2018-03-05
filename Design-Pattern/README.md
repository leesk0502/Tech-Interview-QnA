[Back to Contents](../README.md)
# Design Pattern Interview QnA
디자인 패턴 면접 질문과 답

### Q1. 프레임워크란 무엇인가?
* 소프트웨어의 구체적인 부분에 해당하는 설계와 구현을 재사용이 가능하게끔 일련의 협업화된 형태로 클래스들을 제공하는 것.
* 설계의 기반이 되는 부분을 기술한 **확장 가능한 기반 코드**와 사용자가 이 코드를 자기 입맛대로 확장하는데 **필요한 라이브러리** 이 두가지 요소가 통합되어 제공되는 형태

### Q2. MVC vs MVP vs MVVM
* 각 계층을 분리하여 코드의 재사용성을 높이고 중복을 줄이기 위함.
* MVC(Model + View + Controller)
  * Model : 프로그램에서 사용되는 실제 데이터를 조작 로직을 처리하는 부분
  * View : 사용자에게 보여지는 UI 부분
  * Controller : 사용자의 입력을 받고 처리하는 부분. 여러개의 View를 선택할 수 있음.
  * Process
    * Controller로 사용자의 입력이 들어온다.
    * Controller는 Model의 데이터를 업데이트 및 읽어온다.
    * Model은 해당 데이터를 보여줄 View를 선택해서 화면에 보여준다.
  * Active Model : Model에서 View로 Notify 하는 방식
  * Passive Model : View에서 Model을 Polling 하는 방식
  * 단점
    * View와 Model이 서로 의존적이다.

* MVP(Model + View + Presenter)
  * MVC 패턴의 View와 Model의 의존성을 완전히 분리하기 위함.
  * View와 Model은 서로를 알 필요가 전혀 없다.
  * Presenter : View에서 요청한 부분을 Model에서 가공하여 View로 전달하는 부분
  * Process
    * View로 사용자의 입력이 들어옴.
    * View는 Presenter에 작업 요청.
    * Presenter에서 필요한 데이터를 Model에 요청.
    * Model은 Presenter에 필요한 데이터 응답.
    * Presenter는 View에 데이터 응답.
    * View는 Presenter로 부터 받은 데이터로 화면 갱신.
  * 단점 : View와 Present가 1:1로 강한 의존성을 가진다.

* MVVM(Model + View + ViewModel)
  * MVP의 View와 Present의 의존성을 해결하기 위함.
  * ViewModel : View를 표현하기 위해 만들어진 View를 위한 Model
  * Command 패턴과 Data Binding 두가지를 사용
  * Process
    * View에 입력이 들어오면 Command 패턴으로 ViewModel에 명령함.
    * ViewModel은 Model에 필요한 데이터 요청.
    * Model은 ViewModel에 필요한 데이터 응답.
    * ViewModel은 응답받은 데이터를 가공해서 저장.
    * View는 ViewModel과 Data Binding으로 인해 자동으로 갱신.
