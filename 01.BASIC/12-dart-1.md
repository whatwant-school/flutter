# 완전 초보용 플러터(flutter) 강좌 12 | 플러터 다트(dart) 핵심정리: 클래스와 위젯의 정체 1

- https://www.youtube.com/watch?v=8k4vaoga2co


## Class and Widget

### 프로그래밍 상에서의 클래스란?
- 객체가 가져야 하는 속성과 기능을 정의한 내용을 담고 있는 설계도 역할


### 프로그래밍 상에서의 객체란?
- 클래스가 정의된 후 메모리상에 할당되었을 때 이를 객체라고 함


### 프로그래밍 상에서의 인스턴스란?
- 클래스를 기반으로 생성 됨
- 클래스의 속성과 기능을 똑같이 가지고 있고 프로그래밍 상에서 사용되는 대상


## DartPad
- https://dartpad.dev/

### 변수
- var 타입으로 선언하면 스스로 알아서 추론해서 변수 타입을 지정하기도 함
- 하지만, 정확하지 않기에 명시적으로 선언하는 것을 추천


```Dart
class Person{
  String name = 'John';
  int age;
  String sex;
}

void main() {
  
  // Person class로 p1이라는 인스턴스를 생성
  Person p1 = new Person();
  
  p1.age = 30;
  
  print(p1.age);
}
```
