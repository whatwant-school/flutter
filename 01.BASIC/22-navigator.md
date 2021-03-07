# 완전 초보용 플러터(flutter) 강좌 22 | 조금 매운 맛 강좌 대비 3: Navigator(네비게이터) 이해하기
- https://www.youtube.com/watch?v=BWG9XS5ecig


## Agenda
1. Route 개념
1. Navigator 정의와 push/pop 함수, stack 자료 구조
1. MaterialPageRoute 위젯과 context
1. 페이지 이동 기능 구현 완성


## Reference
- https://api.flutter.dev/flutter/widgets/Navigator-class.html


---

## Route 개념
- Route : 스마트폰에서 보여지는 하나의 `페이지` 또는 `화면`


## Navigator 정의와 push/pop 함수, stack 자료 구조
- Navigator : Route 객체를 관리
- stack 구조로 쌓는 방식(stack)이기에 push/pop 필요


## Source Code
- First Page를 대체하는 것이 아니라 그 위에 Second Page가 쌓이는 방식이다
- 그래서 입력하는 `context`는 현재 First Page의 context를 지칭한다.

- `MaterialPageRoute(builder: builder)`를 사용하는 이유는 일종의 안전 장치이다

```Dart
class Page22 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('First Page'),
      ),
      body: Center(
        child: RaisedButton(
          onPressed: () {
            Navigator.push(context,
                MaterialPageRoute(builder: (BuildContext context) {
              return SecondPage();
            }));
          },
          child: Text('Go to the Second Page'),
        ),
      ),
    );
  }
}
```

- 위의 코드는 아래와 같이 간략화 할 수도 있다.

```Dart
class Page22 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('First Page'),
      ),
      body: Center(
        child: RaisedButton(
          onPressed: () {
            Navigator.push(
                context, MaterialPageRoute(builder: (context) => SecondPage()));
          },
          child: Text('Go to the Second Page'),
        ),
      ),
    );
  }
}
```

- 전체 소스코드는 아래와 같다.

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
        primarySwatch: Colors.orange,
      ),
      home: Page22(),
    );
  }
}

class Page22 extends StatelessWidget {
  @override
  Widget build(BuildContext context2) {
    return Scaffold(
      appBar: AppBar(
        title: Text('First Page'),
      ),
      body: Center(
        child: RaisedButton(
          onPressed: () {
            Navigator.push(context2,
                MaterialPageRoute(builder: (context) => SecondPage()));
          },
          child: Text('Go to the Second Page'),
        ),
      ),
    );
  }
}

class SecondPage extends StatelessWidget {
  @override
  Widget build(BuildContext context3) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Second Page'),
      ),
      body: Center(
        child: RaisedButton(
          onPressed: () {
            Navigator.pop(context3);
          },
          child: Text('Go to the First Page'),
        ),
      ),
    );
  }
}
```


### `RaisedButton`은 deplrecated 된다고 해서 `ElevatedButton`으로 바꿔봤다.

```Dart
import 'package:flutter/material.dart';
import 'package:fluttertoast/fluttertoast.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Appbar',
      theme: ThemeData(
        primarySwatch: Colors.orange,
      ),
      home: Page22(),
    );
  }
}

class Page22 extends StatelessWidget {
  @override
  Widget build(BuildContext context2) {
    return Scaffold(
      appBar: AppBar(
        title: Text('First Page'),
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.push(context2,
                MaterialPageRoute(builder: (context) => SecondPage()));
          },
          child: Text('Go to the Second Page'),
        ),
      ),
    );
  }
}

class SecondPage extends StatelessWidget {
  @override
  Widget build(BuildContext context3) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Second Page'),
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.pop(context3);
          },
          child: Text('Go to the First Page'),
        ),
      ),
    );
  }
}
```
