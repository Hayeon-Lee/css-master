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

6.  grid

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

7.  grid의 line name

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

8.  grid template

    - grid의 비율을 픽셀로 하드코딩 하지 않아도 된다.

    - grid-template-columns는 기본적으로 viewport를 기준으로 나뉜다.

    - grid-template-rows는 세로줄이 기준인데, 이는 끝이 없기 떄문에 height를 지정해줘야 한다.

    ```css
    grid-template-columns: 1fr 1fr 1fr 1fr;

    height: 100px;

    grid-template-rows: 1fr 1fr 1fr 1fr;
    ```

    - **grid-template-areas**

      - 행과 열을 미리 정할 수 있다.

      - 템플릿을 정해준 뒤에는, 해당 자리에 넣을 요소의 css에 grid-area로 특성을 적어줘야 한다.

    ```css
    grid-template-columns: 1fr 1fr 1fr 1fr;

    grid-template-rows: 1fr 1fr 1fr;

    grid-template-areas: 
         'header header header header'
         'content content content menu'
         'footer footer footer footer';
    ```

    ```css
    header {
      grid-area: header;
    }

    box {
      grid-area: content;
    }
    ```

    위처럼 row와 column을 하나하나 정해주지 않고, 더 간단하게 적을 수 있다.

    ```css
    grid-template:
      'a a a a' 1fr
      'b b b c' 2fr
      'd d d d' 1fr / 1fr 1fr 1fr 1fr;

    /*위처럼 적으면, 행과 열의 크기를 하나하나 지정해주지 않고 행의 크기 열의 크기를 한 번에 grid-template 안에 적을 수 있다.*/
    ```

9.  < span > 키워드

    - 아래처럼 적으면 자동으로 행을 2개 차지하게 된다.

    - 두 번째 코드는 열을 2개 차지하게 된다.

    ```css
    grid-row: span 2;
    grid-column: span 2;
    ```

    - 아래처럼 적으면 시작 라인도 적을 수 있다.

    ```css
    grid-column: potato / span 2;
    ```

10. auto columns and rows

    - 아래처럼 코드를 짰을 때, 4개의 div는 grid 안에 들어가지만 남은 5와 6은 정해진 크기대로 되지 않는다.

    ```html
    <div class="father">
      <div class="child">1</div>
      <div class="child">2</div>
      <div class="child">3</div>
      <div class="child">4</div>
      <div class="child">5</div>
      <div class="child">6</div>
    </div>
    ```

    ```css
    .father {
      display: grid;
      gap: 10px;
      min-height: 50vh;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(2, 1fr);
      /*
        세로줄이 1fr 씩 2개 만들어진다
        가로줄이 1fr 씩 2개 만들어진다
        */
    }

    .child {
      background-color: tomato;
      color: white;
      font-size: 28;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    ```

    - 이 때, 아래처럼 css를 수정하면 div를 몇 개씩 더 추가해도 원래 grid에 들어가진다.

    ```css
    .father {
      display: grid;
      gap: 10px;
      min-height: 50vh;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(2, 1fr);
      grid-auto-rows: 1fr; /*기존 크기보다 더 추가되면 가로줄 자동으로 1fr 생김*/
      grid-auto-columns: 1fr; /*마찬가지로 세로줄 자동으로 1fr 생김*/
      grid-auto-flow: column; /*방향이 세로방향으로 추가됨, default는 row*/
    }
    ```

11. Align and Justify Items

    - grid cell 안에 있는 요소가 width와 height를 가질 경우 적용 가능하다.

    ```css
    justify-items: stretch;
    /*default: stretch
     그리드 셀 안의 내용물을 가로 방향 정렬
    */

    align-items: stretch;
    /*default: stretch
    그리드 셀 안의 내용물을 세로 방향 정렬*/

    place-items: end end;
    /*align과 justify를 한 번에 지정 가능*/

    place-self: start end;
    /*이 요소를 갖는 개체 자체의 algin과 justify를 한 번에 지정 가능*/
    ```

12. Align and Justify Content

    - 그리드 컨테이너 자체를 정렬하는 것

    ```css
    align-content: center;
    /*세로에 남는 공간이 생길 경우, 그리드 컨테이너가 세로 중앙 정렬된다.*/

    justify-content: center;
    /*가로에 남는 공간이 생길 경우, 그리드 컨테이너가 가로 중앙 정렬*/

    place-content: start end;
    /*align-content와 justify-content를 한 번에 정렬할 수 있다.*/
    ```

    **items 는 grid 안의 아이템을, content는 grid 자체를 정렬한다.**

13. auto sizing and minmax

    - 내용물의 사이즈에 따라 열 크기를 조절할 수 있는 키워드

    ```css
    grid-template-columns: 1fr max-content 1fr;
    /*두 번째 열은 내부 내용물 총 길이만큼 넓어진다*/
    ```

    ```css
    grid-template-columns: 1fr min-content 1fr;
    /*두 번째 열은 내부 내용물의 가장 긴 단어의 길이만큼 넓어진다*/
    ```

    - 화면이 변하여도 가운데 열이 250px보다는 작아지지 않아야한다.

    ```css
    grid-template-columns: 1fr minmax(250px, 1fr) 1fr;
    ```

14. Auto Fill and Auto Fit

    - 반응형 그리드를 생성할 수 있다. repeat()와 함께 쓰인다.

    - auto-fit: 남는 공간을 축소한다. 지정한 모양을 무시하고 남는 공간을 모두 없애서 꽉 채워버린다.

    - auto-fill: 남는 공간을 유지한다. 빈 공간을 지정한 셀로 최대한 채운다. 속이 비어있어도 컨테이너를 가능한 많이 채운다.

    ```css
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    ```
