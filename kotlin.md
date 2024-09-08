# Kotlin 스럽다 ?

**Kotlin스럽다**는 Kotlin의 고유한 설계 철학을 반영하고, 언어의 특징을 최대로 활용하는 프로그래밍 방식을 의미합니다. Kotlin은 단순히 코드의 간결함을 추구하는 언어가 아니라, 안전성, 표현력, 유연성을 강조하는 프로그래밍 언어입니다. 따라서 **Kotlin스럽다**는 코드를 더 안전하고, 명확하고, 효율적으로 작성하는 것을 의미합니다.

**Kotlin스럽다**는 다음과 같은 5가지 핵심 개념을 따르는 프로그래밍 방식을 의미합니다:

1. **안전성**, **null 안전성**의 극대화
2. **간결함**과 **보일러플레이트 제거**
3. **함수형 프로그래밍**의 적극적 활용
4. **확장 함수**를 통한 유연한 기능 확장
5. **Kotlin의 철학**을 반영한 디자인과 코드 스타일


### 1. **안전성: Null 안전성의 철저한 보장**

Kotlin의 가장 중요한 특징 중 하나는 **null 안전성**입니다. Kotlin은 **NullPointerException**을 방지하기 위해 기본적으로 **null을 허용하지 않는 타입 시스템**을 제공합니다. 이는 코드에서 null 관련 오류를 방지할 수 있으며, 더 안전한 프로그래밍을 가능하게 합니다.

Kotlin에서는 **Nullable 타입**과 **Non-nullable 타입**이 명확히 구분됩니다. 이를 통해 개발자는 null을 명시적으로 처리해야 하며, null 가능성을 미리 파악할 수 있습니다.

- **Nullable 타입**: `String?`처럼 `?`가 붙은 타입은 null을 허용하며, 이 경우 null 관련 처리(예: `?.` 연산자, 엘비스 연산자 `?:`)를 해야 합니다.
- **Non-nullable 타입**: 기본적으로 null을 허용하지 않는 타입이며, `String`은 null이 될 수 없습니다.

```kotlin
fun getLength(text: String?): Int {
    return text?.length ?: 0
}
```

- **안전한 호출 연산자 `?.`**: null인 경우 연산을 생략하며, 그렇지 않은 경우만 호출합니다.
- **엘비스 연산자 `?:`**: null인 경우 대체 값을 지정할 수 있습니다.

Kotlin스럽다 = **null 안전성**을 항상 염두에 두고 코드를 작성하는 것.

### 2. **간결함: 불필요한 보일러플레이트 코드 제거**

Kotlin은 개발자가 반복적으로 작성해야 하는 **보일러플레이트 코드를 제거**함으로써 코드를 간결하게 유지하도록 설계되었습니다. 그 대표적인 예가 데이터 클래스(data class)입니다. Java에서는 객체의 `toString()`, `equals()`, `hashCode()`와 같은 메서드를 개발자가 직접 작성해야 하지만, Kotlin의 **데이터 클래스**는 이를 자동으로 제공합니다.

데이터 클래스는 주로 데이터를 저장하는 용도로 사용됩니다. `data class`를 선언하는 것만으로도 모든 필드에 대한 기본 메서드를 자동으로 생성해줍니다.

```kotlin
data class User(val name: String, val age: Int)

fun main() {
    val user = User("Alice", 25)
    println(user)  // toString() 자동 생성
}
```

- **자동 생성된 메서드**: `toString()`, `equals()`, `hashCode()`, `copy()`.
- **간결성**: Java에서는 이러한 메서드를 모두 수동으로 작성해야 하지만, Kotlin은 이를 자동으로 처리하여 코드를 훨씬 간결하게 만들어줍니다.

Kotlin스럽다 = 반복적으로 작성해야 하는 **코드를 줄이고** 의미 있는 코드에만 집중하는 것.

### 3. **함수형 프로그래밍: 람다와 고차 함수의 적극 활용**

Kotlin은 **함수형 프로그래밍**을 강력하게 지원하는 언어입니다. 고차 함수(함수를 인자로 받거나 반환하는 함수)와 **람다식**을 통해 코드를 더 유연하고 모듈화할 수 있습니다. 이를 통해 반복적인 코드 작성을 줄이고, 더 재사용 가능하고 선언적인 코드를 작성할 수 있습니다.

**람다식**은 익명 함수로, 더 간결하고 직관적인 방식으로 함수를 작성할 수 있습니다. 또한, Kotlin은 `filter`, `map`, `forEach` 등의 **컬렉션 함수**를 제공하여 함수형 프로그래밍을 쉽게 할 수 있도록 지원합니다.

```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
val evenNumbers = numbers.filter { it % 2 == 0 }  // 람다식을 이용한 필터링
val squaredNumbers = numbers.map { it * it }  // 각 숫자를 제곱하는 맵핑
```

- **고차 함수**: 함수를 인자로 전달하거나 반환할 수 있습니다.
- **람다식**: 함수를 간결하게 표현할 수 있습니다.

Kotlin스럽다 = **함수형 프로그래밍의 장점을 이용**하여 코드를 더 직관적으로 만드는 것.

### 4. **확장 함수: 기존 클래스를 손쉽게 확장**

Kotlin의 **확장 함수**는 기존 클래스에 새로운 기능을 추가할 때 매우 유용한 도구입니다. 이 기능을 사용하면, 상속이나 기존 코드를 수정하지 않고도 클래스에 함수를 추가할 수 있습니다. 이러한 확장 함수는 기존 라이브러리에 새로운 기능을 추가할 때 특히 유용합니다. ( 확장함수는 컴퍼일 시에 정적 메소드로 변환되며, JVM에서 클래스의 메서드로 추가되지 않고, 클래스 외부에 정의된 함수로 취급되어집니다. ) 

확장 함수는 원래 클래스에 속하지 않는 함수이지만, **해당 클래스의 인스턴스를 확장**하여 마치 원래 메서드인 것처럼 사용할 수 있습니다. 예를 들어, `String` 클래스에 새 기능을 추가하고 싶다면, 확장 함수를 통해 손쉽게 구현할 수 있습니다.

```kotlin
fun String.shout(): String = this.uppercase() + "!"

fun main() {
    val message = "hello"
    println(message.shout())  // "HELLO!"
}
```

- **확장 함수**: 상속을 사용하지 않고도 기존 클래스에 새 기능을 추가할 수 있습니다.
- **유연성**: 기존 라이브러리를 수정하지 않고도 기능을 확장할 수 있습니다.

Kotlin스럽다 = **상속이나 코드 수정 없이** 필요한 기능을 유연하게 확장할 수 있는 방법을 사용하는 것.

### 5. **Kotlin의 철학: 안전성, 간결함, 함수형 프로그래밍을 지향**

Kotlin은 **개발자의 생산성과 코드 안전성**을 극대화하려는 철학을 가지고 있습니다. 이를 위해 다양한 기능들이 제공되며, 그 중 **스마트 캐스팅**, **디폴트 파라미터**, 디**스트럭처링** 등은 코드를 더 직관적이고 안전하게 만들어줍니다.

- **스마트 캐스팅**: Kotlin은 명시적 타입 캐스팅을 줄이기 위해, 조건문 내에서 자동으로 타입을 추론하여 **스마트 캐스팅**을 수행합니다.
    
    ```kotlin
    fun printLength(obj: Any) {
        if (obj is String) {
            println(obj.length)  // obj가 String일 때 자동으로 String으로 캐스팅됨
        }
    }
    ```
    
- **디폴트 파라미터**: Kotlin은 함수 파라미터에 기본값을 지정할 수 있어, **오버로딩**을 줄이고 코드를 간결하게 만듭니다.
    
    ```kotlin
    fun greet(name: String = "Guest") {
        println("Hello, $name!")
    }
    
    greet()  // "Hello, Guest!"
    greet("Alice")  // "Hello, Alice!"
    ```
    
- 디**스트럭처링: 디스트럭처링(destructuring)한다는 것은 객체가 가지고 있는 프로퍼티를 개별 변수들로 분해하여 할당하는 것을 말한다. 변수를 선언할 때 소괄호를 사용해서 분해하고자 하는 객체를 지정한다.**
    
    ```kotlin
    val (name, email) = cus
    println("name = $name, email = $email")
    
    // 특정 프로퍼티를 가져올 필요 없는 경우
    val (_, email) = cus // 첫번째 프로퍼티 제외
    ```
    

Kotlin스럽다 = **안전성, 간결함, 유연성**을 모두 만족시키는 디자인을 구현하는 것.

---

### **퀴즈: Kotlin스럽게 코드를 리팩토링하라**

요구사항

1. 사용자 목록을 관리하는 간단한 시스템을 구현합니다.
2. 사용자는 이름과 나이를 가집니다.
3. 시스템은 다음 기능을 제공해야 합니다:
    - 사용자 추가
    - 성인 사용자 필터링 (18세 이상)
    - 사용자 이름 출력
    - 평균 나이 계산

**Kotlin이지만 Kotlin 언어의 특성을 살리지 않은 코드 (bad case)**
```kotlin
// User
class User {
    val name: String
    val age: Int

    constructor(name: String, age: Int) {
        this.name = name
        this.age = age
    }
}

// UserManagementSystem
class UserManagementSystem {
    private val users = ArrayList<User>()

    fun addUser(name: String, age: Int) {
        users.add(User(name, age))
    }

    fun getAdultUsers(): List<User> {
        val adultUsers = ArrayList<User>()
        for (user in users) {
            if (user.age >= 18) {
                adultUsers.add(user)
            }
        }
        return adultUsers
    }

    fun printUserNames() {
        for (user in users) {
            println(user.name)
        }
    }

    fun calculateAverageAge(): Double {
        var sum = 0
        for (user in users) {
            sum += user.age
        }
        return if (users.size > 0) sum.toDouble() / users.size else 0.0
    }

// main 
fun main() {
    val system = UserManagementSystem()

    // 사용자 추가
    system.addUser("옥순", 25)
    system.addUser("상철", 17)
    system.addUser("영철", 30)

    println("모든 사용자 이름:")
    system.printUserNames()

    println("\n성인 사용자:")
    system.getAdultUsers().forEach { println("${it.name} (${it.age}세)") }

   println("\n평균 나이: ${system.calculateAverageAge()}")
}
```