## 객체 지향 언어

- 비교 > 절차 지향 언어 > 근데 절차 지향도 어찌어찌 객체처럼 쓸 수 있다 > 대체 명확한 차이란 무엇인가...

- "~~처음 언어를 배울 때 C를 배웠습니다. 본래 게임 개발을 꿈꾸며 소프트웨어 공학을 전공하기 시작하던 차에, 도대체 이런 걸로 게임을 어떻게 만들 수 있을까 당황했던 적이 있습니다~~. 객체 지향을 배우기 전에는 순차적으로 써내려가는 로직 안에 플레이어와 몬스터 간의 상호작용, 언제 입력될지 모르는 플레이어 입력을 어떻게 처리해야 되는지 막막했습니다. > java를 배우기 시작하면서 고민이 점점 해결되었다 > 사람들의 정보를  class 단위로 관리하고 저장하면서... > 이 class를 상속받는 하위 class를 만들면서... > 다양한 연결 관계에서 데이터가 오염될 걱정이 생긴 적이 있는데 캡슐화를 통해... class 외부에 >

- 그러다 2학기 java를 통해 객체 지향 언어를 처음 접했는데 아주 황홀한 기분이었습니다. 추상화, 상속, 다형성, 캡슐화 등은 게임 속의 복잡한 상호작용 관계를 표현하기에 최적이었습니다. > 흠... 객체 지향 언어 특징부터 설명하는 것이 좋아 보임

- 추상화가 보장된 절차 지향 언어라고 생각합니다.
	- 싱글 코어라면 객체 지향 언어도 결국 절차적으로 실행
	- 절차 지향 언어도 객체 지향 언어처럼 사용하는 것이 가능
	- 결국 객체 지향 언어의 확실한 특징은 class나 접근 제한자를 제공함으로써 추상화를 "보장" 해주는 것이라 생각. 
	- 이러한 생각을 바탕으로 추상화가 보장된 절차 지향 언어라는 결론을 내렸다.

## 유니티 생명주기

- 유니티 스크립트를 실행하면 사전에 지정된 순서대로 이벤트 함수들이 실행되는데 이걸 유니티 생명주기라 부릅니다. 이 순서를 이해하면 컴포넌트 간 의존성 처리나 최적화에 도움이 됩니다. 
	- Awake에서 매니저 스크립트 초기화하고 Start에서 이 스크립트를 참조한다던가..
	- Update에서 충돌 감지 해주는 대신 OnTrigger/OnCollision을 사용한다던가...
	- Update는 Frame마다, FixedUpdate는 프레임 상관 없이 fixedDeltaTime 값마다, LateUpdae는 Update가 호출된 후

- 유니티 생명주기는 
- 객체 지향 언 스크립트가 얼마나 많든 생명 주기가 정해져 있어 스크립트 연산의 순서가 보장된다.
- 인풋, 물리 연산, 렌더링 같은 게임이 되기 위해 필요한 연산을 수행(?)
- 플레이어가 얻을 수 있는 장점 > 이미 여러 번 
- 유지 보수와 디버깅 쉬워짐
- 개발자가 생명 주기 함수 중 Update, FixedUpdate, LateUpdate를 잘 사용하여 CPU 부담을 나눌 수 있다.
	- Update 마다 특징


## C++
- Class/Struct는 기본 접근 제한자가 각각 Private/Public이다. 상속의 기본 접근 제한자도 동일하다. class는 추상화 목적으로 사용하고, struct는 데이터 구조를 정의할 때 사용한다. 필요에 따라 함수를 추가할 수도 있다.
- Inline-function은 컴파일 단계에서 in-place로 확장된다. 때문에 함수 호출 오버헤드가 제거되지만, 오브젝트 파일/실행 파일의 크기가 커진다.
- List container는 시퀸스/노드 기반
- rvalue(right-value)는 일반적으로 직접 참조하거나 주소를 구할 수 없는 값이다. 대게 메모리가 아닌, 계산 결과를 일시적으로 저장하는 레지스터나 스택에 위치한다.  리터럴 값/일시적으로 생성된 임시 객체/연산 결과등이 rvalue에 속한다.  
- lvalue reference int& x, rvalue reference int&& x
- rvalue reference는 C++11부터 도입돼 이동 시맨틱을 구현한다. 소유권을 이전하며, 이는 메모리 위치를 바꾸는 것이 아니라 해당 메모리의 자원을 관리하는 포인터나 참조를 새로운 객체로 이전한다는 의미다. 이동 후 원래 겍체는 빈 껍데기 상태로 남는다. std::move() 함수를 통해 lvalue를 rvalue로 바꾸고, rvalue reference로 전달 가능하다.
- Reference는 변수를 가리키는 별칭이다. 이를 사용하면 값에 직접 접근할 수 있다. 포인터와 유사하지만 주소 연산자를 사용하지 않고 초기화 후 변경될 수 없다는 차이점이 있다. 추가적으로 초기화가 필요하고 null을 가리킬 수 없다.

## C샵
- List<> 클래스는 내부적으로 동적 배열(dynamic array) 구조를 사용한다. C++의 vector와 마찬가지로 배열을 확장한다. 다만 .NET 스타일의 메서드를 제공하며, 메모리를 가비지 컬렉터가 관리한다는 점에서 다르다
- `게임오브젝트(GameObject)`는 일반적으로 **프로퍼티**라기보다는 **오브젝트**나 **인스턴스**로 불립니다.

- **프로퍼티(Property)**: C#에서 프로퍼티는 클래스나 객체의 상태를 노출하는 방식으로, 주로 특정 필드에 대한 접근자(`get`, `set`)를 통해 값을 가져오거나 설정하는 데 사용됩니다.
- **게임오브젝트(GameObject)**: 유니티에서 `GameObject`는 게임 씬에서 객체를 나타내는 기본 단위로, 컴포넌트를 통해 다양한 기능을 추가할 수 있는 실체입니다.

따라서 `GameObject`를 "프로퍼티"라고 부르는 것은 정확하지 않으며, 대신 "객체", "오브젝트", 또는 "게임 오브젝트"로 부르는 것이 더 적절합니다.

그러나 `GameObject`가 다른 클래스의 필드로 선언되어 있다면, 그 필드에 대한 **프로퍼티**(예: `public GameObject MyObject { get; set; }`)를 만들 수 있으며, 그 프로퍼티를 통해 `GameObject`에 접근하게 할 수는 있습니다.
# Memory
# Time/Space Complexity
# OS
 - 오브젝트 파일(.o/.obj)는 C++ 컴파일러가 소스 코드를 기계어로 변환한 중간 파일이다. 여러 소스 파일을 각각 오브젝트 파일로 컴파일한 후, 링크 단계에서 각 파일을 합쳐 하나의 실행 파일을 만든다.
- 실행 파일(.out)은 오브젝트 파일들을 링커가 합친 실행 가능한 프로그램이다. 

# 결의
언제든지 시작할 준비가 되어있따.
