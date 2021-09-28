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

# 생성자 함수
* 객체를 생성할 수 있음
* new 연산자로 호출
<pre><code>function User(name, age) {
    this.name = name;
    this.age = age;
    this.sayName = function() {
        console.log(this.name)
    }
}

let user1 = new User("Mike", 30); //new 연산자로 호출
let user2 = new User("Jane", 22);
let user3 = new User("Tom", 17);
user3.sayName(); //Tom
</code></pre>

# 계산된 프로퍼티(Computed Property)
<pre><code>let a = "age";
const user = {
    name: "Mike",
    [a]: 30, //Computed Property
    ["안녕"+"하세요"]: "Hello" //Computed Property
}
</code></pre>

# 객체 메소드(Object Method)
* Object.assign() : 객체 복제
<pre><code>const user = {
    name: "Mike",
    age: 30
}

const cloneUser = user; //이렇게 하면 동시에 참조돼서 안됨
const newUser = Object.assign({}, user); //복제 완료
</code></pre>
* Object.keys() : 키를 배열로 만들어 반환
<pre><code>const user = {
    name: "Mike",
    age: 30,
    gender: "male"
}

Object.keys(user); //["name", "age", "gender"]
</code></pre>
* Object.values() : 값을 배열로 만들어 반환
<pre><code>const user = {
    name: "Mike",
    age: 30,
    gender: "male"
}

Object.values(user); //["Mike", 30, "male"]
</code></pre>
* Object.entries() : 키와 값을 배열로 만들어 반환
<pre><code>const user = {
    name: "Mike",
    age: 30,
    gender: "male"
}

Object.entries(user); //[["name", "Mike"], ["age", 30], ["gender", "male"]]
</code></pre>
* Object.fromEntries() : 키 값 배열을 넣으면 객체로 만들어줌
<pre><code>const arr =[
    ["name", "Mike"],
    ["age", 30], 
    ["gender", "male"]
];

Object.fromEntries(arr); //{
    name: "Mike", 
    age: 30, 
    gender: "male"
}
</code></pre>

# 심볼
* Symbol() : 유일한 식별자를 만들 때 사용
<pre><code>const a = Symbol(심볼명); //new 사용안함
const b = Symbol(심볼명);

a === b; //false
a ==b; //false
a.description; //심볼명 반환(전역 심볼 아닐 때)
</code></pre>

* Symbol.for(심볼명) : 전역 심볼
<pre><code>const id1 = Symbol.for("id");
const id2 = Symbol.for("id");

id1 === id2; //true
</code></pre>

* Symbol.keyFor(변수) : 심볼명 반환
<pre><code>const id1 = Symbol.for("id");
const id2 = Symbol.for("id");

Symbol.keyFor(id1); //id
</code></pre>

# 숫자, 수학 메소드
* Math.ceil(숫자) : 올림
* Math.round(숫자) : 반올림
* 숫자.toFixed(자릿수) : 해당 자릿수까지 표현
* isNaN(숫자) : NaN인지 확인
* parseInt(문자열, 진법) : 문자열을 해당 진법의 숫자로 바꿔줌
* parseFloat(문자열) : 문자열을 부동소수점으로 바꿔줌
* Math.random() : 0~1 사이 무작위 숫자 생성
* Math.floor(Math.random()*100)+1 : 1~100 사이 무작위 숫자 생성
* Math.max(숫자 여러개) : 최댓값
* Math.min(숫자 여러개) : 최솟값
* Math.abs(숫자) : 절댓값
* Math.pow(n, m) : n의 m승 값
* Math.sqrt(숫자) : 제곱근

# 문자열 메소드
* 문자열.length : 문자열의 길이
* 문자열.toUpperCase() : 대문자
* 문자열.toLowerCase() : 소문자
* 문자열1.indexOf(문자열2) : 문자열1에서 문자열2가 어느 위치에 있는지 확인하여 첫번째 위치 반환, 찾는 문자가 없으면 -1 반환
* 문자열.slice(n, m) : n부터 m까지 문자열 반환, m 포함하지 않음
* 문자열.substring(n, m) : n과 m사이 문자열 반환, n과 m 바꿔도 똑같이 동작, m 포함하지 않음
* 문자열.substr(n, m) : n부터 m개의 문자 반환
* 문자열.trim() : 앞 뒤 공백 제거
* 문자열.repeat(n) : 문자열 n번 반복
* 문자열1.includes(문자열2) : 문자열1에 문자열2가 포함되어 있는지 확인
* 문자열.split(",") : 문자열을 ","를 기준으로 구분해서 배열로 반환

# 배열 메소드
* 배열.splice(n, m, x) : n부터 m개 요소 삭제하고 삭제된 요소 앞자리에 x 추가, 삭제된 요소 반환
* 배열.slice(n, m) : n부터 m까지 반환
* 배열.concat(arr1, arr2) : 배열 합쳐서 반환
* 배열.forEach(fn) : 배열 반복
<pre><code>let arr = ["Mike", "Tom", "Jane"];

arr.forEach((name, index) => {
    console.log(`${index+1}. ${name}`);
});
</code></pre>
* 배열.indexOf(n) : n의 인덱스 반환
* 배열.lastIndexOf(n) : n의 마지막 인덱스 반환
* 배열.includes(n) : n이 배열에 포함되는지 확인
* 배열.find(fn) : 특정 조건에 맞는 요소 반환
<pre><code>let userList = [
    {name: "Mike", age: 30},
    {name: "Jane", age: 27},
    {name: "Tom", age:10}
];

const result = userList.find((user) => {
    if (user.age < 19) {
        return true;
    }
    return false;
});

console.log(result); //{name: "Tom", age:10}
</code></pre>
* 배열.findIndex(fn) : 특정 조건에 맞는 요소 반환, 맨 앞에 1개만 반환
<pre><code>let userList = [
    {name: "Mike", age: 30},
    {name: "Jane", age: 27},
    {name: "Tom", age:10}
];

const result = userList.findIndex((user) => {
    if (user.age < 19) {
        return true;
    }
    return false;
});

console.log(result); //2
</code></pre>
* 배열.filter(fn) : 만족하는 모든 요소를 배열로 반환
<pre><code>let userList = [
    {name: "Mike", age: 30},
    {name: "Jane", age: 27},
    {name: "Tom", age:10}
];

const result = userList.filter((user) => {
    if (user.age > 19) {
        return true;
    }
    return false;
});

console.log(result); //{ {name: "Mike", age: 30}, {name: "Jane", age: 27} }
</code></pre>
* 배열.reverse() : 배열을 역순으로 재정렬
* 배열.map(fn) : 함수를 받아 특정 기능을 시행하고 새로운 배열을 반환
<pre><code>let userList = [
    {name: "Mike", age: 30},
    {name: "Jane", age: 27},
    {name: "Tom", age:10}
];

const newUserList = userList.map((user, index) => {
    return Object.assign({}, user, {
        isAdult: user.age > 19,
    });
});

console.log(newUserList); 
</code></pre>
* 배열.join(",") : 배열 안에 있는 요소들을 ","로 합쳐서 반환
* Array.isArray(배열) : 배열인지 확인
* 배열.sort() : 배열 재정렬, 문자열 정렬
* 배열.sort(fn) : 숫자 정렬
<pre><code>let arr = [27, 8, 5, 13];

function fn(a, b) {
    return a - b;
}
arr.sort(fn);

console.log(arr);
</code></pre>
* 배열.reduce(fn) : 배열 요소 하나로 더함
<pre><code>let arr = [1, 2, 3, 4, 5];

function fn(prev, cur) {
    return prev + cur;
}
const result = arr.reduce(fn);

console.log(result);
</code></pre>

# 구조 분해 할당
* 배열 구조 분해
<pre><code>let users = ["Mike", "Tom", "Jane"];
let [user1, user2, user3] = users;

let str = "Mike-Tom-Jane";
let [user1, user2, user3] = str.split('-');

let [user1, ,user2] = ["Mike", "Tom", "Jane", "Tony"];
</code></pre>

* 변수 서로 바꿀 때도 사용
<pre><code>[a, b] = [b, a];
</code></pre>

* 객체 구조 분해
<pre><code>let user = {name: "Mike", age: 30};
let {name, age=0} = user; //age 기본값 0
let {name: userName, age: userAge} = user; //키이름 변경
</code></pre>

# 나머지 매개변수, 전개 구문
* arguments : 함수로 넘어온 모든 인수를 배열로 만들어 접근
<pre><code>function showName(name) {
    console.log(arguments.length);
    console.log(arguments[0]);
    console.log(arguments[1]);
}

showName(); //undefined
showName("Mike", "Tom"); //2 "Mike" "Tom"
</code></pre>

* 나머지 매개변수
    * 인수를 배열 형태로 만들어서 사용하고 싶을 때
    * "...인수" 형태로 표현
    * 아무것도 전달 안했을 때 undefined가 아니라 []로 리턴
<pre><code>function showName(name, age, ...skills) { //단, 나머지 매개변수는 맨 마지막 인수여야 함
    this.name = name;
    this.age = age;
    this.skills = skills;
}

const user1 = new User("Mike", 30, "html", "css");
const user2 = new User("Tom", 20, "JS");
</code></pre>

* 전개구문(배열)
<pre><code>let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

let result = [0, ...arr1, ...arr2, 7];

console.log(result); //[0, 1, 2, 3, 4, 5, 6, 7]
</code></pre>

* 전개구문(객체) : 복제
<pre><code>let user = {name: "Mike", age: 30};
let user2 = {...user}; //복제

user2.name = "Tom";

console.log(user.name); //"Mike"
console.log(user2.name) //"Tom"
</code></pre>
<pre><code>let user = {name: "Mike"};
let info = {age: 30};
let fe = ["JS", "React"];
let lang = ["Korean", "English"];

user = {
    ...user,
    ...info,
    skills: [...fe, ...lang],
}
</code></pre>

# 클로저(Closure)
* 함수와 렉시컬 환경(함수를 선언한 곳에 따라 함수의 상위 스코프가 달라짐)의 조합
* 외부함수보다 중첩함수가 더 오래 유지되는 경우, 이미 생명주기를 마감한 외부함수의 변수를 참조할 수 있음 
* 중첩함수가 클로저
<pre><code>function makeCounter() {
    let num = 0; //은닉화

    return function() {
        return num++;
    }
}

let counter = makeCounter();

console.log(counter()); //0
console.log(counter()); //1
console.log(counter()); //2
</code></pre>

# setTimeout, setInterval
* setTimeout(실행할 함수, 시간, 인수) : 일정 시간이 지난 후 함수를 실행
<pre><code>function fn(name) {
    console.log(name)
}

setTimeout(fn, 3000, "Mike"); //3000은 3초
</code></pre>
* setInterval(실행할 함수, 시간, 인수) : 일정 시간을 간격으로 함수를 반복
<pre><code>function fn(name) {
    console.log(name)
}

setInterval(fn, 3000, "Mike"); //3000은 3초
</code></pre>
* clearInterval(tId) : 일정 횟수 반복 후에 반복 중단
<pre><code>let num = 0;

function showTime() {
    console.log(num++)
    if (num > 5) {
        clearInterval(tId);
    }
}

const tId = setInterval(showTime, 3000) //0 1 2 3 4
</code></pre>

# call, apply, bind 메소드
* call : 함수 호출 방식과 관계없이 this 지정 가능
* apply : 배열로 받은 매개변수를 차례대로 매개변수로 사용, 첫번째 매개변수는 this로 사용될 것
* bind : 함수의 this 값을 영구히 바꿀 수 있음
<pre><code>const mike = {
    name : "Mike",
};

const tom = {
    name: "Tom",
};

function showThisName() {
    console.log(this.name);
}

function update(birthYear, occupation) {
    this.birthYear = birthYear;
    this.occupation = occupation;
}

showThisName(); //window.name
showThisName.call(mike); //Mike

update.apply(mike, [1999, 'singer']);
console.log(mike) //{name: "Mike", birthYear: 1999, occupation: "singer"}

const updateMike = update.bind(mike);
updateMike(1980, "police");
console.log(mike) //{name: "Mike", birthYear: 1980, occupation: "police"}
</code></pre>

# 상속, 프로토타입
* 방법 1 : 객체.\_\_proto__ 사용
<pre><code>const car = {
    wheels: 4,
    drive: function() {
        console.log ("drive..");
    },
}

const bmw = {
    color: "red",
    navigation: 1,
}

bmw.__proto__ = car; //color, navigation, wheels, drive
</code></pre>
* 방법 2 : 생성자함수.prototype 사용
<pre><code>const bmw = function(color, navigation) {
    this.color = color;
    this.navigation = navigation;

}

bmw.prototype.wheels = 4;
bmw.prototype.drive = function() {
    console.log("drive..");
}

const x5 = new bmw("red");
</code></pre>

# 클래스
* 기본 형태 : constructor 메소드
<pre><code>class User2 {
    constructor(name, age) { //객체를 만들어주는 생성자 메소드
        this.name = name;
        this.age = age;
    }
    showName() { //프로토타입
        console.log(this.name);
    }
}

const tom = new User2("Tom", 19);
</code></pre>
* class에서의 상속 : extends
<pre><code>class Car {
    constructor(color) {
        this.color = color;
        this.wheels = 4;
    }
    drive() {
        console.log("drive..");
    }
    stop() {
        console.log("stop!");
    }
}

class bmw extends Car {
    constructor(color) { //오버라이딩, 상속받은 클래스에 constructor 만들 때 super(color); 키워드로 먼저 호출해야 함, 상위 클래스의 인수도 똑같이 넘겨받아야 함
        super(color);
        this.navigation = 1;
    }
    park() {
        console.log("park");
    }
}

const z4 = new bmw("blue");
</code></pre>

# 프로미스 (Promise)
* 프로미스 : 비동기 처리를 위한 패턴
<pre><code>const pr = new Promise((resolve, reject) => { //resolve : 성공시, reject : 실패시
    setTimeout(() => {
        resolve("OK")
    }, 3000)
});

pr.then(
    function(result) {
      console.log(result);
    })
    .catch(
    function(err) {
      console.log(err);
    })
    .finally(
    function() {
        console.log("---주문 끝---");
    });
</code></pre>
* 콜백 함수 : 어떤 일이 완료된 후 실행되는 함수
<pre><code>const f1 = (callback) => {
    setTimeout(function() {
        console.log("1번 주문 완료");
        callback();
    }, 1000);
};

const f2 = (callback) => {
    return new Promise((res, rej) => {
        setTimeout(function() {
        console.log("2번 주문 완료");
        callback();
    }, 3000);
    })
};

const f3 = (callback) => {
    setTimeout(function() {
        console.log("3번 주문 완료");
        callback();
    }, 2000);
};

console.log("시작");
f1(function() { //콜백 지옥
    f2(function() {
        f3(function() {
            console.log("끝")
        });
    });
});
</code></pre>
* 프로미스 체이닝
<pre><code>const f1 = () => {
    return new Promise((res, rej) => {
        setTimeout(() => {
            res("1번 주문 완료");
        }, 1000);
    });
};

const f2 = (message) => {
    console.log(message);
    return new Promise((res, rej) => {
        setTimeout(() => {
            res("2번 주문 완료");
        }, 3000);
    });
};

const f3 = (message) => {
    console.log(message);
    return new Promise((res, rej) => {
        setTimeout(() => {
            res("3번 주문 완료");
        }, 2000);
    });
};

console.log("시작");
f1()
.then((res) => f2(res))
.then((res) => f3(res))
.then((res) => console.log(res))
.catch(console.log())
.finally(() => {
    console.log("종료");
});

//async, await 사용
console.log("시작");
async function order() {
    try {
        const result1 = await f1();
        const result2 = await f2(result1);
        const result3 = await f3(result2);
        console.log(result3);
    } catch(e) {
        console.log(e);
    }
    console.log("종료");
}
order();
</code></pre>
* Promise.all : 다 수행되거나 다 수행되지 않을 때 사용
<pre><code>Promise.all([f1(), f2(), f3()])
.then((res) => {
    console.log(res)
})
</code></pre>
* Promise.race : 하나라도 reject 되면 stop
<pre><code>Promise.race([f1(), f2(), f3()])
.then((res) => {
    console.log(res)
})
</code></pre>

# async, await
* 함수 앞에 async 추가하면, 항상 프로미스 반환
* await : 다른 함수의 반환값을 기다렸다가 반환
<pre><code>function getName(name) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve(name);
        }, 1000);
    });
}

async function showName() {
    const result = await getName("Mike");
    console.log(result);
}

console.log("시작");
showName();
</code></pre>

# Generator
* 함수의 실행을 중간에 멈췄다가 재개할 수 있는 기능
* next, return, throw 메소드
<pre><code>function* fn() { //Generator: function 옆에 * 표시
    try {
        console.log(1);
        yield 1; //yield 키워드로 함수의 실행을 멈춤
        console.log(2);
        yield 2;
        console.log(3);
        yield 3;
        return "finish";
    } catch(e) {
        console.log(e);
    }
}

const a = fn();
a.next(); //1
a.next(); //2
a.return("END"); //done 상태가 true로 바뀜
a.throw(new Error("err")); //catch 실행, done 상태가 true로 바뀜
</code></pre>

* iterable
    * Symbol.iterator 메서드가 있음
    * Symbol.iterator는 iterator를 반환해야 함
* iterator
    * next 메소드를 가짐
    * next 메소드는 value와 done 속성을 가진 객체를 반환
    * 작업이 끝나면 done은 true가 됨
<pre><code>function* fn() {
    yield 4;
    yield 5;
    yield 6;
    }

const a = fn();

a[Symbol.iterator]() === a; //true
</code></pre>
<pre><code>function* fn() {
    const num1 = yield "첫번째 숫자를 입력해주세요";
    console.log(num1);

    const num2 = yield "두번째 숫자를 입력해주세요";
    console.log(num2);
  
    console.log(num1+num2);
    return num1 + num2;
}

const a = fn();
a.next();
a.next(3);
a.next(4);
</code></pre>
* 다른 Generator 불러오기
<pre><code>function* gen1() {
    yield "W";
    yield "o";
    yield "r";
    yield "l";
    yield "d";
}

function* gen2() {
    yield "Hello, ";
    yield* gen1();
    yield "!";
}

console.log(...gen2()); //Hello, W o r l d !
</code></pre>
