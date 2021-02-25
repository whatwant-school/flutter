# 완전 초보용 플러터(flutter) 강좌 9 | 캐릭터 페이지 디자인 1: 위젯정리

- URL : https://www.youtube.com/watch?v=gUVAUOvPm_c


## 캐릭터 카드 페이지 만들기

```Dart
class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Bookllenge'),
        centerTitle: true,
        backgroundColor: Colors.redAccent,
        elevation: 0.0,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text('hello'),
            Text('hello'),
            Text('hello'),
          ],
        ),
      ),
    );
  }
}
```
