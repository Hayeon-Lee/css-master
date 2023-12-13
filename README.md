# CSS MASTER

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

6. grid

    - display: grid 로 설정 가능하다.

    ```css
        display: grid;
        grid-template-columns: 100px 200px;
        grid-template-rows: 200px 100px;
        gap: 10px;
    ```

    - 기본적으로 하나의 요소는 하나의 행과 열만을 차지하게 된다. 
    
    - 아래와 같이 코드를 적으면 변경이 가능하다.

    - 아래와 같이 요소를 추가하면서 그려지는 박스의 크기를 조절할 수 있다.

    ```css
        grid-column-start:1;
        /*세로줄의 시작을 1번 라인으로 결정한다.*/
        grid-column-end: 4
        /*4번째 세로줄까지 그려진다*/
        grid-column-end: -1
        /*가장 마지막 세로줄까지 그려진다*/
    ```

    ```css
        grid-row-start: 1;
        /*가로줄의 시작을 1번 라인으로 결정한다.*/
    ```

7. grid의 line name

    - [] 안에 이름을 적어준다. 아래의 코드를 참고한다.

    ```css
        grid-template-columns: [tomato] 100px [banana] 200px [berry] 50px [lemon];
    ```

    - 위의 코드대로 작성하면, 개발자 모드에서 컬럼의 이름을 확인할 수 있다.

    - 라인의 이름을 결정하면, 코드를 더욱 직관적으로 작성할 수 있어 편리하다.

    ```css
        grid-column: tomato / lemon;
        /*tomato 라인부터 lemon 라인까지 그려진다.*/
    ```