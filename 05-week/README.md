# 13.Clima - Powering Your Flutter App with Live Web Data
외부 API로부터 날씨 정보를 받아와 출력해주는 앱


## geolocator

### permission
강의대로 해도 되겠지만, 아래처럼 하는 것이 더 괜찮지 않나 싶다.
```dart
  Future<void> getCurrentLocation() async {
    bool serviceEnabled;
    LocationPermission permission;

    //Checking location permissions
    serviceEnabled = await Geolocator.isLocationServiceEnabled();
    if (!serviceEnabled) {
      return Future.error('Location services are disabled!');
    }

    permission = await Geolocator.checkPermission();
    if (permission == LocationPermission.denied) {
      permission = await Geolocator.requestPermission();
      if (permission == LocationPermission.denied) {
        return Future.error('Location permissions are denied!');
      }
    }

    if (permission == LocationPermission.deniedForever) {
      return Future.error(
          'Location permissions are permanently denied. Thus, this action cannot be performed.');
    }

    try {
      Position position = await Geolocator.getCurrentPosition(
          desiredAccuracy: LocationAccuracy.low);

      latitude = position.latitude;
      longtitude = position.longitude;
    } catch (e) {
      print(e);
    }
  }
```


### Links
- https://pub.dev/packages/geolocator
  - geolocator


## Asynchronous Programming

### Future / async / await


## Widget Lifecycle

### Stateless
```dart
class Screen1 extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return null;
  }
}
```

### Stateful
```dart
class Screen2 extends StatefulWidget {
  @override
  _Screen2State createState() => _Screen2State();
}

class _Screen2State extends State<Screen2> {
  void initState() {
    super.initState();
  }
  
  Widget build(BuildContext context) {
    return null;
  }
  
  void deactivate() {
    super.deactivate();
  }
}
```


## Dart Exception Handling
```dart
try {

} catch (e) {

}
```


## Null Aware Operator
```dart
someVariable ?? defaultValue
```


## API (Application Programming Interface)

### OpenWeatherMap
- sample API 실행이 안되므로, 처음부터 그냥 가입해서 본인의 API Key 를 사용해야 함
  - 가입 후 email confirm 필요
  - 바로 사용안되고 2시간 이내 활성화 된다고 함


### http
URL을 사용할 때 Uri.parse() 해서 사용해야 한다
```dart
Uri url = Uri.parse('https://api.openweathermap.org/data/2.5/weather?lat=35&lon=139&appid=xxx');
http.Response response = await http.get(url);
```


### Links
- https://openweathermap.org/
  - OpenWeatherMap
- https://docs.flutter.dev/cookbook/networking/fetch-data
  - Fetch data from the internet
- https://pub.dev/packages/http
  - http package


## JSON

### JSON Viewer Pro
- `JSON Viewer Awesome` extension 명칭이 `JSON Viewer Pro`로 바뀌었다 


### Links
- https://chrome.google.com/webstore/detail/json-viewer-pro/eifflpmocdbdmepbjaopkkhbfmdgijcc
  - JSON Viewer Pro


## Spinner

### Links
- https://pub.dev/packages/flutter_spinkit
  - Flutter Spinkit


## TextField

### Links
- https://docs.flutter.dev/cookbook/forms/text-input
  - Create and style a text field
