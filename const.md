# Const로 변하지 않는 값을 표현하기

const를 사용하면서 조작(mutation)을 피하는 것이 최선이다.

변수는 재할당 할 수 없지만, 값을 바꿀수는 있다.

* 객체 배열의 형태에서는 주의깊게 살펴 보아야하는데, 이는 push()를 통해서 값을 바꿀 수 있기 때문



# let 과 const로 유효 범위 충돌 줄이기

만약 값이 변경되어야 할 경우 가장 좋은 선택은 let이다.

### let vs var

* let은 블록 유효범위를 따른다
* var는 어휘적 유효범위를 따른다.



# 블록 유효 범위 변수로 정보를 격리하라.

*호이스팅

함수 안에 있는 선언들을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것을 말한다.
https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html

유효범위 문제를 해결하기 위해서 전통적으로는 클로저와 고차함수, 즉시 실행함수를 조합해서 해결한다.

ex)

function addClick(items){

​	for(var i=0;i<items.length;i++){

​		items[i].onClick = (function(i){

​			return function () {

​				return i;

​			}

​		}	(i));

​	}

​	return items;

}

const example = [{},{}];

const clickSet = addClick(example);

clickset[0].onClick();

// 이것을 let을 사용하면 쉽게 해결 가능



## 템플릿 리터럴로 변수를 읽을 수 있는 문자열로 변환

