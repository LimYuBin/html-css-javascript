# 변수 작성법
* const : 절대로 바뀌지 않는 상수, 수정할 수 없음
<pre><code>const PI = 3.14;
const birthday = "1999-02-03";
</code></pre>
* let : 변할 수 있는 값

*  \`${변수명}` : 다른 변수 가져올 수 있음
<pre><code>const name = "Mike";
const message = `my mame is ${name}`;
const message = `나는 ${20+3}살 입니다.`;
</code></pre>

1. 변수는 문자, 숫자, $, _ 만 사용 가능
2. 첫글자는 숫자 불가능
3. 예약어 사용 불가능
4. 가급정 상수는 대문자로
5. 변수명은 읽기 쉽고 이해할 수 있게

* typeof 연산자
    *  내가 작성한 코드이면 상관 없지만, 다른 개발자가 작성한 코드의 자료형을 알아야할 때 사용
<pre><code>console.log(typeof 3); //number
console.log(typeof true); //boolean
console.log(typeof "xxx"); //string
console.log(typeof null); //object
console.log(typeof undefined); //undefined
</code></pre>

# 형변환
* String() : 문자형으로 변환
* Number() : 숫자형으로 변환
* Boolean() : 불린형으로 변환

# 대화상자
* alert(메시지) : 알려줌
* prompt(메시지, default 값) : 입력 받음
* confirm(메시지) : 확인 받음
<pre></code>const name = prompt("이름을 입력하세요.");
alert("환영합니다, " + name + "님");
alert(`환영합니다 ${name}님`);
const isAdult = confirm("당신은 성인입니까?");
console.log(isAdult); //확인 누르면 true, 취소 누르면 false
</code></pre>

# 논리연산자
* || : OR
* && : AND
* ! : NOT

* 논리연산자를 사용할 때, 성능 최적화 고려해야 함
    * 운전면허가 있고 시력이 좋은 여군 
     * -> 여군인데 시력이 좋고 운전면허가 있는 사람

# 조건문
* if 문
<pre></code>const age = 20;

if(age>20){
    console.log("환영합니다.");
} else if(age === 20) {
    console.log("반가워요")
} else {
    console.log("안녕히가세요.");
}
</code></pre>

* switch 문
<pre></code>let fruit = prompt("무슨 과일을 사고 싶나요?");

switch(fruit) {
    case "사과":
        console.log("100원 입니다.");
        break;
    case "바나나":
        console.log("200원 입니다.");
        break;
    case "수박":
        console.log("300원 입니다.");
        break;
    default:
        console.log("그런 과일은 없습니다.");
}
</code></pre>

# 반복문
* for 문
<pre><code>for(초기값, 조건, 코드 실행 후 작업) {
    //반복할 코드
}
</code></pre>

* while 문
<pre><code>let i = 0;
while(i<0) {
    //코드
    i++;
}
</code></pre>
* do while 문
<pre><code>let i = 0;
do {
    //코드
    i++;
} while(i<10)
</code></pre>

* break : 멈추고 빠져나옴
* continue : 멈추고 다음 반복으로 진행
<pre><code>while(true) {
    let answer = confirm("계속 할까요?");
    if(!answer) {
        break;
    }
}

for(let i=0; i<10; i++) {
    if(i%2) {
        continue;
    }
    console.log(i)
}
</code></pre>

# 함수
* 함수 선언문 : 어디서든 호출 가능 (선언문 위, 아래 다)
<pre><code>function sayHello(name) {
    console.log(`Hello, ${name}`);
    return; //함수 중간에 return 만나면 거기까지만 실행
    console.log("Hi");
}

sayHello('Mike'); //Hello, Mike
</code></pre>

* 함수 표현식
<pre><code>let sayHello = function(name) {
    console.log(`Hello, ${name}`);
}

sayHello('Mike'); //Hello, Mike
</code></pre>

* 화살표 함수
<pre><code>let sayHello = (name) => {
    console.log(`Hello, ${name}`);
}

sayHello('Mike'); //Hello, Mike
</code></pre>

# 객체
* 선언
<pre><code>const superman = {
    name : "clark",
    age: 33,
    fly: function() {
        console.log(`${this.name}가 날아갑니다.`) //this는 객체, 화살표 함수에서는 this 사용 불가능
    }
}
</code></pre>

* 접근
<pre><code>superman.name //clark
superman["age"] //33
</code></pre>

* 추가
<pre><code>superman.gender = "male"
superman["hairColor"] = "black"
</code></pre>

* 삭제
<pre><code>delete superman.hairColor;
</code></pre>

* 확인 : for ~ in (객체를 순회)
<pre><code>//개별로 확인
'birthday' in superman //false
'age' in superman //true

//한번에 확인
for(x in superman) {
    console.log(x); //name, age
}
for(x in superman) {
    console.log(superman[x]); //clark, 33
}
</code></pre>

# 배열 Array
* 배열은 문자, 숫자,  객체, 함수 등도 포함 가능
<pre><code>let students = ["철수", "영희", "영수"];
console.log(students[0]); //철수
console.log(students[1]); //영희
console.log(students[2]); //영수

students[0] = "민정" //수정
students.push("화정") //맨 뒤에서 추가
students.pop(); //맨 뒤에서 삭제
students.unshift("선호"); //맨 앞에서 추가
students.shift(); //맨 앞에서 삭제
console.log(student.length); //길이
</code></pre>

* for ~ of (배열을 순회)
<pre><code>let days = ["월", "화", "수"];

for(let day of days) {
    console.log(day);
}
</code></pre>
