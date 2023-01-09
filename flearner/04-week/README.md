# 12. BMI Calcurator - Building Flutter UI for Imtermediates (4hr 27min)

## ThemeData

### primaryColor
강의에 나오는 대로 적용되지 않는다.
```dart
# deprecated
      theme: ThemeData(
        primaryColor: Colors.red,
      ),

# new
      theme: ThemeData(
        colorScheme: ColorScheme.light().copyWith(
          primary: Colors.red,
        ),
      ),
```


### accentColor
마찬가지로 아래와 같이 변경하여야 한다
```dart
      theme: ThemeData(
        colorScheme: ColorScheme.light().copyWith(
          primary: Colors.red,
          secondary: Colors.purple,
        ),
      ),
```


### textTheme
body1 항목이 bodyText2 항목하고 대응되는 이상한 일이?!
```dart
# deprecated
        textTheme: TextTheme(
          body1: TextStyle(
            color: Color(0xFFFFFFFF),
          ),
        ),

# new
        textTheme: TextTheme(
          bodyText2: TextStyle(
            color: Color(0xFFFFFFFF),
          ),
        ),
```


### Links
- https://dribbble.com/
  - 멋진 디자인을 볼 수 있는 사이트
  - 특히, Mobile UI도 볼 수 있음
- https://docs.flutter.dev/cookbook
  - Flutter Cookbook
- https://docs.flutter.dev/cookbook/design/themes
  - Documents for Theme
- https://www.colorzilla.com/
  - 색을 찍어 볼 수 있게 해주는 chrome extension


## Split Source File
깔끔하게 정리할 수 있어서 좋다!


## Key

### Links
- https://www.youtube.com/watch?v=kn0EOS-ZiIc
  - When to Use Keys - Flutter Widgets 101 Ep. 4


## final vs const

### Links
- https://dart.dev/guides/language/language-tour#final-and-const
  - final and const


## font

### Links
- https://pub.dev/packages/font_awesome_flutter
  - 딩벳 폰트와 같은 기능


## GestureDetector

### Links
- https://api.flutter.dev/flutter/widgets/GestureDetector-class.html


## Enums (Enumeration)
```dart
enum EnumName {typeA, typeB, typeC}

EnumName.typeA
```

## Ternary Operator (3항 연산자)
```dart
Condition ? DoThisIfTrue : DoThisIfFalse
```


## Functions
함수를 *()* 없이 사용하는 것은 정말 헷갈린다.

* 함수의 parameter로 function을 전달
* 변수처럼 function을 선언
  * class method도 이와 같은 방식으로 정의 가능

```dart
# deprecated
class ReusableCard extends StatelessWidget {
  ReusableCard({required this.colour, required this.cardChild, this.onPress});

  final Color colour;
  final Widget cardChild;
  final Function? onPress;

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: onPress,
      child: Container(

# new
class ReusableCard extends StatelessWidget {
  ReusableCard({required this.colour, required this.cardChild, this.onPress});

  final Color colour;
  final Widget cardChild;
  final VoidCallback? onPress;

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: onPress,
      child: Container(
```


## Slider class

### Links
- https://api.flutter.dev/flutter/material/Slider-class.html


## Customisation


## Routes & Navagation

### Links
- https://docs.flutter.dev/cookbook/navigation/navigation-basics


## Maps
```dart
Map<keyType, valueType> mapName {
  Key: Value
}

mapName[Key]
```


## BMI

### Links
- https://ko.wikipedia.org/wiki/체질량_지수








