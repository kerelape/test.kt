# test.kt
Test library for kotlin (and other JVM languages)

#### Example

```kotlin
// src/test/Greeting.test.kts

test(Greeting::class) {
  
  // Arbitary test
  "can greet a random person" {
    Assertion { // Every test must return an Assertion object (fun interface Assertion, with one method, assert returning Boolean)
      Greeting("somebody").print() == "Hello, somebody!"
    }
  }
  
  // Test that runs the block and returns true if the block fails
  fails "with empty name" {
    Greeting("").print()
  }
  
  can "print random name" {
    val name = listOf("John", "David", "Jake").random()
    equal(
      Greeting(name).print(),
      name
    )
  }
  
}

```
