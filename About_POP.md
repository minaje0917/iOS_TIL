# POP ( Protocol Oriented Programming )

1. 객체 지향 프로그래밍<br>
사물을 객체로 형성하여 공통점을 갖는 모든 곳에서 상속받는 객체 내부의 모든 로직을 캡슐화한다. <br>
의도하지 않아도 상속했다는 이유로 모든 속성과 행위를 공유해야한다. <br>
복잡한 상속 구조를 지닌 클래스를 상속했다면 원하는 클래스를 참조해야할 떄 다운캐스팅을 해야한다. <br>
또한 가장 큰 단점은 단 하나의 SuperClass만 상속할 수 있다. <br>
시간이 흐르면 기능도 확장하기 마련이므로 이에 따라 복잡도가 높아지고 관리도 어려워진다. 
2. POP <br>
필요한 부분만 프로토콜로 분리해서 만들 수 있고 다중프로토콜을 구현할 수 있다.<br>
프로토콜 규칙을 class, struct, enum에 적용할 수 있기 떄문에 확장부분에서도 객체 지향 프로그래밍보다 유연하다. <br>  

3. Example <br>
스위프트는 다른 언어와 달리 클래스로 구현된 타입보다는 대부분 구조체로 기본 타입이 구현되어 있습니다. <br>
상속도 되지 않은 구조체로 공통 기능을 가질 수 있는 방법에는 프로토콜과 익스텐션이 있습니다. <br>

    ``` swift 
    protocol Walkable {
        var isBareFoot: Bool { get set }
        
        func walk()
    }

    struct Person: Walkable {
        var isBareFoot: Bool
        var name: String
        
        func walk() {
            print("\(name)은 걷습니다")
        }
    }

    struct Animal: Walkable {
        var isBareFoot: Bool
        
        func walk() {
            print("\(name)은 걷습니다")
        }
    }
    ```
    프로토콜을 채택 시 프로토콜이 요구하는 사항을 모두 구현해주어야한다.<br>

    예를 들어 프로토콜에 많은 요구사항들이 있고, 많은 구조체에서 채택을 했다면 많은 중복된 코드를 사용해야 할 거다. <br>