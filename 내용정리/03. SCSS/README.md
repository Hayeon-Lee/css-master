# 03 SCSS

1. SASS 와 SCSS란?

    1. CSS 를 편리하게 사용할 수 있도록 하며, 추가 기능을 제공하는 확장판 스크립트 언어

    2. SASS는 들여쓰기와 줄 바꿈 형식

    3. SCSS는 중괄호와 세미콜론 형식

    4. css 변수를 이렇게 작성할 수 있다.
    ```scss
    $bgColor: red;

    body {
        background-color: var($bgColor);
        padding: 0;
        margin: 0;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
            Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }

    ```


2. Nesting

    1. 직관적으로 코드를 작성할 수 있다.

        * 기존 코드: ul, li, a 의 상하 관계를 모두 적어줘야 했음
        ```scss
        ul {
            list-style-type: none;
            padding: 0;
            display: flex;
            gap: 10px;
        }
        ul li {
                background-color: tomato;
                color: white;
                padding: 5px 10px;
                border-radius: 7px;
        }
        ul li a {
                text-decoration: none;
                color: white;
        }
        ```

        * 바뀐 코드 : ul 내부에 li, li 내부에 a를 적어도 위와 똑같이 작동
        ```scss
        ul {
            list-style-type: none;
            padding: 0;
            display: flex;
            gap: 10px;

            li {
                background-color: tomato;
                color: white;
                padding: 5px 10px;
                border-radius: 7px;

                a {
                text-decoration: none;
                color: white;
                }
            }
        }
        ```
    
    2. 참조 중인 다른 태그를 가리킬 수 있다.

    * &: 를 이용하여 자기 자신을 가리킬 수 있다. 그리고 중첩도 가능하다.
    ```scss
    li {
      background-color: tomato;
      color: white;
      padding: 5px 10px;
      border-radius: 7px;

      &:hover {
        opacity: 0.8;

        a:hover {
          color: grey;
        }
      }
      a {
      text-decoration: none;
      color: white;
      }
    }
    ```