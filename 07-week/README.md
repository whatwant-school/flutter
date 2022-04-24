# 15. Flash Chat - Flutter x FireBase Cloud FireStore (3 hour 56 min)
Firebase를 이용한 채팅앱 개발

- stub project
  - https://github.com/Flearner-flutter/flash-chat-flutter-flearner


## Route

### Links
- https://docs.flutter.dev/cookbook/navigation/named-routes
  - Navigate with named routes


## static


## Flutter Animation - Hero Animations/Custom Animation

### Links
- https://dribbble.com/
  - 상당한 퀄리티의 디자인 리소스
- https://docs.flutter.dev/development/ui/animations/hero-animations
  - Hero Animtaions
- https://api.flutter.dev/flutter/animation/CurvedAnimation-class.html
  - CurvedAnimation class


## Minins

## TyppewriteAnimatedTextKit (deprecated)
```dart
                DefaultTextStyle(
                  style: const TextStyle(
                    color: Colors.blueGrey,
                    fontSize: 45.0,
                    fontWeight: FontWeight.w900,
                  ),
                  child: AnimatedTextKit(
                    animatedTexts: [
                      TypewriterAnimatedText('Flash Chat'),
                    ],
                    // onTap: () {
                    //   print("Tap Event");
                    // },
                  ),
                ),
```

### Links
- https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins
  - mixins
- https://pub.dev/packages/animated_text_kit
  - animated text kit


## Refactoring

### Function
- class에서 function을 변수로 다룰 때 강의와 차이점
```dart
  # deprecated
  final Function onPressed;
  
  # now
  final void Function() onPressed;
```

### hintText
- 기본 설정으로는 hintText가 보이질 않는다. 색상일 지정하려면 다음과 같이 하면 된다.
```dart
              decoration: const InputDecoration(
                hintText: 'Enter your email',
                hintStyle: TextStyle(color: Colors.grey),
```

### copyWith()
- 일부 속성만 변경하기




## FireBase

### Error
- 기존 실행 중이던 앱 전부 종료 하고 다시 빌드, 실행하면 에러 발생
- SDK 버전 이슈인데, 아래와 같이 minSdkVersion 올려주면 일단은 해결됨
  - ./android/app/build.gradle
```dart
    defaultConfig {
        // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
        applicationId "co.whatwant.flash_chat"
        minSdkVersion 19
        targetSdkVersion 30
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
    }
```

- 그런데, 어설프게 올리면 아래와 같이 Multidex 에러가 또 발생할 수 있음
  - Flutter 2.10에서 multidex 사용하는 것이 기본 설정으로 된다고 했는데...
```sh
[!] App requires Multidex support
┌─ Flutter Fix ──────────────────────────────────────────────────────────────────────────────────┐
│ Flutter multidex handling is disabled. If you wish to let the tool configure multidex, use the │
│ --mutidex flag.                                                                                │
└────────────────────────────────────────────────────────────────────────────────────────────────┘
```

- 아래와 같은 설정을 추가함으로써 해결할 수도 있지만, 그냥 minSdkVersion 값을 21 이상으로 해주면 심플하게 해결
```gradle
    defaultConfig {
        ...
        multiDexEnabled true
    }
...

dependencies {
    ...
    implementation 'com.android.support:multidex:2.0.1'
}
```

- iOS 실행을 하면 또 에러 발생

```sh
    [!] Automatically assigning platform `iOS` with version `9.0` on target `Runner` because no platform was specified. Please specify a platform for this target in your Podfile. See `https://guides.cocoapods.org/syntax/podfile.html#platform`.
```
  - ios/Podfile 에서 아래와 같이 명시적으로 적어주면 됨
  - 9.0으로 하면 또 에러가 나서 10.0으로 했더니 해결됨 (각자 상황에 맞는 버전으로 하면 될듯)
```
# platform :ios, '9.0'
platform :ios, '10.0'
```

### cocoapods update
```sh
$ pod repo update
$ sudo gem install cocoapods -n /usr/local/bin
$ pod setup
```


### Links
- https://github.com/firebase/flutterfire
  - FlutterFire plugins
  - flutter 하위에서 별도로 분리되어 이사갔음
  - 문서 내용들은 별도로 제공됨
    - https://firebase.flutter.dev/
    - https://pub.dev/publishers/firebase.google.com/packages



## firebase_auth
- 강의에서는 이 부분을 못봤다.
```dart
# main.dart

# before
void main() => runApp(FlashChat());

# after
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp();
  runApp(const FlashChat());
}
```

- 그리고 관련해서 겪은 버전 차이들...
```dart
# before
final user = await _auth.currentUser();
# now
final user = _auth.currentUser;

# before
FirebaseUser loggedInUser;
# now
User loggedInUser;
```


## progress
- 기존 패키지는 null safty 이슈로 에러 발생
- null safty 패키지로 사용

### Links
- https://pub.dev/packages/modal_progress_hud
  - modal progress hud
- https://pub.dev/packages/modal_progress_hud_nsn
  - Null Safty version


## FireStore

```dart
# before
final _firestore = FireStore.instance;
# now
final _firestore = FirebaseFirestore.instance;

# before
  void getMessages() async {
    final messages = await _firestore.collection('messages').getDocuments();

    for (var message in messages.documents) {
      print(message.data);
    }
  }
# now
  void getMessages() async {
    final messages = await _firestore.collection('messages').get();

    for (var message in messages.docs) {
      print(message.data());
    }
  }
```


## StreamBuilder

### change
- before
```dart
              final messages = snapshot.data.documents;
                List<Text> messageWidgets = [];
                for (var message in messages!) {
                  final messageText = message.data['text'];
```
- now
```dart
              final messages = snapshot.data?.docs;
                List<Text> messageWidgets = [];
                for (var message in messages!) {
                  final messageText = message.get('text');
```


### Links
- https://api.flutter.dev/flutter/widgets/StreamBuilder-class.html
  - StreamBuilder class
- https://api.flutter.dev/flutter/widgets/AsyncSnapshot-class.html
  - AsyncSnapshot class



## ListView


### Links
- https://api.flutter.dev/flutter/widgets/ListView-class.html
  - ListView class













---
# Android Emulator Error
- 안드로이드 에뮬레이터에서 실행을 하고자 하면 저장공간 부족 에러가 발생하곤 한다.
```sh
adb: failed to install /Users/whatwant/workspace/flash-chat-flutter-flearner/build/app/outputs/flutter-apk/app.apk: Failure [INSTALL_FAILED_INSUFFICIENT_STORAGE]
Uninstalling old version...
Error: ADB exited with exit code 1
Performing Streamed Install

adb: failed to install /Users/whatwant/workspace/flash-chat-flutter-flearner/build/app/outputs/flutter-apk/app.apk: Failure [INSTALL_FAILED_INSUFFICIENT_STORAGE]
Error: Failed to install APK again.
Error launching application on sdk gphone64 arm64.
Exited (sigterm)
```
- 에뮬레이터의 기본 저장공간이 너무 작아서 그러니 늘려주자
```sh
❯ cd .android/avd/Nexus_6P_API_32.avd

❯ pwd
/Users/whatwant/.android/avd/Nexus_6P_API_32.avd

❯ nano config.ini
```
```ini
AvdId=Nexus_6P_API_32
PlayStore.enabled=false
abi.type=arm64-v8a
avd.ini.displayname=Nexus 6P API 32
avd.ini.encoding=UTF-8
disk.dataPartition.size=800M
...
```
- `disk.dataPartition.size=2048M` 원하는 만큼 잡아주고, 초기화 하자.
- 당연히, 에뮬레이터 종료 상태에서 진행하자
```sh
❯ rm -rf ./userdata-qemu.img
```
- 이제 다시 에뮬레이터 실행하면 빵빵한 스토리지를 사용할 수 있다.
- 대체 왜 AVD 에서 이런 설정 메뉴를 안만들어주는 것인지 모르겠다.


# Android Error
- Kotlin version
  - ./android/build.gradle
```gradle
buildscript {
    ext.kotlin_version = '1.5.10'
    repositories {
        google()
        mavenCentral()
    }
```

- SDK version
  - ./android/app/build.gradle
```gradle
android {
    compileSdkVersion 31
```
