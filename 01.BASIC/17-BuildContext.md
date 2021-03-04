# 완전 초보용 플러터(flutter) 강좌 17 | 아리송한 BuildContext 이해하기
- https://www.youtube.com/watch?v=o-HpnWhI70U


## BuildContext

### 첫번째 정의
- A handle to the location of a widget in the widget tree
  - widget tree에서 현재 widget의 위치를 알 수 있는 정보

- 모든 Widget은 build method를 갖는다
  - build method는 BuildContext parameter를 받는다.
  - return을 보면 Scatfold()를 되돌려 주는 것을 알 수 있다.


### 두번째 정의
- Each widget has its own BuildContext, which becomes the parent of the widget returned by the StatelessWidget.build or State.build function
  - 이 BuildContext는 stateless 위젯이나 state 빌드 메서드에 의해서 리턴 된 위젯의 부모가 된다
