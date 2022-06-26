## FLEX 

  헷갈리는 부분들만 정리하기 
  ```html

  <div class="container">
      <div class="flex-item "></div>
    </div>
     <div class="flex-item"></div>
    </div>
     <div class="flex-item"></div>
    </div>
  ```
  ```css
    .container {
      display : flex
    }
  ```
  item들을 감싸고 있는 container에 flex를 적용하면 flex box가 되고 item들은 flex-item이된다. 

  flex item들은 기본적으로 가로 방향으로 배치되며 자신이 가진 내용물의 width 만큼 자리를 차지하게된다.

  height는 컨테이너의 높이만큼 늘어난다. 

## Flex 아이템에 적용하는 속성들

  ### ✏️ 유연한 박스의 기본 영역 - flex-basis 

    > flex basis는 flex 아이템의 기본 크기를 설정합니다. (flex-direction이 row일 때는 너비, column 일 때는 높이). 

  ```css
  .flex-item { 
    flex-basis: auto; 
    /* 기본값 */
  }
  ```

  flex-basis의 값으로는 우리가 width, height 등에 사용하는 각종 단위의 수가 들어갈 수 있고 기본값 auto는 해당 아이템의 width값을 사용한다. width를 따로 설정하지 않으면 컨텐츠의 크기가 됌! 

  ### ✏️ 유연하게 늘리기 - flex-grow

    > flex-grow는 아이템이 flex-basis의 값보다 커질 수 있는지를 결정하는 속성.
      flex-grow에는 숫자값이 들어가는데 몇이든 일단 0보다 큰 값이 세팅이 되면 해당 아이템이 유연한(Flexible) 박스로 변하고 원래의 크기보다 커지며 빈 공간을 메우게 된다! 이걸 적용하지않으면 아이템 자체는 플랙서블하게 움직이지않음!!!

      flex-grow에 들어가는 숫자의 의미는 아이템들이 flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나누어 가진다고 생각하면 된다.

  ### ✏️ 유연하게 줄이기 - flex-shrink

    > flex-gorw와는 다르게 flex-basis의 값보다 작아질 수 있는지를 결정하는 속성. default value = 1 
      flex-shrink를 0으로 세팅하면 아이템의 크기가 flex-basis보다 작아지지 않기 때문에 고정폭의 컬럼을 쉽게 만들 수 있다.
      고정 크기는 width로 설정! 

  ## ✏️ 한번에 사용할 수 있는 flex ! 

    > flex-flow와 같이 이녀석도 한번에 축약형으로 쓸 수 있다.

```css
  .item {
    flex : 1; 

    /* flex-grow: 1 flex-shrink: 1 flex-basis: 0% */

    flex : 1 1 auto;

    /* flex-grow: 1 flex-shrink: 1 flex-basis: auto */

    flex : 1 500px;

    /* flex-grow : 1 flex-shrink: 1 flex-basis: 500px */
  }

``` 

```html
<!-- 반응형 다단컬럼 레이아웃 using flexBox -->
<!DOCTYPE html>
<html lang="ko">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="chrome">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="./default.css">
  <link rel="stylesheet" href="./output.css">
  <title>flex01</title>
  <style>
    .flex-container {
      flex-direction: column;
      display: flex; 
      min-height: 100vh;
    }
    .flex-item {
      flex : 1 auto;
    }
    @media(min-width: 600px) {
      .flex-container {
        flex-direction: row;
        flex-wrap: wrap;
      }
      .flex-item {
        width: 50%;
      }
    }
    @media (min-width: 900px) {
      .flex-item {
        width: 30%;
      }
    }

  </style>
</head>

<body>
  <div class="flex-container">
    <div class="flex-item">aaaaaaaaaaaa</div>
    <div class="flex-item">aaa</div>
    <div class="flex-item">aaaaaaaaaaaa</div>
    <div class="flex-item">aaaa</div>
    <div class="flex-item">aaaaaaaaaaaa</div>
    <div class="flex-item">aaaaaa</div>
    <div class="flex-item">aaaaaaaaaaaaa</div>
    <div class="flex-item">aaaaaa</div>
    <div class="flex-item">aaa</div>
    <div class="flex-item">aaaaaaaaaaaa</div>
  </div>
</body>

</html>

```

  

