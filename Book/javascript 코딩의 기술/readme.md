

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

* Object.assign() : 일련의 객체를 전달받고 가장 먼저 인수로 받은 객체를 뒤이어 인수로 넘긴 개체의 키-값을 이용해서 갱신 후 첫번째 객체를 반환.

>  Object.assign({}, default, book)  첫번째 객체에 빈객체를 사용하면, 원본객체의 조작 없이 빈객체에 정보가 갱신되어 반환됨. 

* 중첩객체 복사는 Object.assign ()을 이용하여 복사하도록 하면, 모든것을 갱신할 수 있다

  <pre>
      <code>
          const employee2 = Object.assign(
          {},
          defaultEmployee,
          {
              name: Object.assign({}, defaultEmp;ouee.name),
          },
          );
          export{defalute}
      	</code>
      </pre>
  

</code>

  </pre>

    - 로대시( Lodash) 라이브러리의 경우 cloneeDeep()메소드를  이용할 수 있다. 

#### Tip12. 객체펼침 연산자로 정보를 갱신하라 

#### Tip13.  맵으로 명확하게 키-값 데이터를 갱신하라

+ 맵은특정 작업을 매우 쉽게 처리하는 특별한 종류의 컬렉션이다. 

+ 객체와 다르게 키-값 쌍을 자주 변경하는 겨웅에 적합하도록 특별히 설계되었다. 

+ 인터페이스가 명확하고, 메스드는 예측 가능한 이름을 가지고 있으며, 반복과 같은 동작이 내장 되어 있다.

+ 중괄호로 생성자를 대신할 수 있는 객체와 달리, 맵에서는 항상 명시적으로 새로운 인스턴스를 생성 해야한다. 

  > let filters = new Map();
  >
  > filters.set('견종', '래브라도레트리버'); //데이터 설정
  >
  > filters.get('견종'); //'래드라도레트리버'  
  + 위의 코드를 보면 앱을 할당할 때 let을 사용한 이유는 데이터를 추가하면서, 객체를 조작할 것이기 때문이다.
  + 매서드를 차례로 연결해서 여러값을 쉽게 추가할 수 있습니다. 새로운 인스턴스를 생성하고 바로 메서드를 연결 할 수 도 있습니다. 이러한 방법을  체이닝 이라고 부르면 Tip25에서 다시 설명 할 예정

  > let filters= new map()
  >
  > ​                  .set('견종','래브라도레트리버')
  >
  > ​                  .set('크기','대형견)
  >
  > ​                  .set('색상','갈색');
  >
  > filtes.get('크기') // '대형견'

  - 배열을 이용해서 값을 추가 할 수도 있다. 
  - 맵에서 값을 제거 할 땐, delete() 매서드를 사용하면 된다.

  > filters.delete('색상');
  >
  > filtes.get('색상')  // undefind

  - 모든 키-값을 제거할땐 clear()메서드를 사용하면 된다. 

  > filters.clear();
  >
  > filtes.get('색상')  // undefind

+ 맵도 객체와 마찬가지로 키만 모아서 확인 할 수 있습니다. 다만 배열과, 맵이 아닌 맵이터레이터가 반환된다. 

  > Map.kesy();// MapIterator 이 반환된 값으로 나온다. 

### Tip14. 맵과 펼침연산자로 키-값 데이터를 순회하라 

- 키-값 컬렉션에 항목을 자주 추가하거나 삭제하는 경우에는 객체보단 맵을 사용하는 것이 적합

- 맵은 정렬과 순회에 필요한 기능 내장, 맵이터레이터의 일부 로 포함 

- 이터레이터는 키-값 쌍을 넘겨줌 

- entries() 매서드 는 맵에 있는 키-값을 쌍으로 묶은 맵이레이터를 반환

- 맵에는 정렬메서드가 내장되어 있지 않지만, 펼침연산자를 이용할 수 있다. 

  <pre> 
  function getSortedAppliedfilters(filters){
  	const applied = [...filters]
      				.sort(sortByKey)
      				.map(([key,value]) => {
      					return '${key}:${value}';
      				})
      				.join(', ');
      			return '선택한 조건은 ${applied} 입니다.';  
  }    
  </pre>

  

  1. 맵을 배열로 변환.
  2. 배열을 정렬.
  3. 배열에 담긴 키-값 쌍을 '키:값' 형식의 문자열로 변환.
  4. 배열의항목을 연결해서 문자열로 만듬.
  5. 템플릿 리터럴을 이용해서 다른 정보와 함께 문자열로 병합. 

### Tip15. 맵 생성 시 부수 효과를 피하라 

### Tip16. Set을 이용해 고윳값을 관리 하라 

- set 또한 펼침 연산자를 사용 할 수 있다. 



## 4. 조건문을 깔끔하게 작성하라

### Tip 17. 거짓값이 있는조건문을 축약하라 

거짓 값의 목록

> - false
> - null
> - o 
> - NaN(숫자가 아님)
> - ' '
> - " "

### Tip 18. 삼항 연산자로 빠르게 데이터를 확인하라

### Tip 19. 단락 평가를 이용해 효율성을 극대화하라 

단락 평가란 ? 가장 타장한 정보를 먼저 위치시켜 정보 확인을 건너 뛰는 것을 말한다. 

> OR 연산자 (||) - 비교중 하나라도 true 가 있다면, true 반환
>
> AND연산자 (&&) - 모두가 true일 경우에만 true 반환, 그 외는 false 
>
> 를 이용해여, 조건문의 중첩을 피할 수 있다. 



## 5. 반복문을 단순하게 만들어라 

### Tip 20. 화살표 함수로 반복문을 단순하게 만들어라 

화살표 함수란 ? 필요 없는 정보를 최대한 걷어 낸다.  ( function 키워드 , 인수를 감싸는 괄호 , return 키워드, 중괄호)


    function capitalize(name){
    	return name[0].toUpperCase() +name.slice(1);
    }
    // 기명함수 : 이름이 함수의 일부로 선언되어 있다는 것. 


    const assignedFunction = function(){
    	//익명 함수 : 람다 대수로부터 영향을 받아 만들어진 프로그래밍에서 함수를 표현하는 방식의 일종
    }



익명 함수를 변수에 할당하는 방식을 화살표 함수로 바꾸는 경우에도 사용, function 키워드를 제거하고 두꺼운 화살표로 대체 , 

매개변수가 하나뿐이라면 괄호도 제거 가능.

<pre>
    const capitalize = name => {
		return name[0].toUpperCase()+name.slice(1);
	}
</pre>



1. 매개변수가 없는 경우, 괄호 사용

    before : 
        function key (){
       		 return 'abc123';
        }
    after :
        conster key = () =>{
       		 return 'abc123';
        }
        
    before : 
        function key (){
        	return 'abc123';
        }
    after :
        conster key = () =>{
        	return 'abc123';
        }



2. 매개변수가 2개 이상인 경우, 괄호 사용 가능

> before  :
>
> function greet(first, last){
>
> return '안녕하세요, ${capitalize(first)}, ${capitalize(last)}님'; 
>
> } 
>
> after :
>
>  const greet = (first, last) =>{
>
> return '안녕하세요, ${capitalize(first)}, ${capitalize(last)}님'; 
>
> }

3. return 키워드도 사용할 필요가 없다. 즉, 함수 몸체의 실행결과를 자동으로 반환한다. 

>before : 
>
>fucntion formatUser(name){
>
>return ' ${capitalize(name)}님이 로그인 했습니다. '; 
>
>}
>
>after : 
>
>const formatUser = name => ' ${capitalize(name)}님이 로그인 했습니다. '; 

4. 자바 스크립트에서는 함수를 다른 함수에 인수로 전달 가능

   콜백 함수란 ? 원래 함수의 끝에서 실행 하는 함수. 

>1. 기명함수를 생성하고 전달
>
>   function applyCustomGreeting(name, callback){
>
>   ​	return callback(capitalize(name));
>
>   }
>
>2. 원본 함수를 호출 할 때 익명 함수를 생성하면 더 편리함
>
>   applyCustomGreeting('mark', fuction (name){
>
>   ​	return '안녕, ${name}!';
>
>   });
>
>3. 이 익명 함수의 불필요한 부분을 생략 ()
>
>   applyCustomGreeting('mark', name=>'안녕, ${name}!'; );

### Tip 21. 배열 메서드로 반복문을 짧게 작성하라 

- map() : 형태를 바꿀 수 있지만 길이 유지 
- sort () : 형태나  길이는 변경되지 않고 순서만 변경
- filter() : 길이는 변경되지만 형태는 바꾸지 않음
- find() : 배열을 반환하지 않는다. 한개의 데이터가 반환 되고, 형태는 바뀌지 않음
- forEach(): 형태를 이용하지만 아무것도 반환하지 않는다. 
- reduce() : 길이와 형태를 바꾸는 것을 비롯해 무엇이든 처리할 수 있다. 

### Tip 22. map() 메서드로 비슷한 길이의 배열을 생성하라 

map() 메서드를 통해, 정보의 부분집합을 생성 할 수 있다. 

map() 메서드는 흔히 사용되고, 새롭게생성되는 배열에 메스드의 콜백에서 반환하는 정보가 담김. 

즉, 다른 배열 메서드에 비해 반환값을 알기 쉬움. 

map() 메사드를 사용하면 새로운 값을 담을 배열을 준비할 필요가 없음. 배열 메서드의 일부로 포함되기 때문.

또한, push()메서드로 옮길 필요도 없음,  

map()메서드는 맵 함수의 실행결과를 반환될 배열에 추가하기 때문, 

그래서 원본 배열의 각 항목을 인수로 받아 새롭게 생성될 배열에 담길 값을 반환한ㄴ


```javascript
const instrunments = band.map(member => member.instrument);
//  instrument 는 band 라는 object 배열의 map()함수의 실행 결과 배열을 담는다. 
```

** 맵 객체와  혼동 하지 말것 (위 소스에서 memebr)

### Tip23. filter()와 find()로 데이터의 부분집합을 생성하라 

데이터 형태는 유지하면서 전체 항목의 일부만 필요한 경우는 filter() 메소드가 적합.

map()메서드와 다르게, 배열에있는 정보를 변경하지 않는다. 단, 반환되는 배열의 길이를 줄일뿐.


```javascript
const scores =[30, 82, 70, 45];
function getNumberOfPassingScores(scores){
    const passing = scores.filter(scores => scores >=59);
    //[87,70]
    return passing.length;
}
//2

function getNumberOfPassingScores(scores){
    const passing = scores.filter(scores => scores === 100);
    //[]
    return passing.length;
}
// 0
```

filter()함수는 ture or false  반환하지만, 최종적으로 반환되는 배열에는 실제 값이 담긴다. 

필터 함수는 각각의 점수를 한번에 하나씩 검사하고, 반환값이 ture 일떄는 값을 그대로 유지합니다. 또한 **반환되는 배열은 원본 배열 순서도 그대로 유지** 

filter() 메서드는 항상 배열을 반환하며 조건이 일치하는 값이 없는 경우에도 반환한다. 

match() 메서드가 참 or 거짓을 반환하기 때문에 필터 함수에 곧바로 사용할 수 있다. 


```javascript
const daves = team.filter(member => member.mathch(/Dav/));
```

가끔 배열에 조건과 일치하는 항목이 최대 하나뿐이라는 사실을 알고 있는 경우가 있다. 그런 경우에는 filter() 메서드와 비슷한 find() 메서드를 사용할 수 있다. 

find() 메서드는 참 or 거짓 값을 반환하는 함수를 인수로 받고, 배열의 항목에 전달한 함수로 평가해 참 값을 반환하는 첫번째 항목만 반환합니다. 참값을 반환하는 항목이 없다면 undefined를 반환한다. 

ex)특정 id를 찾는 경우.. 

### Tip24. forEach()로 동일한 동작을 적용하라 

### Tip25.체이닝으로 메서드를 연결하라.



