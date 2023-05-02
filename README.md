# JS 100문제 모음집 Part.1
JS 알고리즘 100문제 모음집 1권

## 1. 배열의 삭제
💡 문제 : 다음 배열에서 400, 500를 삭제하는 code를 입력하세요.
```js
const nums = [100, 200, 300, 400, 500];
```
<strong>- 내가 푼 답</strong>
```js
  return nums.slice(0, -2); //slice는 원본배열의 값을 변화시키지 않는다.
```
<br>

## 2. 배열의 내장함수
💡 문제 : 배열 내장함수를 이용하여 코드를 입력하고 다음과 같이 출력되게 하세요.
```js
const arr = [200, 100, 300];
```
<strong>- 내가 푼 답</strong>
```js
  arr.splice(2, 0, 10000);
  console.log(arr);
```
<br>

## 3. 변수의 타입
💡 문제 : 다음 출력 값으로 올바른 것은?
```js
var arr = [100, 200, 300];
console.log(typeof(arr));
```
<strong>- 내가 푼 답</strong>
```js
object 
//Array.isArray(판별하고싶은 데이터)
//Array.isArray() 메서드는 인자가 Array인지 판별한다. true, false로 반환
```
<br>

## 4. 변수의 타입2
💡 문제 : 다음 변수 a를 typeof(a)로 넣었을 때 출력될 값과의 연결이 알맞지 않은 것은?
```js
1)  입력 : a =1,   출력 : number
2)  입력 : a = 2.22,   출력 : boolean
3)  입력 : a = 'p',   출력 : string
4)  입력 : a = [1, 2, 3],   출력 : object
```
<strong>- 내가 푼 답</strong>
```js
2 // number
```
<br>

## 5. for문 계산
💡 문제 : 다음 코드의 출력 값으로 알맞은 것은?
```js
var a = 10;
var b = 2;

for(var i=1; i<5; i+=2){
    a += i;
}

console.log(a+b);
```
<strong>- 내가 푼 답</strong>
```js
16 
// 10 + 1 + 3 + 2 
// i가 2씩 증가하는 것 주의
```
<br>

## 6. false
💡 문제 : 다음은 자바스크립트 문법 중에서 False로 취급하는 것들 입니다.
앗, False로 취급하지 않는 것이 하나 있네요! True를 찾아주세요.
```js
1)  NaN
2)  1
3)  ""
4)  0
5)  undefined
```
<strong>- 내가 푼 답</strong>
```js
2 
// NaN은 거짓 같은 값(Falsy, falsey로 쓰이기도 함) 값은 불리언 문맥에서 false로 평가되는 값이다.
// number에서 0이 아닌 수는 true
// "" 빈 문자열
// undefined 역시 falsy
```
<br>

## 7. 변수명
💡 문제 : 다음 중 변수명으로 사용할 수 없는 것 2개를 고르시오.
```js
1)  age
2)  Age
3)  let
4)  _age
5)  1age
```
<strong>- 내가 푼 답</strong>
```js
3, 5
// let 은 JavaScript의 예약어이다. 
// 숫자로 시작할 수 없다. age1은 가능
```
<br>

## 8. 객체의 키 이름 중복
💡 문제 : 자바스크립트 객체를 다음과 같이 만들었다. 출력값을 입력하시오. (출력값은 공백을 넣지 않습니다.)
```js
var d = {
    'height':180,
    'weight':78,
    'weight':84,
    'temperature':36,
    'eyesight':1
};

console.log(d['weight']);
```
<strong>- 내가 푼 답</strong>
```js
84
// weight에 78 -> 84로 재할당
```
<br>

## 9. concat을 활용한 출력 방법
💡 문제 : 다음 소스 코드를 완성하여 날짜와 시간을 출력하시오.
```js
데이터
var year = '2019';
var month = '04';
var day = '26';
var hour = '11';
var minute = '34';
var second = '27';

var result = //빈칸을 채워주세요

console.log(result);


출력
2019/04/26 11:34:27
```

<strong>- 내가 푼 답</strong>
```js
const result = year.concat('/',month,'/',day,' ',hour,':',minute,':',second) 
console.log(result);
```
```js
const allData = [year,month,day,hour,minute,second]
const date = allData.slice(0,3).join('/')
const time = allData.slice(2, ).join(':')
console.log(date + ' ' + time)
// concat이 번거롭다고 느꼈는데 더 좋은(?) 방법은 없을까?
```
<br>

## 10. 별 찍기
💡 문제 : 크리스마스 날, 은비는 친구들과 함께 파티를 하기로 했습니다. 그런데, 크리스마스 트리를 사는 것을 깜빡하고 말았습니다. 온 가게를 돌아다녀 봤지만 크리스마스 트리는 모두 품절이었습니다. 
하는 수 없이 은비는 프로그래밍으로 트리를 만들기로 합니다. 
```js
입력
5

출력
    *
   ***
  *****
 *******
*********
```
<strong>- 내가 푼 답</strong>
```js
const n = prompt("정수를 입력하세요");
if (!isNaN(n)){
  const integer = parseInt(n)

  for (let i = 1; i <= integer; i++) {
  console.log(' '.repeat(integer - i) + "*".repeat(2 * i - 1));
  }
}
else
  alert("숫자가 아닙니다. 정수를 입력하세요")
  
// 혹시나 유저가 정수 외의 값을 입력할 경우를 대비했다.
// for 반복문의 i를 0부터 시작했더니 '*'을 찍는 과정에서 2 * 0 - 1에서 -인 경우가 발생하여 1부터 시작했다.
// 처음에 if문의 조건을 `(typeof n === 'number')`로 했었는데 정수를 입력해도 else가 실행됐다.
// prompt는 입력을 문자열로 받기 때문에 이런 오류가 발생한 듯 하다.
// 따라서 부정연산자를 사용해 'isNaN' 숫자가 아닌 것을 '부정' -> '숫자이면'으로 수정했다
```
<br>

## 11.  for를 이용한 기본 활용
💡 문제 : 1부터 100까지 모두 더하는 Code를 <pass> 부분에 완성하세요. for를 사용해야 합니다.
```js
let s = 0;

//pass

console.log(s);
```
<strong>- 내가 푼 답</strong>
```js
for (let i=0; i<100; i++){
  s += i
}
```
<br>

  ## 12. 게임 캐릭터 클래스 만들기
💡 문제 : 다음 소스코드에서 클래스를 작성하여 게임 캐릭터의 능력치와 '파이어볼'이 출력되게 만드시오.
주어진 소스 코드를 수정해선 안됩니다.
```js
데이터
<여기에 class를 작성하세요.>

const x = new Wizard(545, 210, 10);
console.log(x.health, x.mana, x.armor);
x.attack();


출력
545 210 10
파이어볼
```
<strong>- 내가 푼 답</strong>
```js
function Wizard(health, mana, armor){
  this.health = health,
  this.mana = mana,
  this.armor = armor,
  this.attack = function(){
    return('파이어볼')
  }
}
const x = new Wizard(545, 210, 10);
console.log(x.health, x.mana, x.armor);
x.attack();
// 생성자 함수
```
```js
 const Wizard = class Wizard {
  constructor (health, mana, armor) {
    this.health = health;
    this.mana = mana;
    this.armor = armor;
  }
  attack() {
    return('파이어볼');
  }
}
const x = new Wizard(545, 210, 10);
console.log(x.health, x.mana, x.armor);
x.attack(); 
 // 클래스
 ```
<br>

## 13.  몇 번째 행성인가요?
💡 문제 : 우리 태양계를 이루고 있는 행성은 수성, 금성, 지구, 화성, 목성, 토성, 천왕성, 해왕성으로 총 8개 입니다. 저희는 우리 태양계의 n번째 행성이 무엇인지 알고 싶습니다.
입력으로 행성의 순서를 나타내는 숫자 n이 입력됩니다. 출력으로 그 순서에 해당하는 행성의 이름을 출력해 주세요. 예를들어 1이 입력되면, 첫번째 행성인 수성이 출력됩니다.
```js
입출력

입력 : 1
출력 : 수성
```
<strong>- 내가 푼 답</strong>
```js
const planet = ['태', '수', '금', '지', '화', '목', '토', '천', '해', '명'];
const n = prompt("정수를 입력하세요");
console.log(planet[n-1]);
}
```
```js
  //질문
const n = parseInt(prompt("정수를 입력하세요"));
const planet = {
  태양:1,
  수성:2,
  금성:3,
  지구:4,
  화성:5,
  목성:6,
  토성:7,
  천왕성:8,
  해왕성:9}

const keysOfPlanet = Object.keys(planet);

const answer = keysOfPlanet.find((key) => planet[key] === n);

console.log(answer);
//planet[key]에서 key가 객체의 키가 아닌, find에서 넘겨주는 변수
//find : 배열을 순환하면서 조건을 만족하는 배열 요소의 값 또는 인덱스 반환
  ```
<br>
  
  
## 14.  3의 배수 인가요?
💡 문제 : 영희는 친구와 게임을 하고 있습니다. 서로 돌아가며 랜덤으로 숫자를 하나 말하고 그게 3의 배수이면 박수를 치고 아니면 그 숫자를 그대로 말하는 게임입니다.
입력으로 랜덤한 숫자 n이 주어집니다. 만약 그 수가 3의 배수라면 '짝'이라는 글자를, 3의 배수가 아니라면 n을 그대로 출력해 주세요.

```js
입력 : 3
출력 : 짝

입력 : 2
출력 : 2
```
<strong>- 내가 푼 답</strong>
```js
const n = parseInt(prompt("정수를 입력하세요"))
if (n%3 === 0){
  console.log('짝')
}
else
  console.log(n)
```
```js
const n = parseInt(prompt("정수를 입력하세요"))
const answer = n%3 === 0 ? '짝' : n
console.log(answer)
```
<br>
  
 ## 15.  자기소개
💡 문제 : 신학기가 시작되고, 아이들이 돌아가면서 자기소개를 하기로 했습니다. 만약 입력으로 김다정이라는 이름이 주어지면 "안녕하세요. 저는 김다정입니다."라고 출력하게 해주세요.
  ```js
 입출력

입력 : 김다정
출력 : 안녕하세요. 저는 김다정입니다.
```
<strong>- 내가 푼 답</strong>
```js
const name = prompt("이름을 입력하세요")
console.log(`안녕하세요. 저는 ${name} 입니다.`)
```
<br>
  
  ## 16. 로꾸꺼
💡 문제 : 문장이 입력되면 거꾸로 출력하는 프로그램을 만들어 봅시다.
```js
입출력

입력 : 거꾸로
출력 : 로꾸거
```
<strong>- 내가 푼 답</strong>
```js
const str = prompt('문장을 입력하세요.')
const rts = str.split('').reverse().join('')
console.log(rts)
//문장을 배열로 전환
//배열의 순서를 뒤집고
//다시 문쟈열로 조인
```
 ```js
const str = prompt('문장을 입력하세요.')
let rts = ''
for (let i = str.length; i>0; i--){
   rts += str[i];
  }
console.log(rts)
//i = str.length로 작성하니까 length와 인덱스의 차이 1 때문에 정의되지 않은 값이 들어가서 `undefined + 거꾸로 된 배열`이 출력됨
//str.length-1로 수정
//i>0 때문에 맨 앞이 짤림
//i>=0 으로 수정
  
const str = prompt('문장을 입력하세요.')
let rts = ''
for (let i = str.length-1; i>=0; i--){
   rts += str[i];
  }
console.log(rts)
 ```
<br>

  ## 17 . 놀이기구 키 제한
💡 문제 : 유주는 놀이공원 아르바이트 중입니다. 그런데 놀이기구마다 키 제한이 있습니다. 유주가 담당하는 놀이기구는 키가 150cm 이상만 탈 수 있습니다. 입력으로 키가 주어지면
키가 150이 넘으면 YES를 틀리면 NO를 출력하는 프로그램을 작성하세요.

<strong>- 내가 푼 답</strong>
```js
const tall = parseInt(prompt('키를 단위 없이 입력하세요. 예시 : 168'))
const answer = tall>150 ? 'YES' : 'NO'
console.log(answer)
```
<br>

## 18. 평균 점수
💡 문제 : 영하네 반은 국어, 수학, 영어 시험을 보았습니다. 영하는 친구들의 평균 점수를 구해주기로 했습니다. 공백으로 구분하여 세 과목의 점수가 주어지면 전체 평균 점수를 구하는 프로그램을 작성하세요. 단, 소숫점 자리는 모두 버립니다.

```js
입력 : 20 30 40
출력 : 30
```
<strong>- 내가 푼 답</strong>
```js
const input = prompt('여러 개의 입력값을 공백으로 구분하여 입력해주세요:');
const inputs = input.split(' ');
let sum = 0;
for (let i = 0; i<inputs.length; i++) {
  sum += Number(inputs[i])
}
console.log(Math.floor((sum/inputs.length)))
```
<br>

## 19. 제곱을 구하자
💡 문제 : 공백으로 구분하여 두 숫자 a와 b가 주어지면, a의 b승을 구하는 프로그램을 작성하세요.

<strong>- 내가 푼 답</strong>
```js
const input = (prompt('두 정수를 공백으로 구분하여 입력하세요 (예시 : 10 2)'));
const toNum = input.split(' ');
console.log(Math.pow(toNum[0], toNum[1]))
```
<br>

## 20. 몫과 나머지
💡 문제 : 공백으로 구분하여 두 숫자가 주어집니다. 두번째 숫자로 첫번째 숫자를 나누었을 때 그 몫과 나머지를 공백으로 구분하여 출력하세요.
```js
입출력

입력 : 10 2
출력 : 5 0
```

<strong>- 내가 푼 답</strong>
```js
const input = (prompt('두 정수를 공백으로 구분하여 입력하세요 (예시 : 10 2)'));
const toNum = input.split(' ');
console.log(parseInt(toNum[0]/toNum[1])+' '+parseInt(toNum[0]%toNum[1]))
```
<br>
  
 ## 21. set은 어떻게 만드나요?
💡 문제 : 다음 중 set을 만드는 방법으로 올바른 것을 모두 고르시오.
```js
1)  var x = {1, 2, 3, 5, 6, 7};
2)  var x = {};
3)  var x = new Set('javascript');
4)  var x = new Set(range(5));
5)  var x = new Set();
 ```
<strong>- 내가 푼 답</strong>
```js
3, 5
// Set은 인자로 iterable(배열, 맵, 집합, 문자열 등)을 받는다.
// Set 객체는 값 콜렉션으로, 삽입 순서대로 요소를 순회할 수 있다. 
// 하나의 Set 내 값은 한 번만 나타날 수 있다.
// 즉, 어떤 값은 그 Set 콜렉션 내에서 유일
```
<br>

## 22. 배수인지 확인하기
💡 문제 : 다음 중 변수 i가 6의 배수인지 확인하는 방법으로 올바른 것은?
```js
1)  i / 6 == 0
2)  i % 6 == 0
3)  i & 6 == 0
4)  i | 6 == 0
5)  i // 6 == 0
 ```
<strong>- 내가 푼 답</strong>
```js
// const i = 6;  
// 1. 1
// 3. AND 비트 연산자(&)는 두 개의 피연산자의 각 자리마다 대응하는 비트가 모두 1일 경우 1을 반환
// 4. i와 6의 비트 OR 연산 결과를 반환. 이 결과는 0 또는 양의 정수
// 5. 몫 연산자. 

```
<br>

  ## 23. OX문제
💡 문제 : console.log(10/3)의 출력 결과는 3이다.
  <br>
  <br>
<strong>- 내가 푼 답</strong>
  <br>
```js
  X : 부동소수점 형태로 반환
```
<br>
  
 
## 24. 대문자로 바꿔주세요!
💡 문제 : 민지는 국제 포럼에서 아르바이트를 하게 되었습니다. 민지는 각 국에서 온 참가자들의 명단을 엑셀로 정리하고 있는데 참가자들 이름이 어떤 이는 전부 소문자, 어떤 이는 전부 대문자로 써져 있는 등 형식이 제각각이었습니다. 민지를 위해 이름이 입력되면 전부 대문자로 출력되는 프로그램을 만들어주세요.

```js
입력 : mary
출력 : MARY
```
<strong>- 내가 푼 답</strong>
```js
const input = prompt('이름을 입력하세요');
console.log(input.toUpperCase());
```
<br>
  
 ## 25. 원의 넓이를 구하세요
💡 문제 : 원의 넓이는 반지름의 길이 x 반지름의 길이 x 3.14로 구할 수 있습니다. 함수를 사용하여 원의 넓이를 구하는 코드를 작성해봅시다. 입력으로 반지름의 길이 정수 n이 주어지면 원의 넓이를 반환하는 함수를 만들어 주세요.
<br>
<br>
<strong>- 내가 푼 답</strong>
```js
const n = parseInt(prompt('반지름을 입력하세요'))
const round = function(r) {
  return(r * r * 3.14)
}
round(n);
```
<br>

 ## 26. 행성 문제2
💡 문제 : 우리 태양계를 이루는 행성은 수성, 금성, 지구, 화성, 목성, 토성, 천왕성, 해왕성이 있습니다.
이 행성들의 영어 이름은 Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune입니다. 행성의 한글 이름을 입력하면 영어 이름을 반환하는 프로그램을 만들어 주세요.
<br>
<br>

<strong>- 내가 푼 답</strong>
```js
const planets = {
	'수성' : 'Mercury',
	'금성' : 'Venus',
	'지구' : 'Earth',
	'화성' : 'Mars',
	'목성' : 'Jupiter',
	'토성' : 'Saturn',
	'천왕성' : 'Uranus',
	'해왕성' : 'Neptune',
};

const name = prompt("행성의 이름을 입력하세요.");
console.log(planets[name]);
```
<br>

 ## 27. 객체 만들기
💡 문제 : 첫번째 입력에서는 학생의 이름이 공백으로 구분되어 입력되고, 두번째에는 그 학생의 수학 점수가 공백으로 구분되어 주어집니다. 두 개를 합쳐 학생의 이름이 key이고 value가 수학 점수인 객체를 출력해주세요.

<br>
<br>

```js
입력
Yujin Hyewon
70 100

출력
{'Yujin': 70, 'Hyewon': 100}
```

<strong>- 내가 푼 답</strong>

```js
const name = prompt('학생들의 이름을 공백으로 구분하여 입력하세요.').split(' ')
const grade = prompt('점수를 이름의 순서에 맞게 공백으로 구분하여 입력하세요.').split(' ')
let myObj = {}; 
for(let i = 0; i < name.length; i++) {
    myObj[name[i]] = parseInt(grade[i]);
}
console.log(myObj);
```
<br>


 ## 28. 2-gram
💡 문제 : 2-gram이란 문자열에서 2개의 연속된 요소를 출력하는 방법입니다. 예를 들어 'Javascript'를 2-gram으로 반복해 본다면 다음과 같은 결과가 나옵니다.

<br>

```js
입력
Javascript

출력
J a
a v
v a
a s
s c
c r
r i
i p
p t
```
<strong>- 내가 푼 답</strong>

```js
const a = prompt('문자를 입력하세요');
const arr = [...a];
    arr.forEach((e, index) => {
  if (index < arr.length - 1) {
    console.log(arr[index] + ' ' + arr[index + 1]);
  }
});
```
<br>

## 29. 대문자만 지나가세요
💡 문제 : 진구는 영어 학원 아르바이트를 하고 있습니다. 반 아이들은 알파벳을 공부하는 학생들인데 오늘은 대문자 쓰기 시험을 봤습니다. 알파벳 하나만을 입력하고 그 알파벳이 대문자이면 YES를 아니면 NO를 출력하는 프로그램을 만들어 주세요.

<br>

<strong>- 내가 푼 답</strong>
```js
const al = prompt('알파벳을 한 개 입력하세요.');
(al.charCodeAt(0) < 91 && al.charCodeAt(0) > 64) ? 'YES' : 'No' 
```
<br>

## 30. 문자열 속 문자 찾기
💡 문제 : 문자 pineapple에는 apple이라는 문자가 숨어 있습니다. 원범이는 이렇듯 문자열 속에 숨어있는 문자를 찾아보려고 합니다. 첫번째 입력에서는 문자열이 입력되고, 두번째에는 찾을 문자가 입력되어야 합니다. 그 문자가 시작하는 index를 반환하는 프로그램을 만들어 주세요
<br>

<strong>- 내가 푼 답</strong>
```js
const fullstr = prompt('문자열을 입력하세요');
const str = prompt('찾을 문자를 입력하세요');

console.log(fullstr.indexOf(str)); 
//indexOf는 찾은 문자의 
```
	
```js

```
<br>
