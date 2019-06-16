## JavaScript - Ajax적용_fetch API _hash



2019-06-16

------

< 생활코딩 Web3 - Javascript - Ajax >



## Ajax 적용



#### * 초기 페이지 구현 - index.html

```html
<!-- <h1><a href="index.html">WEB</a></h1> -->
  <h1><a href="#!welcome">WEB</a></h1>
  <input id="night_day" type="button" value="night" onclick="
    nightDayHandler(this);
  ">
  <div id="grid">
    <ol id="nav">
      <!-- 방법 1 - 기본(동기화) -->
      <li><a href="1.html">HTML</a></li>
      <li><a href="2.html">CSS</a></li>
      <li><a href="3.html">JavaScript</a></li>
        
      <!-- 방법 2 - fetch API 적용(비동기화) -->
      <li><a onclick="
          fetch('html').then(function(response){
            response.text().then(function(text){
              document.querySelector('article').innerHTML = text;
            })
          });
        ">HTML</a></li>
        <li><a onclick="
          fetch('css').then(function(response){
            response.text().then(function(text){
              document.querySelector('article').innerHTML = text;
            })
          });
        ">CSS</a></li>
        <li><a onclick="
          fetch('javascript').then(function(response){
            response.text().then(function(text){
              document.querySelector('article').innerHTML = text;
            })
          });
        ">JavaScript</a></li>
        
      <!-- 방법 3 - 리팩토링(함수화) -->
      <!-- # : 북마크기능 / ! : hash bang -->
      <!-- hash bang을 이용해서 어떤 사이트에 처음 들어왔을 때 초기 페이지를 로드하는 방법 -->
      <li><a href="#!html" onclick="fetchPage('html')">html</a></li>
      <li><a href="#!css" onclick="fetchPage('css')">css</a></li>
      <li><a href="#!javascript" onclick="fetchPage('javascript')">javascript</a></li>
    </ol>
    <article>

    </article>
    <script>
    function fetchPage(name){
      fetch(name).then(function(response){
        response.text().then(function(text){
          document.querySelector('article').innerHTML=text;
        })
      })
    }
    if(location.hash){
      fetchPage(location.hash.substr(2));
    } else {
      fetchPage('welcome');
    }
    </script>
```

