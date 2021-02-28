# 완전 초보용 플러터(flutter) 강좌 14 | 앱바(app bar) 메뉴 아이콘 추가하기

- https://www.youtube.com/watch?v=ze0t5gWKBvE


## App bar
- leading : 아이콘 버튼이나 간단한 위젯을 왼쪽에 배치할 때
- actions : 복수의 아이콘 버튼 등을 오른쪽에 배치할 때
- onPressed : 함수의 형태로 일반 버튼이나 아이콘 버튼을 터치했을 때 일어나는 이벤트를 정의하는 곳


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
      home: AppBarPage(),
    );
  }
}

class AppBarPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('appBar icon menu'),
        centerTitle: true,
        elevation: 0.0,
        leading: IconButton(
            icon: Icon(Icons.menu),
            onPressed: () {
              print('menu button is clicked');
            }),
        actions: <Widget>[
          IconButton(
              icon: Icon(Icons.shopping_cart),
              onPressed: () {
                print('shopping cart button is clicked');
              }),
          IconButton(
              icon: Icon(Icons.search),
              onPressed: () {
                print('search button is clicked');
              })
        ],
      ),
    );
  }
}
```
