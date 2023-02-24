# 🌟 Learned #19

# 🔶This

## (1) this의 동작 원리

`this`는 현재 실행 중인 함수의 객체를 참조한다.

this의 값은 함수가 어떻게 호출되었는지에 따라 달라진다.

**1. 일반 함수 호출에서 `this`는 전역 객체를 가리킨다.**
**2. 객체의 메소드로 호출된 함수에서 `this`는 해당 객체를 가리킨다.**
**3. 생성자 함수에서 `this`는 생성된 객체를 가리킨다.**
**4. `call()` 또는 `apply()` 메소드를 사용하여 명시적으로 `this`를 지정할 수 있다.**

따라서 `this`의 값은 실행 컨텍스트에 따라 동적으로 결정되며, 함수를 호출하는 방법에 따라 달라진다.

## (2) this의 용법

call() 또는 apply() 메소드를 사용하여 함수 내에서 this를 지정하거나
객체의 메소드에서 this를 사용하여 해당 객체의 속성에 접근하거나 수정할 수 있다.

## (3) 평소 코드와 this를 사용할 때의 차이점

`this를 사용하는 가장 큰 차이점`은 **함수를 호출하는 방법에 따라 this가 참조하는 값이 달라진다**는 것입니다. 그리고 이러한 동적인 특성 때문에 this의 값이 예상과 다르게 결정될 수 있습니다. 따라서 this를 사용할 때는 주의가 필요합니다.
특히, 콜백 함수나 중첩 함수에서 this를 사용할 때는 주의가 필요합니다. 이러한 경우에는 this를 변수에 저장하여 사용하거나 bind() 메소드를 사용하여 this를 지정할 수 있습니다.