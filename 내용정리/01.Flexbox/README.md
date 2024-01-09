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

6. align-content

    - 다중 라인 flex 컨테이너에서 라인들의 정렬을 설정하는 데에 유용하다.

    - 즉, 다중라인 컨테이너가 아닐 경우, align-content는 동작하지 않는다.

    - 여러 줄일 때 아이템들의 수직 정렬을 의미한다. flex-start 값을 주면 아이템들은 각 줄의 윗쪽에 배치되고, center로 하면 각 줄의 센터로 배치된다.

7. row-gap 과 column-gap

    - 각 아이템들 사이 여백을 의미한다.

8. order

    - order 태그를 쓰고, 숫자를 적으면 해당 순번으로 배치된다.

    - 단, 기본값이 0이므로 1부터 순서를 주면 맨 뒤로 간다.

    - 음수로 설정해도 가능하다. 오더는 연속적인 숫자가 아니어도 된다. 그냥 작은 수 부터 큰 수 순서로 정렬된다.

9. align-self

    - 해당 태그가 적힌 요소만! 정렬된다.

    * align-items vs align-content vs align-self

    |특징   |align-items|align-content|align-self|
    |-------|---------|----------|----------|
    |적는 위치| 자식 | 부모 | 부모|
    |정렬 대상| 자식 하나만 | 부모에 속한 모든 것| 부모에 속한 모든 것|
    |정렬 효과| 속성에 맞게 요소가 정렬| 속성에 맞게 요소가 정렬| 축이 정렬됨

10. flex-grow

    - 자식 요소에게 차지할 수 있는 공간의 제한을 알려준다.

    - 픽셀과 백분율을 이용하지 않고, 비율만을 사용한다.

    - 부모 요소의 너비를 지정해주지 않았을 때 화면에 보이는 비율 자체를 최대한 가져가려고 한다 (지정해준 비 만큼)

    - default는 0이다.
        - 그래서 div의 width를 지정해주지 않으면, div안에 적힌 내용만큼만 width 가 생기게 되는 것.

11. flex-shrink

    - flex-grow 와 반대요소

    - 숫자를 적어주면, 높은 숫자를 적은 요소가 다른 요소보다 빠르게 줄어든다.

    - default 는 1이다.
        - 그래서 화면을 축소해도 div 안에 있는 요소는 축소가 되지 않는다.

12. flex-basis

    - 박스의 초기 크기를 정한다.

    - 이후 flex-grow를 설정하면, 초기 크기부터 커지기 시작하기 때문에 같은 flex-grow를 가진 요소보다 더 크거나, 작을 수도 있다.

    - 이후 flex-shrink를 설정하면, flex-basis는 min-width와 동일하기 때문에 상자가 줄어들어도 basis에서 적어둔 크기보다 작아지지는 않는다. 

    - flex-grow, flex-shrink, flex-basis 모두 합쳐서 한 곳에 적기
    ```css
        flex: 0 1 500px; //커지지 않고 축소되며 500px이 최대 크기
        flex: 1 0 500px; //축소되지 않고 커지며 500px이 최소 크기
    ```

---------

## [번외] flexbox froggy

css 를 게임으로 익혀볼 수 있는 사이트 : **https://flexboxfroggy.com/#ko** 
