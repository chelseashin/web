## JavaScript_시작



2019-06-02

----

< SSAFY & 생활코딩 Web2 - Javascript >

 `HTML`은 웹이 만들어져서 보여지는 가장 정적인 형태의 웹페이지이다. 여기에서 그치지 않고 인간은 더욱 Dynamic한(동적인) 페이지를 만들기를 갈망했고, 그렇게 해서 나오게 된 것이 바로 `JavaScript`이다.  



### Intro

1. Javascript(이하 JS)는 브라우저를 동적으로 사용하기 위해 고안된 언어이다.
2. Java의 유명세를 없기 위해 지어진 이름일 뿐, 둘은 전혀 관련/유사성이 없다.
3. ECMA Script(이하 ES)는 브라우저마다 파편화되어가고 있는 JS생태계를 정리하기 위해 ECMA가 제시한 표준안이다. 즉 ES6 는 ECMA 가 제안하는 JS의 표준 ver.6 이라는 의미이다.
4. ES5(2009)에서 ES6+(2015~)로 넘어가는 중이다. (아직도 ES5 표준으로 작성된 참고자료가 많다.)
5. 우리는 ES6+ 의 표준을 기준으로 학습한다.
6. IE 는 HTML5 표준과 ES6 표준 두가지 모두 매우 안 지킨다.
7. 브라우저 console 에서 바로 사용할 수 있는 JS를 Vanilla JS라고 부른다. (Vanilla 아이스크림 === 순정) Vanilla JS 는 프로그래밍을 통해 BOM 조작, DOM 조작을 할 수 있다.
8. 브라우저라는 제한된 환경을 넘어 브라우저 밖(컴퓨터)에서 JS를 구동할 수 있는 새로운 실행 환경(runtime env)인 **Node.js** 가 등장한다. (Node.js 환경에서는 당연히 DOM, BOM 조작 불가능)
9. Node.js 의 등장과 웹 app이 다시 주목받는 등 여러가지 요인으로 인하여 JS는 [2018 StackOverflow 설문조사 기준 가장 인기있는 프로그래밍 언어다.



* `Javascript` 소개

자바스크립트를 사용하여 웹 프로그래밍에서 할 수 있는 일은 다음과 같이 매우 다양하다.

1. 자바스크립트는 HTML의 '내용'을 변경할수 있다.
2. 자바스크립트는 HTML의 '속성'을 변경할수 있다.
3. 자바스크립트는 HTML의 '스타일'을 변경할수 있다.



* `Javascript` 역할 및 특징
  - 사용자와 상호작용하는 웹페이지 구현
  - 동적인 페이지 구현
  - HTML을 제어하는 언어
  - 객체지향언어.
  - 컴파일 과정을 거치지 않는다.
  - front와 back 구현 모두 가능한 언어로, 가장 선호도 높고 점유율이 높다.



#### HTML과 JavaScript의 만남 1(script 태그)

 JavaScript는 기본적으로 HTML위에서 동작하는 언어이다. 어떻게 하면 HTML에 완전히 다른 문법을 가지고 있는 Javascript를 끼워넣을 것인지에 대해서 생각해보자.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>JavaScript</h1>
    <!-- javascript -->
    <script>
        document.write('hello world!');
        document.write(1 + 1);
    </script>
    <!-- html과 어떻게 다른지 확인 -->
    <h1>html</h1>
    hello world!
    1 + 1
</body>
</html>
```



 JavaScript는 `1 + 1`를 더하여 화면에 띄워주는 역할을 한다. 반면 HTML에서 `1 + 1`을 하면 영원히 '1+1'이다. JavaScript는 연산까지하여 웹에 띄워준다. JavaScript에서 웹페이지에 어떤 글씨에 출력할 때 document.write를 사용한다. 이 부분이 html파일에서 자바스크립트라는 것을 알려주기 위해서 `<script> </script>`를 사용한다는 것을 알아두자. 



#### HTML과 JavaScript의 만남 2(이벤트)

JavaScript가 사용자와 상호작용하는데 핵심적인 역할!

* onclick 속성에는 무조건 JS 속성값. 사용자가 클릭했을 때 웹브라우저가 JS code에 따라 기억하고 있다가 동작하는 것.
* 웹브라우저 위에 일어나는 일들 : 사건(Event)
* 웹브라우저 위에서 일어나는 여러가지 사건(Event)인데 그 중에 기념할만한 것들을 정의해 놓고 있음. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <input type="button" value="hi" onclick="alert('Hello world!')">
    <input type="text" onchange="alert('changed')">
    <input type="text" onkeydown="alert('key down!')">
</body>
</html>
```



* Event Listener
  * `click` – 마우스버튼을 클릭하고 버튼에서 손가락을 떼면 발생한다. 
  * `mouseover` – 마우스를 HTML요소 위에 올리면 발생한다. 
  * `mouseout` – 마우스가 HTML요소 밖으로 벗어날 때 발생한다. 
  * `mousemove` – 마우스가 움직일때마다 발생한다. 마우스커서의 현재 위치를 계속 기록하는 것에 사용할 수 있다. 
  * `keypress` – 키를 누르는 순간에 발생하고 키를 누르고 있는 동안 계속해서 발생한다.
  * `keydown` – 키를 누를 때 발생한다.
  * `keyup` – 키를 눌다가 떼는 순간에 발생한다.
  * `load` – 웹페이지에서 사용할 모든 파일의 다운로드가 완료되었을때 발생한다. 
  * `scroll` – 스크롤바를 드래그하거나 키보드(up, down)를 사용하거나 마우스 휠을 사용해서 웹페이지를 스크롤 할 때 발생한다. 페이지에 스크롤바가 없다면 이벤트는 발생하지 않다. 
  * `change` – 폼 필드의 상태가 변경되었을 때 발생한다. 라디오 버튼을 클릭하거나 셀렉트 박스에서 값을 선택하 는 경우를 예로 들수 있다. 
  * `input` - input 또는 textarea 요소의 값이 변경되었을 때 
  * `submit` - form을 submit 할 때



1. DOM selector 

   * querySelector() 
   * querySelectorAll()

2. 이벤트 리스너 등록 

   * 특정한 DOM element(무엇을)를 어떠한 행동을 했을 때(언제), 어떻게 한다.

   ```javascript
   // 1. 무엇을 
   const button = document.querySelector('#some-button')
   // 2. 언제 => 버튼을 '클릭' 하면 
   button.addEventListener('click', function (event) {    
       const area = document.querySelector('#my')    
   // 3. 어떻게 => 뿅    
       area.innerHTML = '<h1>뿅</h1>' })
   ```

   * 이벤트 리스너에서의 콜백함수에는 arrow function 을 사용하지 않는다. 



#### HTML과 JavaScript의 만남 3(콘솔)

* 콘솔(Console)

  * 가벼운 상황에 사용

  * 파일을 만들지 않고 JS code를 즉석으로 실행시켜 볼 수 있음.

  * 웹에서 `F12`를 누르고 Console창을 열어볼 수 있음. 

  * 문자의 갯수를 경고창으로 알려주는 코드

    ```javascript
    alert('The World Wide Web (abbreviated WWW or the Web) is an information space where documents and other web resources are identified by Uniform Resource Locators (URLs), interlinked by hypertext links, and can be accessed via the Internet.[1] English scientist Tim Berners-Lee invented the World Wide Web in 1989. He wrote the first web browser computer program in 1990 while employed at CERN in Switzerland.[2][3] The Web browser was released outside of CERN in 1991, first to other research institutions starting in January 1991 and to the general public on the Internet in August 1991.'.length)
    
    // 결과 : 582
    ```

   `Console`이라는 것을 통해 JS를 작성하여 보고있는 웹페이지를 대상으로 해서 JS를 실행할 수 있다는 것을 볼 수 있었다. 



----

**단순하면서도**
**중요한 것들만 가지고 있고**
**그러면서 다양한 곳에서 사용되고 있는**
**세상에서 제일 많이 쓰이는 언어** 

**지금은 자바스크립트의 시대!!!**

 우리가 웹 페이지를 JavaScript를 이용한다는 것은 웹페이지를 만드는 것처럼 거대한 목표일 수도 있지만 이미 만들어져 있는 웹사이트를 나의 어떤 필요에 의해 맥락적으로 간단하면서도 허접하지만, 나에게 딱 맞는 코드를 작성해서 이 문제를 해결할 수 있다는 것이다. 우리가 코딩을 해서 더 얻을 수 있는 효용은 나의 현실의 문제를 해결하는 수많은 단계의 일들을 가볍게 해결하는 방법으로 사용할 수 있다는 말이 굉장히 와닿았다.

 결국은 우리가 코딩을 하는 이유는 어떠한 원하는 것을 웹상에서 이루기 위해서가 아니겠는가. 코딩이 현실에서 일어나는 아주 작은 문제에서부터 큰 문제 까지를  해결하기 위한 아주 훌륭하고 혁신적인 도구가 될 수 있다는 것을 다시 한 번 되새길 수 있었다. :smiley: