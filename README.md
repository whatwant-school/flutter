# 플러너 4기

## 과정 링크
- 과정소개: https://study.flearner.co/flutter
- 사전미션: https://flearnerhq.notion.site/8-049b8887b3b5465380a4b61b12252756
- 채널톡 바로가기: https://flearner.channel.io
- 카카오 오픈채팅: https://open.kakao.com/o/g5Jv9Yyd
- Notion: https://flearnerhq.notion.site/4-ee2fe395a4354302b6b4e02fe13322ff

---
## 학습 자료
- Angela 자료
  - https://github.com/londonappbrewery/Flutter-Course-Resources
- Flunner 자료
  - https://github.com/Flearner-flutter/Flutter-Course-Resources

---
# The Complete 2021 Flutter Development Bootcamp with Dart

## 01. Introduction to Cross-Platform Development with Flutter and Dart (39m)
- 그냥 일반적인 소개 내용


## 02. Setup and Installation (78m)
- Windows 환경 및 macOS 환경 각각에 대한 친절한 설치 안내


## 03. I Am Rich - How to Create Flutter Apps From Scratch (58m)
- Flutter App 생성 방법
  - VSCode 에서는 organization 미리 셋팅 해놓으면 편리함
- Scaffold()
  - appBar - title / backgroundColor / body
- Image() - NetworkImage()
- Center()
- draw.io 사이트를 소개해줬는데, 아래 사이트로 redirect 됨
  - https://app.diagrams.net/
- image 등의 리소스 활용을 위한 pubspec.yaml 작성법
- App Icon 만들고 등록하기
  - https://appicon.co/
  - 여러 유형에 알맞은 App Icon Generator Site
  - android/ios 폴더에 App Icon 등록하는 곳이 존재
    - android/app/src/main/res/
    - ios/Runner/Assets.xcassets/
  - 원형 아이콘에 맞추기 위해서 Android Studio 활용 가능
    - android/ 에서 'Open in Android Studio' 실행
    - app/res/ 에서 'Image Asset' 실행
    - icon 편집 가능
    - 일괄 변경도 가능


## 04. Running Your App on a Physical Device (26m)
- 실제 Android/iPhone 기기에서 실행하는 방법


## 05. I Am Poor - App Challenge (8m)
- 직접 만들기 숙제
- icon 자료 창고
  - https://icons8.com/
    - Icons, illustrations, photos, music, and design tools
  - https://www.vecteezy.com/
    - Download Free Vector Art, Stock Photos & Stock Videos.
  - https://www.canva.com/
    - 다양한 유형의 아이콘/배경 디자인을 웹에서 쉽게 만들 수 있도록 도와주는 도구
    - 한글도 지원을 해줘서 당황


## 06. MiCard - How to Build Beautiful UIs with Flutter Widgets (95m)
- git/GitHub 간단한 설명
- HotReload
- `stless` 타이핑 하면 **StatelessWidget** 자동완성 구문이 나온다!!


### Container()
- Layout widgets : layout 관련된 여러 widget을 모아서 설명 (Container 포함)
  - https://docs.flutter.dev/development/ui/widgets/layout
- child가 없는 Container는 가능한 큰 크기를 갖는다.

```dart
// 아래 예제의 경우 child 없는 Container에 의해 전체가 하얗게 된다.

return Scaffold(
  backgroudColor: Colors.teal,
  body: Container(
    color: Colors.white,
  ),
);

// 다음과 같이 child를 갖는 경우 child 크기로 줄어든다.

return Scaffold(
  backgroudColor: Colors.teal,
  body: Container(
    color: Colors.white,
    child: Text('Hello'),
  ),
);
```

- height: / width:
  - double.infinity : 화면의 가장 큰 값
- margin: (바깥)
  - EdgeInsets.symmetric()
    - vertical / horizontial
  - EdgeInsets.fromLTRB()
    - left / top / right / bottom
  - EdgeInsets.only()
    - choice one : left / top / right / bottom
  - EdgeInsets.all()
- padding: (내부)
  - margin과 동일


### SafeArea()
- 위 아래 위험한(?) 영역을 제외할 수 있음


### Column() - Row()와 거의 동일
- child가 아닌 **children**을 사용 (복수 widgets을 다루기 때문)
- mainAxisSize:
  - MainAxisSize.min
- verticalDirection:
  - verticalDirection.up : 밑에서부터 위로 쌓아 올라감
  - verticalDirection.down
- mainAxisAlignment:
  - MainAxisAlignment.start : 시작 위치부터 배열하고자 함
  - MainAxisAlignment.end : 끝 위치부터 배열하고자 함
    - verticalDirection.up과 다르게 쌓아올라가는 것은 아님. 위치만!
  - MainAxisAlignment.center : 가운데 위치
  - MainAxisAlignment.spaceEvenly : 간격을 넓직하게 띄어서 배치
  - MainAxisAlignment.spaceBetween : 양쪽 정렬 (끝까지 띄어서 배치)
- crossAxisAlignment:
  - CrossAxisAlignment.end : children에 있는 아이들 중 가장 오른쪽에 있는 아이를 기준으로 끝 정렬
  - CrossAxisAlignment.stretch : 화면 크기를 기준으로 잡아늘이기
    - chidren의 width값을 double.infinity로 주지 않아도 된다


### SizedBox()
- child 사이에 간격을 주고 싶을 때 사용
- width: / height:
- child:
  - Divider() 같은 class 사용 가능


### Divider()
구분선 같은 용도로 사용
- https://api.flutter.dev/flutter/material/Divider-class.html
- color:
- 길이를 줄이기 위해서는 상위 위젯으로 설정 가능
  - SizedBox()의 width값 설정으로 중간에 짧은 구분선 삽입

```dart
SizedBox(
  height: 20.0,
  width: 150.0,
  child: Divider(
    color: Colors.teal.shade100,
  ),
)
```

### CircleAvatar()
원형 이미지를 출력하기 위한 아이
- radius:
- backgroundColor:
- backgroundImage:
  - AssetImage('images/xxx.jpg)
  - pubspec.yaml에서 assets 지정해주는 것 잊지 말기


### Text()
- style:
  - TextStyle()
    - fontSize:
    - color:
      - Colors.teal[100] = Colors.teal.shade100
    - fontWeight:
      - FontWeight.bold
    - fontFamily:
      - 밑에서 정의한 Custom Font의 family 명칭 사용
    - letterSpacing:


### Custom Font
- 상업적으로 이용가능한 폰트 제공
  - https://fonts.google.com/
- flutter에서 custom fonts 사용하는 방법
  - https://docs.flutter.dev/cookbook/design/fonts
- 다운로드 받은 ttf 파일을 임의의 디렉토리에 복사 (./fonts)
- pubspec.yaml에서 assets와 같은 레벨로 **fonts** 정의

```yaml
  assets:
  - images/
  
  fonts:
  - family: xxx
    fonts:
    - asset: fonts/xxx-xxx.ttf
```


### Icon()
- Icons 에서 사용할 수 있는 것들을 예쁘게 보여줌
  - https://api.flutter.dev/flutter/material/Icons-class.html
- 어울리는 색상 palletes 조합을 알려준다.
  - https://www.materialpalette.com/
  - More Awesome Design 링크를 못찾았는데, 직접 들어가면 Colors, Icons 관련 항목도 있다.
    - https://www.materialpalette.com/colors
    - https://www.materialpalette.com/icons
- size:
- color:


### Card()
Container와 비슷하지만, 그림자가 있고 모서리에 작은 곡선으로 처리
- https://api.flutter.dev/flutter/material/Card-class.html
- Container 대신 Card를 사용하면 되지만
- padding 속성은 사용하지 못함
  - Padding class로 묶어 줘야 함
- 기본색은 white로 되어 있음


### Padding()
- child에게 padding 속성을 줌
- 이걸 이용해서 Card()를 둘러쌀 수 있음
  - 하지만, Card() 내부에 padding을 주는 것이 아니라 바깥에 적용

```dart
Padding(
  padding: EdgeInsets.all(8.0),
  child: const Card(
    child: Text('Hello')
  ),
)
```


### ListTile()
Card()의 child로 icon과 text를 처리할 때 유용한 class
- https://api.flutter.dev/flutter/material/ListTile-class.html
- leading:
  - Icon() 같은 것 지정
- title:
  - Text() 같은 것 지정

```dart
Card(
  color: Colors.white,
  margin: EdgeInsets.symmetric(vertical: 10.0, horizontal: 25.0),
  child: ListTile(
    leading: Icon(
      Icons.email,
      color: Colors.teal,
    ),
    title: Text(
      'whatwant@gmail.com',
      style: TextStyle(
        fontSize: 20.0,
        color: Colors.teal.shade900,
        fontFamily: 'Source Sans Pro',
      ),
    ),
  ),
)
```

- 이렇게 하면, 적당한 padding이 적용된 위젯을 볼 수 있음


## 07. Dicee - Building Apps with State (103m)
주사위 굴리기 앱 만들기

### Image()
- https://api.flutter.dev/flutter/widgets/Image-class.html
- image:
  - AssetImage()
    - path of image
- width: / height:

```dart
Image(
  image: AssetImage('images/dice1.png'),
),

// 위 코드와 아래 코드는 같은 내용

Image.asset('images/dice1.png'),
```


### Expanded()
- Overflow : 화면의 경계를 벗어나게 되는 경우 노란색/검은색 바가 나오게 됨
- Row, Column, Flex 에서 사용할 수 있음
- https://api.flutter.dev/flutter/widgets/Expanded-class.html
- child:
  - Image()와 같은 widget에 사용
- flex:
  - 다른 Expanded()와의 크기 비율 지정

```dart
// 앞의 Expanded()가 2배의 크기로 출력

<Widget> [
  Expanded(
    flex: 2,
    child: Image(
      image: AssetImage('images/dice1.png'),
    ),
  ),
  Expanded(
    flex: 1,
    child: Image(
      image: AssetImage('images/dice1.png'),
    ),
  ),
],
```

### Center()
- child:
  - Row() : 위아래 기준으로 중앙 정렬


### Buttons
많이 바뀐 컨텐츠이므로 사이트 정보 확인 필요
- https://docs.flutter.dev/development/ui/widgets/material#Buttons

### FlatButton() → TextButton()
- child:
  - Image.asset() 같은 요소들
- onPressed: () {}
  - VoidCallback = no parameter, no return
  - 

### Dart Functions
함수에 대해 기본적인 설명


### Hot Reload
**build** widget에 대해서만 적용이 됨

```dart
// 변수가 build 외부에서 정의되면 Hot Reload 적용이 안됨

class DicePage extends StatelessWidget {
  var leftDiceNumber = 5;

  @override
  Widget build(BuildContext context) {
    ...
      child Image.asset('images/dice$leftDiceNumber.png'),
    ...
  }
}

// 변수가 build 내부에서 정의되면 Hot Reload 적용됨

class DicePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    var leftDiceNumber = 5;

    ...
      child Image.asset('images/dice$leftDiceNumber.png'),
    ...
  }
}
```

- 위의 예제의 경우 StatelessWidget을 사용하면 안되는 상황이긴 하다.


### Dart Variables / Data Types
변수 및 데이터 타입에 대한 기본적인 설명
- Dart 문법을 실습해볼 수 있는 사이트
  - https://dartpad.dev

```dart
void main() {
  var myName = 'whatwant';

  print (myName);
}
```

- Primitive Types
  - String / int / double / bool



### StatefulWidget
2개의 class로 구성

```dart
class [Name] extends StatefulWidget {
  @override
  _[Name]State createState() => _[Name]State();
}

class _[Name]State extends State<[Name]> {
  return Container();
}
```

### setState()
**build() {}** 구문을 다시 실행하길 원할 때 사용

```dart
TextButton (
  onPressed: () {
    setState(() {
      leftDiceNumber = 5;
    })
  },
  child: Image.asset('images/dice$leftDiceNumber.png'),
)
```


### Random()
- https://api.flutter.dev/flutter/dart-math/Random-class.html

















