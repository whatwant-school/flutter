## 09.Xylophone - Using Flutter and Dart Packages to Speed Up Development (90min)
- 실로폰 앱을 만들기 위해 사운드를 출력하는 외부 오픈소스 패키지 사용하는 방법을 학습
- `english_words` 패키지는 어느덧 *4.0.0* 버전이 되어있다.
- `audioplayers` 패키지는 사용법 자체가 많이 바뀌었다.
  - `audio_cache.dart`가 `audioplayers.dart`로 합쳐졌나보다.
- Dart Funtion에 대한 설명을 해주는데... 기본적인 개념 수준 + Flutter(Dart) 특성 조금


### Tip #1

```yaml
#pubspec.yaml

   cupertino_icons: ^1.0.2
```
* `^1.0.2` 이렇게 되어있으면 1.0.2 이상의 버전 모두 되는 줄 알았는데, 아니다.
* `2.x` 버전은 안되고 `1.x` 버전 범위에서만 적용이 된다.


### Tip #2
* *Android Studio*의 *External Libraries* 브라우저는 *VSCode*의 *Explorer* 하단에 있는 *DEPENDENCIES*에서 확인할 수 있다.


## Tip #3
* 작업 중에 cocoapods 관련 오류가 계속 튀어나왔다.
* 해결은 새로 clone 받고 pubspec.yaml & main.dart 바로 업데이트 한 뒤 빌드하니까 갑자기 되었는데, 혹시 모르니 아래 링크 참조
* https://stackoverflow.com/questions/64443888/flutter-cocoapodss-specs-repository-is-too-out-of-date-to-satisfy-dependencies


### Link
- https://pub.dev/
  - Flutter Packages 검색 사이트
- https://freesound.org/
  - 다양한 무료 효과음 많음


---
## 10. Quizzler - Modularising & Organising Flutter Code (165min)
* True/False 대답으로 진행하는 퀴즈 앱 만들기 과정
* `Dart Lists`에 대해서 집중 공부
* `Dart Conditions`에서 정말 친절하게 *if else* 구문에 대해 설명
  * 'Please go to the supermarket and buy 1 bottle of milk. If they have eggs, buy 6'
* `Dart Classes`에 대해서도 친절하게 설명을 해준다.
  * 비교문에 이어서 클래스라니?! 심지어 객체지향, 추상화까지?!
  * 심지어 encapsulation까지도 별도 섹션으로 설명해준다.
  * 어허... inheritance, polymorphism 전부 설명한다.


### Tip #1
* `Android Studio`의 *VCS - Local History* 기능은 `VSCode`의 Extension 중에서 *Local History (xyz)* 설치하면 된다.


### Tip #2
* *Question* class 내역이 강의대로 하면 안된다. 다음 구문을 참고해보자.

```dart
class Question {
  late String questionText;
  late bool questionAnswer;

  Question(String q, bool a) {
    questionText = q;
    questionAnswer = a;
  }
}
```


### Links
* https://exercism.org/tracks/dart
  * Dart 언어를 공부하기 위한 깔끔한 사이트
* https://pub.dev/packages/rflutter_alert
  * 경고창을 띄워주는 패키지


---
## 11. Boss Level Challenge 2 - Destini
* Destini 게임 만드는 과정을 글로 안내~


### Links
* https://api.flutter.dev/flutter/widgets/Visibility-class.html
  * Visibility Class
