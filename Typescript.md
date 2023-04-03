# Typescript
- javascript 문법에 타입 표기 구문이 추가된 것으로 생각하면 쉽다. (superset)
- 정적 타입의 특징을 갖는다. 
- 브라우저에서 실행이 안 된다. 자바스크립트로의 컴파일이 필요하다.
- 컴파일 단계에서 오류를 찾을 수 있다.

## 타입 

### 기본 유형
- number: 정수, 실수 전부 다 할 수 있다. 소문자로 표기
```
let age: number;
age = 12;
age = 18.3;
age = '1'; // 이와 같은 경우에는 오류 발생
```
- string: 문자열. 소문자로 표기
```
let name: string;
name = 'manx';
```
- boolean: 논리형. true/false
```
let ㅜ  flag: boolean;
flag = true;
flag = false;
```
- null: null. 값을 넣으려고 하는 경우 오류 발생.
```
let emp: null;
emp = 'sss'; // 오류 발생.
```
- undefined

### 배열 및 객체
```
let hobbies: string[]; // 배열의 선언은 배열 안에 들어갈 데이터 타입 뒤에 대괄호를 붙인다.
let snake: number[];
let moles: boolean[];

hobbies = ['Cooking', 'Sleeping'];
snake = [12, 23, '34'] // 오류 발생
moles = [true, false, false];

let personA; // 명시하지 않은 경우 기본으로 any 라는 타입으로 지정된다. 어떤 값이든 저장 가능. 예비적으로 사용하는 것이고 TS가 만들어진 목적과는 반대되는 사용이기에 기피하는 것이 좋다.
personA = {
    name: 'Max',
    age: 12
}

let personB: { // 객체의 형태를 정의한다. 중괄호로 객체 타입을 지정하고 생성은 아니다.
    name: string,
    age: number;
};

let people: {
    name: string,
    age: number
}[]; // 객체 배열
```

### 타입 추론(type inference)
- 명시적으로 타입을 지정하지 않아도 초기값에 의해 값이 정해지면 해당 변수는 해당 타입의 변수임을 추론하는 기능.
- 이로 인해 다른 타입의 값을 넣을 경우, 오류가 발생한다.
```
let maker = 'Speedo'; // maker 변수는 string으로 지정이 된다.
maker = 123; // string으로 추론되기에 오류 발생
```

### 유니온
- 한개 이상의 타입을 지정
```
l
```

## 컴파일
- npx tsc 명령어를 이용해 컴파일을 실행할 수 있다.
- 처음 사용할 경우 오류가 발생하는데 그 이유는 타입스크립트 구성 파일을 프로젝트 폴더에 추가해 타입스크립트에게 컴파일할 파일을 알려줘야 한다.