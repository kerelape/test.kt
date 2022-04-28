# test.kt
Test library for kotlin (and other JVM languages)

#### Example

```kotlin
// src/test/Greeting.test.kts

test(Greeting::class) {
  
  "can greet a random person" {
    Assertion {
      Greeting("somebody").print() == "Hello, somebody!"
    }
  }
  
  fails "with empty name" {
    Greeting("").print()
  }
  
}

```
