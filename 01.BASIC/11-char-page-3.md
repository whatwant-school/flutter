# 완전 초보용 플러터(flutter) 강좌 11 | 캐릭터 페이지 디자인 3: 실전코딩 part 2(완결편)

- https://www.youtube.com/watch?v=qnnExhBcNTk


## Tip
테스트 앱의 오른쪽 상단의 debug 표시 지우려면...

```Dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
...
```

## coding

```Dart
class Grade extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.amber[800],
      appBar: AppBar(
        title: Text('Bookllenge'),
        backgroundColor: Colors.amber[700],
        centerTitle: true,
        elevation: 0.0,
      ),
      body: Padding(
        padding: EdgeInsets.fromLTRB(30.0, 40.0, 0.0, 0.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: <Widget>[
            Center(
              child: CircleAvatar(
                backgroundImage: AssetImage('assets/rabbit-1.png'),
                radius: 60.0,
              ),
            ),
            Divider(
              height: 60.0,
              color: Colors.grey[850],
              thickness: 0.5,
              endIndent: 30.0,
            ),
            Text(
              'NAME',
              style: TextStyle(color: Colors.white, letterSpacing: 2.0),
            ),
            SizedBox(
              height: 10.0,
            ),
            Text(
              'BBANTO',
              style: TextStyle(
                  color: Colors.white,
                  letterSpacing: 2.0,
                  fontSize: 28.0,
                  fontWeight: FontWeight.bold),
            ),
            SizedBox(
              height: 30.0,
            ),
            Text(
              'BBANTO POWER LEVEL',
              style: TextStyle(color: Colors.white, letterSpacing: 2.0),
            ),
            SizedBox(
              height: 10.0,
            ),
            Text(
              '14',
              style: TextStyle(
                  color: Colors.white,
                  letterSpacing: 2.0,
                  fontSize: 28.0,
                  fontWeight: FontWeight.bold),
            ),
            SizedBox(
              height: 30.0,
            ),
            Row(
              children: <Widget>[
                Icon(Icons.check_circle_outline),
                SizedBox(
                  height: 10.0,
                ),
                Text(
                  'using lightsaber',
                  style: TextStyle(fontSize: 16.0, letterSpacing: 1.0),
                )
              ],
            ),
            Row(
              children: <Widget>[
                Icon(Icons.check_circle_outline),
                SizedBox(
                  height: 10.0,
                ),
                Text(
                  'face here tattoo',
                  style: TextStyle(fontSize: 16.0, letterSpacing: 1.0),
                )
              ],
            ),
            Row(
              children: <Widget>[
                Icon(Icons.check_circle_outline),
                SizedBox(
                  height: 10.0,
                ),
                Text(
                  'fire flames',
                  style: TextStyle(fontSize: 16.0, letterSpacing: 1.0),
                )
              ],
            ),
            Center(
              child: CircleAvatar(
                backgroundImage: AssetImage('assets/rabbit-2.png'),
                radius: 40.0,
                backgroundColor: Colors.amber[800],
              ),
            )
          ],
        ),
      ),
    );
  }
}
```
