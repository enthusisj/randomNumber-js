# 자바스크립트(javascript)
자바스크립트(JavaScript)는 **객체(object)** 기반의 스크립트 언어이다.

HTML로는 웹의 내용을 작성하고, CSS로는 웹을 디자인하며, 자바스크립트로는 **웹의 동작**을 구현할 수 있다.

자바스크립트는 주로 웹 브라우저에서 사용되나, Node.js와 같은 프레임워크를 사용하면 서버 측 프로그래밍에서도 사용할 수 있다.

현재 컴퓨터나 스마트폰 등에 포함된 대부분의 웹 브라우저에는 자바스크립트 인터프리터가 내장되어 있다.   


# 로또 번호 추첨기
### 자바스크립트를 사용해서 1~45공 중 6개 뽑는 로또 번호를 만들어보자.   
   

```javascript 
    <body>
        <script>
        //자바 스크럽트
        </script>
    </body>
```
먼저, javascript는 body구문 안에 script를 써서 쓰고자 하는 자바스크립트언어를 작성한다.   

```javascript
     <body>
        <script>
            var lotto=[];
        </script>
    </body>
```   
그 다음, 변수 선언을 해준다.   
이때 6개의 숫자를 나타내기 위해 배열을 쓴다.


```javascript
      <body>
        <script>
            var lotto=[];
            while(lotto.length <6){
                var num=parseInt(Math.random()*45+1)
            }
        </script>
    </body>
```
1부터 45까지의 정수형 숫자를 반복해서 6개의 숫자가 나와야 한다.   
.length는 배열의 길이를 나타내는데 배열의 첫번째 인덱스는 0이므로 6개를 나타내려면 6보다 작다고 표시해야한다.   
parseInt(); 는 소수점은 버리고 정수로 변환해주는 함수이다.   
반복문은 for()과 while()문으로 쓸 수 있는데 여기서 for문을 쓰게 된다면, 추첨공이 6개가 나와야하는데 안나올 수 있다. 이런 문제를 막기위해  while문을 써야한다.   



만약, 
```javascript
    var num=parseInt(Math.random()*45)
```

이렇게 쓰면 0부터 45미만의 숫자가 발생하므로 +1을 해줘야한다.   

```javascript
    <body>
        <h1>로또 번호 추첨기 </h1>
        <script>
           
           var lotto=[];
           while(lotto.length <6){
               var num=parseInt(Math.random()*45+1)
               if(lotto.indexOf(num)== -1){
                   lotto.push(num);
               }
           }
           lotto.sort((a,b)=>a-b);
        </script>
    </body>
```
추첨공이 중복되는 것을 막기위해 .indexOf(값)함수를 쓴다. 값이 있으면 위치, 없으면 -1을 해서 인덱스의 위치를 지정해준다.   
.push()는 마지막 값을 추가해주는 함수이다.   
.sort((a,b)=>a-b)는 오름차순으로 정렬해주는 함수이고, b-a를 하면 내림차순으로 정렬해주는 함수이다.  

만약, .sort()함수만 쓰면?   
```javascript
    lotto.sort();
```
[1,2,3,11.22,33]을 배열에 넣어다고 하자. 결과는 [1,11,2,22,3,33]이 된다.  

```javascript
    document.write();
``` 
를 써서 출력을 하게 한다.

## 전체 코드
```html
<!DOCTYPE html>
<html lang="ko">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>로또 번호 추첨기 </title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>로또 번호 추첨기 </h1>
        <script>
           
           var lotto=[];
           while(lotto.length <6){
               var num=parseInt(Math.random()*45+1)
               if(lotto.indexOf(num)== -1){
                   lotto.push(num);
               }
           }
           lotto.sort((a,b)=>a-b);
           document.write("<div class='ball ball1'>"+lotto[0] + "</div>");
           document.write("<div class='ball ball2'>"+lotto[1] + "</div>");
           document.write("<div class='ball ball3'>"+lotto[2] + "</div>");
           document.write("<div class='ball ball4'>"+lotto[3] + "</div>");
           document.write("<div class='ball ball5'>"+lotto[4] + "</div>");
           document.write("<div class='ball ball6'>"+lotto[5] + "</div>");
        </script>
    </body>
</html>
```

## 실행결과
![logo](/javascript/result.jpg"result")  

