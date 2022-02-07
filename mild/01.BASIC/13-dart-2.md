# 완전 초보용 플러터(flutter) 강좌 13 | 플러터 다트(dart) 핵심정리: 클래스와 위젯의 정체 2

- https://www.youtube.com/watch?v=DXMKK6-957I


## Class and Widget
- 생성자와 관련된 함수의 구조와 기능
- 생성자의 구조와 역할
- 클래스와 위젯의 관계

### 생성자 기본

```Dart
class Person{
  String name;
  int age;
  String sex;
  
  Person(String name, int age, String sex){
    this.name = name;
    this.age = age;
    this.sex = sex;
  }
}

void main() {
  
  Person p1 = new Person('Tom', 30, 'male');
  Person p2 = new Person('Jane', 27, 'female');
  
  print(p1.age);
  print(p2.age);
}
```


### named argument
- 생성자에서 parameter를 `{}`로 둘러싸면, parameter 입력이 선택사항이 된다.
- 또한 선택적으로 지명해서 입력할 수도 있다.

```Dart
class Person{
  String name;
  int age;
  String sex;
  
  Person({String name, int age, String sex}){
    this.name = name;
    this.age = age;
    this.sex = sex;
  }
}

void main() {
  
  Person p1 = new Person(age:30);
  Person p2 = new Person(name:'Jane');
  
  print(p1.age);
  print(p2.name);
}
```


## 클래스 and 위젯

앞에서 공부했던 Flutter의 문법이 어디에서 비롯된 것인지 위에서 알아 보았다.
결국은 클래스 == 위젯 ...
