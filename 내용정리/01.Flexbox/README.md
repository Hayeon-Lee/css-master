# 01 Flexbox

1.  display 속성

    - block: width 와 height를 갖고, 옆에 그 어떤 요소도 허용하지 않는다.
    - inline: text와 같다. width와 height를 가질 시 화면에 나타나지 않는다.
    - inline-block: width와 height를 가질 수 있고, block임에도 옆으로 나열이 가능하다.

2.  flexbox 코드를 적는 규칙

    - 자식 요소가 아닌, 직속 부모 요소에 프로퍼티를 적는다.

    - 방향에 따른 프로퍼티를 적절하게 써주어야 한다.

    - 자식들이 공통적으로 갖는 특성은 부모 속성 안에 넣어줄 것

3.  flex-direction

    - 기본 방향은 row, 수직은 column이다.

    - main axis: flex-direction과 같은 방향 -> **justify-content**

    - cross axis: flex-direction과 수직인 방향 -> **align-items**

    - 정렬과 관련된 프로퍼티들은 축이 변하면 해당 축에서 적용된다.

4.  flex-wrap

    - 컨테이너가 한 줄인지 다중 줄인지를 정해주는 요소이다.

    - 기본값: nowrap 이기 때문에 flex box는 기본적으로 한 줄에 모든 요소를 넣고자 한다.

    - wrap으로 바꿀 시: 한 줄이 아닌 여러 줄로 요소를 배치한다.

    - wrap-reverse로 바꿀 시: 뒤집어서, 여러 줄로 나온다.

5.  flex-flow

    - flex-direction과 flex-wrap을 합친 속성이다. 두 값을 함께 적어주면 됨.

    - flex-flow: row wrap

      -> flex-direction은 가로, 요소들은 여러 줄로 나타난다.
