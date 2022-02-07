# 완전 초보용 플러터(flutter) 강좌 20 | 조금 매운 맛 강좌 대비 1: 컨테이너 위젯(Container widget) 되짚어 보기
- https://www.youtube.com/watch?v=RhEzrNTSW7c


## Reference
- https://flutter.dev/docs/development/ui/widgets/layout
  - https://api.flutter.dev/flutter/widgets/Container-class.html


## Container Widget
- Container는 가능한 최대의 크기를 갖고자 한다
- 하지만, child를 갖게 되면 그 child 크기에 맞춰 줄어들어 버린다
- Container는 오직 1개의 child만 갖을 수 


### 기본 상태 → 전체 blue

```Dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Appbar',
      theme: ThemeData(
        primarySwatch: Colors.red,
      ),
      home: Page20(),
    );
  }
}

class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.blue,
    );
  }
}
```


### Container 추가 → 전체 red

```Dart
class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.blue,
      body: Container(
        color: Colors.red,
      ),
    );
  }
}
```


### Container에 child 추가 → Hello 글씨 만큼만 red, 나머지는 blue

```Dart
class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.blue,
      body: Container(
        color: Colors.red,
        child: Text('Hello'),
      ),
    );
  }
}
```

- 그런데, 그나마 그 글씨가 위쪽 noti 영역에 위치 → SafeArea로 한정시킬 수 있음


### SafeArea 지정 → 아래 영역으로 제대로 출력

``` Dart
class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        backgroundColor: Colors.blue,
        body: SafeArea(
          child: Container(
            color: Colors.red,
            child: Text('Hello'),
          ),
        )
    );
  }
}
```


### 위치 조정 1

```Dart
class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        backgroundColor: Colors.blue,
        body: SafeArea(
          child: Container(
            color: Colors.red,
            child: Text('Hello'),
            width: 100,
            height: 100,
            margin: EdgeInsets.all(20),
          ),
        ));
  }
}
```

### 위치 조정 2

```Dart
class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        backgroundColor: Colors.blue,
        body: SafeArea(
          child: Container(
            color: Colors.red,
            child: Text('Hello'),
            width: 100,
            height: 100,
            margin: EdgeInsets.symmetric(
              vertical: 80,
              horizontal: 20
            )
          ),
        ));
  }
}
```


### 위치 조정 3
- padding 값을 늘려벼리면 글씨 출력 부분이 줄어들 수 있다. (padding vs margin)
  - padding : 안쪽
  - margin : 바깥쪽

```Dart
class Page20 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        backgroundColor: Colors.blue,
        body: SafeArea(
          child: Container(
            color: Colors.red,
            child: Text('Hello'),
            width: 100,
            height: 100,
            margin: EdgeInsets.symmetric(vertical: 80, horizontal: 20),
            padding: EdgeInsets.all(20),
          ),
        ));
  }
}
```
