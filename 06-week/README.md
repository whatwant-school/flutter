# 14. Boss Level Challenge 3 - Bitcoin Ticker (73min)
 암호화폐의 현재 가치를 실시간으로 받아오는 앱 개발
 
 [Bitcoin Ticker Stub Project](https://github.com/Flearner-flutter/bitcoin-ticker-flutter-flearner)


## Dropdown Button

### Links
- https://api.flutter.dev/flutter/material/DropdownButton-class.html
  - DropdownButton Class


## Loop

### TroubleShooting
- 강의대로 하면 실제 호출할 때 에러가 발생한다
```dart
  List<DropdownMenuItem> getDropDownItems() {
    List<DropdownMenuItem<String>> dropdownItems = [];

    for (String currency in currenciesList) {
      var newItem = DropdownMenuItem(
        child: Text(currency),
        value: currency,
      );

      dropdownItems.add(newItem);
    }

    return dropdownItems;
  }
```
- return 부분에서도 명시적으로 구체적으로 써줘야 한다
```dart
  List<DropdownMenuItem<String>> getDropDownItems() {
    List<DropdownMenuItem<String>> dropdownItems = [];

    for (String currency in currenciesList) {
      var newItem = DropdownMenuItem(
        child: Text(currency),
        value: currency,
      );

      dropdownItems.add(newItem);
    }

    return dropdownItems;
  }
```


### Links
- https://99-bottles-of-beer.net/
  - `99 bottles of beer`라는 동요를 순환문으로 해결하는 challenge 사이트


## Cupertino (iOS-style) widgets

### Links
- https://docs.flutter.dev/development/ui/widgets/cupertino
  - Cupertino (iOS-style) widgets
- https://api.flutter.dev/flutter/cupertino/CupertinoPicker-class.html
  -  CupertinoPicker class


## Boss Level Chanllenge

### Links
- https://www.coinapi.io/
  - CoinAPI
