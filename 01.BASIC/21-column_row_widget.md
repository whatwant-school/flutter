# 완전 초보용 플러터(flutter) 강좌 21 | 조금 매운 맛 강좌 대비 2: 컬럼 위젯(Column widget)과 로우 위젯(Row widget) 되짚어 보기
- https://www.youtube.com/watch?v=8ZpMFUlFcvo


## Reference
- https://medium.com/flutter-community/flutter-layout-cheat-sheet-5363348d037e


## Code

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
        primarySwatch: Colors.red,
      ),
      home: Page21(),
    );
  }
}

class Page21 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.teal,
      body: SafeArea(
          child: Column(
        //세로 중간으로 옴
        //mainAxisAlignment: MainAxisAlignment.center,
        //중간에 간격을 두고
        //mainAxisAlignment: MainAxisAlignment.spaceEvenly,
        //mainAxisAlignment: MainAxisAlignment.spaceBetween,
        //밑에부터 위로 쌓이고
        //verticalDirection: VerticalDirection.up,
        //위부터 아래로 쌓이고
        //verticalDirection: VerticalDirection.down,
        //가로 정렬 중 오른쪽 끝
        crossAxisAlignment: CrossAxisAlignment.end,
        children: <Widget>[
          Container(
            width: 100,
            height: 100,
            color: Colors.white,
            child: Text('Container1'),
          ),
          Container(
            width: 100,
            height: 100,
            color: Colors.blue,
            child: Text('Container2'),
          ),
          Container(
            width: 100,
            height: 100,
            color: Colors.red,
            child: Text('Container3'),
          ),
          // 정렬을 위해 invisible ...
          Container(
            //이걸 선언하면 가로로 최대 길이가 되어서 위의 아이들이 오른쪽 정렬
            width: double.infinity,
          )
        ],
      )),
    );
  }
}
```
