---
title: FE Interview 10
date: 2020-08-05 19:00:00
author: nailerHeum
category: Interview
---

# FeBase interview3

---

## 1. JavaScript의 작동방식의 장단점에 관해 설명해주세요.

Javascript는 일급 함수를 지원하고, 프로토타입 기반의 다중 패러다임을 지원하고, 기능이 간단한 스크립트 언어입니다. 일반적으로 싱글 스레드와 이벤트 루프를 사용합니다.

### **장점**

- 일급 함수이기 때문에 함수를 인자로 사용할 수 있고, 클로저 패턴을 사용할 수 있습니다.
- 스크립트 언어로 인터프리터 방식과 JIT 컴파일러 방식을 혼용합니다. 빠른 실행이 가능하고 디버깅이 간편합니다.
- 일반적인 자바스크립트는 싱글 스레드로 동작하며 이벤트루프와 논블로킹 I/O를 지원하기 때문에 다양한 I/O 요청을 비동기적으로 처리하여 CPU를 효율적으로 사용하게 됩니다. 따라서 다른 언어에 비해 상대적으로 많은 요청을 빠르게 처리할 수 있는 서버를 구현할 수 있습니다.

### 단점

- 지원하는 기능이 단순하고 제한적입니다.
- 스크립트 언어이기 때문에 런타임에 발생하는 오류를 예방하기 까다롭습니다.
- 일반적으로 싱글 스레드이기 때문에 많은 양의 연산을 모두 하나의 스레드에서 처리하게 됩니다. 이러한 경우 연산 처리 하나로 인해서 다른 모든 작업들도 진행하지 못하고 기다리게 됩니다.

**일급 함수**

- 인자로 전달이 가능하다.
- 반환값으로 사용할 수 있다.
- 할당된 이름과 관계없이 고유한 구별이 가능하다.
- 변수나 데이터 구조 안에 담을 수 있다.
- 동적인 프로퍼티 할당이 가능하다.

## 2. 객체 안의 속성과 배열의 아이템을 순회할 때 사용하는 문법에 관해 설명해주세요.

자바스크립트에서 객체 안의 속성을 순회하는 좋은 방법은 `Object.entries()` 를 사용하는 것입니다. 또는 `Object.keys()` 를 사용할 수도 있습니다.

```jsx
const object1 = {
  a: 'hi',
  b: 3,
	c() {
		console.log('bye');
	}
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// or

for (const k of Object.entries(object1)) {
	console.log(`${k}: ${object1[k]});
}

// a: hi
// b: 3
// c: c() {
// 	console.log('bye');
// }
```

배열을 순회할 때도 `Object.entries()` 를 사용하거나 일반적인 for loop를 사용하여 순회할 수 있습니다.

```jsx
arr = [1, 2, 3, 4];
for (const [key, value] of Object.entries(arr)) {
    console.log(`${key}: ${value}`);
}

// or

for (let i=0; i<arr.length; i++) {
	console.log(`${i}: ${arr[i]}`);
}

// 0: 1
// 1: 2
// 2: 3
// 3: 4
```