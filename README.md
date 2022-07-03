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
## The Complete 2021 Flutter Development Bootcamp with Dart

### 01. Introduction to Cross-Platform Development with Flutter and Dart (39m)
- 그냥 일반적인 소개 내용


### 02. Setup and Installation (78m)
- Windows 환경 및 macOS 환경 각각에 대한 친절한 설치 안내


### 03. I Am Rich - How to Create Flutter Apps From Scratch (58m)
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


### 04. Running Your App on a Physical Device (26m)
- 실제 Android/iPhone 기기에서 실행하는 방법


### 05. I Am Poor - App Challenge (8m)
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
- 아래 예제의 경우 child 없는 Container에 의해 전체가 하얗게 된다. 
```dart
return Scaffold(
  backgroudColor: Colors.teal,
  body: Container(
    color: Colors.white,
  ),
);
```
- 다음과 같이 child를 갖는 경우 child 크기로 줄어든다.
```dart
return Scaffold(
  backgroudColor: Colors.teal,
  body: Container(
    color: Colors.white,
    child: Text('Hello'),
  ),
);
```

