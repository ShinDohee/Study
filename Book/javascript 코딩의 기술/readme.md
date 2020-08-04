

# 1. 변수할당으로 의도를 표현하라.

####  Tip1. 변수의 재할당을 피해라	

* const를 사용하라

​       단, const에 할당된 값이 불변의 값이 되지 않는다는 것은 고려할 것.

​       변수를 재 할당 할 수 없지만, 값을 바꾸는것은 가능함. 



####  Tip2. 유효범위 충돌을 줄여라 (const , let)

* let 은 재할당 할 수 있다는 점에서 var과 비슷하지만, Scope 가 다름
  * var : 어휘적 유효 범위 (lexical scope)
  * let : 블록 유효 범위 ( block scope) 

> 블록 유효 범위 ( block scope)  : 변수를 선언한 중괄호를 벗어나면 변수가 존재하지 않음
>
> 어휘적 유효 범위 (lexical scope) : 호출할 때가 아니라 선언하였는지에 따라 결정됨





#### Tip3. 블록 유효 범위 변수로 정보를 격리하라	

* let은 불록 유효 범위를 따르므로, 블록 내에서 선언한 변수는 해당 블록에서만 유효합니다. 따라서 반복되어 값이 변경되더라도, 이전에 선언한 함수의 값은 변경되지 않습니다. 

  **let을 이용하여 for 문이 반복될 때마다 값을 잠금**





#### Tip4. 템플릿 리터럴로 변수를 읽을 수 있는 문자열로 변환하라 

> 템플릿 리터럴 : 자바스크립트 표현식을 사용하여 문자열을 연결하고 새로운 문자열을 생성하는 간단한 문법 
>
> > 1. 따옴표 또는 쌍따옴표 대신 백틱을 사용
> > 2. 변수에 할당한 문자열처럼 단순 문자열이 아니라면 특별한 지정자로 감싸줘야함 ( ex. ${변수}  )





# 2. 배열로 데이터 컬렉션을 관리하라 

#### Tip5. 배열로 유연한 컬렉션을 생성하라 

#### Tip6. include()로 존재여부를 파악하라

<pre><code>const section = ['contack' , 'shipping'];
function displayShipping(sections){
	return sections.includes('shipping');
}</code></pre>

#### Tip7. 펼침 연산자로 배열을 본떠라 

#### Tip8. push() 메서드 대신 펼침 연산자로 원본 변경을 피하라

> 펼침 연산자의 이점
>
> * 가변인수-apply() 대체(배열 요소를 함수의 이수로 사용하고자 할 때)
>
> * 복사하기 - 원본을 조작하지 않고 복사본으로 정렬하기
>
> * 객체 펼침 연산- object.assign() 대체
>
> * 배열 펼침연산자 - 배열리터럴 내에서의 사용 등등 
>
>   [출처] ([https://velog.io/@kwonh/ES6-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%BB%AC%EB%A0%89%EC%85%98-Array2-%EB%B0%B0%EC%97%B4-%ED%8E%BC%EC%B9%A8%EC%97%B0%EC%82%B0%EC%9E%90%EC%A0%84%EA%B0%9C%EC%97%B0%EC%82%B0%EC%9E%90-Spread-Syntax-Spread-Operator-1y6chdfg](https://velog.io/@kwonh/ES6-데이터컬렉션-Array2-배열-펼침연산자전개연산자-Spread-Syntax-Spread-Operator-1y6chdfg))

#### Tip9. 펼침 연산자로 정렬에 의한 혼란을 피하라



# 3.특수한 컬랙션을 이용해 코드 명료성을 극대화하라

 #### Tip10. 객체를 이용해 정적인 키-값을 탐색하라

#### Tip11.  Object.assign() 으로 조작없이 객체를 생성하라 

