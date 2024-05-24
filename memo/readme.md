1.import란: 다른 모듈,패키지,파일 또는 라이브러리에서 정의된 기능이나 객체를 현재의 코드 파일로 가져오는 것을 의미함. 이는 코드의 재사용성을 높이고, 기능을 모듈화 하며 복합한 시스템을 더 쉽게 관리 할 수 있게 한다.

2.모듈이란: 특정 기능을 수행하는 코드 묶음입니다. 자바스크립트에서는 하나의 파일이 하나의 모듈이 될 수 있으며, 다른 파일로부터 필요한 함수를 가져와서 사용할 수 있습니다.

2024.05.24
02_core-11_standard-built-in-object-01_built-in-global-property.js
global object 


/* 빌트인 전역 프로퍼티 */

Infinity :
console.log(global.Infinity === Infinity);  //true
console.log(10/0);                          // Infinity// 양의 무한대
console.log(-10/0);                         // Infinity// 음의 무한대
console.log(typeof Infinity);               // number

// NaN : 숫자가 아님(Not a Number)을 나타내는 숫자 값
// Number.NaN 프로퍼티와 같다.
console.log(global.NaN);            // NaN
console.log(Number('abc'));         // NaN
console.log(10 * 'abcf');           // NaN
console.log(typeof NaN);            // number

// undefined : 원시 타입 undefined 
console.log(global.undefined);               // undefined
let nothing;
console.log(nothing);                        // undefined
console.log(typeof undefined);               // undefined

1.global object(전역객체): 자바스크립트에서 모든 전역 변수와 함수를 포함하는 특별한 객체이다.
이 객체는 모든 코드에 대한 최상위 스코프룰 제공하며 전역 변수와 함수를 이 객체의 속성(property)으로 사용할 수 있다. 자바스크립트 환경에 따라 던역 객체의 이름은 다를 수 있다. 브라우저 환경에서는 'window' 객체가 전역 객체를 나타낸다. Node.js환경에서는 'global'객체가 전역 객첼를 나타낸다.
2.전역변수란?:Grobal Variable은 프로그램 전체에서 접근 가능한 변수를 의미한다. 즉 변수가 어디에서든 참조할 수 있는 범위를 갖는 변수이다. 전역 변수는 전역 스코프(global scope)에 선언되어 있으며, 프로그램의 어느 곳에서나 사용할 수 있다. 전역변수는 보통 함수 내부가 아닌 함수 외부에서 선언된다. 함수 내부에서 선언된 변수는 지역변수(Local Variable)로 해당 함수 내에서만 유효한 범위를 갖는다.
3.스코프란?:프로그래밍에서 변수와 함수의 유효범위를 나타내는 개념.
4. 브라우저 환경에서 전역 객체 예시
//전역변수 선언
var globavar = 'I am a global variable';
//전역함수 선언
function globalFunction(){
    console.log('I am a global function');
}
//window 객체를 통해 전역 변수와 함수에 접근
console.log(window.globarVar);// 출력: I am a gobal variable
window.globalFunction(); // 출력: I am a gobal function

Node.js환경에서의 전역 객체 예시('global')
//전역 변수 선언
global.globaVar = 'I am a global variable;
//전역 함수 선언
global.globalFunction = function(){
    console.log('I am a global function');
};
 //global 객체를 통해 전역 변수와 함수에 접근
 console.log(global.globalVar); // 출력: I am a global variable
 global.globalFunction(); // 출력: I am a global function
 위의 예제에서 'global'객체는 Node.js 환경에서의 전역객체를 나타낸다.

 전역 객체를 사용하면 어플리케이션 전체에서 공유할 데이터나 함수를 쉽게 정의하고 접근할 수 있다. 그러나 전역 변수와 함수의 남용은 코드를 이해하기 어렵게 만들 수 있으므로 적절한 사용이 필요하다.
 5.전역 프로퍼티(Built-in Global Properties)가 있다.
 이 프로퍼티들은 전역 객체의 일부이며 모든 스크립트에서 접근 할 수 있다.
 여기에는 'Infinty','NaN','undefined'같은 값들이 포함된다.
 이외에도 몇가지 비트인 정역 함수도 있다. 
 이 프로퍼티와 함수는 자바스크립트환경에서 기본적으로 제공되므로 특별한 선언 없이 바로 사용가능
 *주요 빌트인 전역 프로퍼티
 1)Infinity:양의 무한대를 나타내는 숫자 값
console.log(Infinity);// 출력: Infinity
console.log(1/0); // 출력: Infinty
2)NaN
"Not-a-Number"의 약자로 숫자가 아님을 나타내는 값이다.
console.log(NaN);// 출력:NaN
console.log("hello" *2);// 출력 : NaN
3)undefined
값이 할당되지 않은 변수의 초기 값을 나타낸다.
let x;
console.log(x);//출력:undefined
*주요 빌트인 전역 함수
1)eval()
.문자열로 표현된 자바스크립트 코드를 실행한다.
eval("console.log('Hello,World!); // 출력:Hello,World!

3)isNaN()
전달된 값이 NaN인지 검사합니다.
console.log(isNaN(NaN)); // 출력: true
console.log(isNaN(10)); // 출력: false
4) parseFloat()
문자열을 부동 소수점 숫자로 변환합니다.
console.log(perseFloat("3.14)); // 출력:3.14
console.log(perseFloat("314e-2")); // 출력:3.14
5) parselnt()
문자열을 정수로 변환합니다.
console.log(parseInt("10"));// 출력:10
console.log(parseInt("10.5)); // 출력:10
 6.프로퍼티란?:자바스크립트 객체(Object)의 구성 요소로,객체의 상태나 동작을 나타내는 키-값 쌍이다.이름과 그에 대한 값으로 이루어져있다.
 
 
 9.undefined?:
 10.빌트란?
----------------------------------------------------------------------------------------
 02_core-11_standard-built-in-object-02_bulit-in-global-function.js
 /* 빌트인 전역 함수 */

// isFinite
// 전달 받은 인수가 정상적인 유한수인지 검사하여 유한수이면 true를 반환하고, 무한수이면 false를 반환
// 전달 받은 인수가 숫자가 아닌 경우 숫자로 타입 변환 후 검사를 수행하며, NaN으로 평가되는 값이면 false를 반환
console.log(isFinite(10));              // true
console.log(isFinite('10'));            // true
console.log(isFinite(null));            // true 왜 true?자바스크립트에서 값을 유한수인지 확인하려면 isFinite() 함수를 사용할 수 있습니다. 이 함수는 전달된 값이 유한한 숫자인지 여부를 검사합니다. null은 유한수가 아니므로 isFinite(null)은 특별한 경우로 true를 반환합니다. 그러나 이는 자바스크립트의 타입 변환 특성 때문입니다. 실제로 null을 숫자로 변환하면 0이 되기 때문에 유한한 숫자로 간주됩니다.

console.log(isFinite(Infinity));        // false //왜 faalse?: isFinite()함수는 유한한 숫자인지 검사 infinity는 유한한 숫자가 아닙니다.
console.log(isFinite(-Infinity));       // false//-infinity는 유한한 숫자가 아닙니다.

console.log(isFinite(NaN));             // false Nat-a-Number숫자가 아니다.
console.log(isFinite('abc'));           // false 문자열이라 숫자가 아니다.
console.log('-------------------------------');

// isNaN
// 전달 받은 인수가 NaN인지 검사하여 그 검사 결과를 불리언 타입으로 반환
// 전달 받은 인수가 숫자가 아닌 경우 숫자로 타입 변환 후 검사를 수행
console.log(isNaN(NaN));  ->숫자가 아니인가?              // true->그렇다.
console.log(isNaN(10));  ->숫자가 아니인가?               // false->아니다.

console.log(isNaN('abc'));              // true
console.log(isNaN('10'));               // false
console.log(isNaN(''));                 // false ('' => 0)

console.log(isNaN(true));               // false (true => 1)
console.log(isNaN(false));              // false (false => 0)

console.log(isNaN(undefined));          // true 

console.log(isNaN({}));                 // true
console.log('-------------------------------');

// parseFloat : 전달받은 문자열 인수를 부동 소수점 숫자, 실수로 해석하여 반환
console.log(parseFloat('10.01'));       // 10.01
console.log(parseFloat('10'));          // 10
// 공백으로 구분 된 문자열은 첫 번째 문자열만 변환
console.log(parseFloat('10 20 30'));    // 10
// 숫자가 아닌 문자열은 제외하고 변환
console.log(parseFloat('10cm'));        // 10
// 첫 번째 문자열을 숫자로 변환할 수 없다면 변환 불가
console.log(parseFloat('GS25'));        // NaN
// 앞뒤 공백은 무시
console.log(parseFloat('  1004  '));    // 1004

// parseInt : 전달받은 문자열 인수를 정수로 해석하여 반환
console.log(parseInt('10'));            // 10
console.log(parseInt('10.01'));         // 10
console.log('-------------------------------');

// encodeURI
// URI(인터넷에 있는 자원을 나타내는 유일한 주소)를 문자열로 전달받아 이스케이프 처리를 위해 인코딩한다.
// 네트워크를 통해 정보를 공유할 때 어떤 시스템에서도 읽을 수 있는 아스키 문자 셋으로 변환
const uri = 'http://greedy.com?name=홍길동&job=student';
const enc = encodeURI(uri);         
console.log(enc);                   // http://greedy.com?name=%ED%99%8D%EA%B8%B8%EB%8F%99&job=student

// decodeURI
// 인코딩 된 URI를 인수로 전달 받아 이스케이프 처리 이전으로 디코딩한다.
const dec = decodeURI(enc);
console.log(dec);                   // http://greedy.com?name=홍길동&job=student

// encodeURIComponent
// URI 구성 요소를 인수로 전달 받아 알파벳, 0~9의 숫자, - _ . ! ~ * ' ( ) 문자는 제외하고 인코딩한다.
// 쿼리 스트링 구분자로 사용 되는 =, ?, &까지 인코딩한다.
const uriComp = 'name=홍길동&job=student';
const encComp = encodeURIComponent(uriComp);
console.log(encComp);               // name%3D%ED%99%8D%EA%B8%B8%EB%8F%99%26job%3Dstudent

// decodeURIComponent
const decComp = decodeURIComponent(encComp);
console.log(decComp);               // name=홍길동&job=student

1.isFinite()
전달된 값이 유한한 숫자인지 검사한다.
console.log(isFinite(10)); //출력: true
console.log(isFinite(Infinty)); // 출력: false