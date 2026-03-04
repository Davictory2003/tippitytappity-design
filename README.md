# tippitytappity-design

tippitytappity is a program to practice typing


## Data model

```mermaid
classDiagram
    direction LR
    class User {
        -string username
        -string email
        -string password
        +login(user, pass) bool
    }

    class PhraseBank {
        -list phrases
        +getRandomPhrase(type: string) string
    }

    class TypingTest {
        -string targetText
        -string currentInput
        -float startTime
        -float endTime
        +startTest()
        +calculateWPM() int
        +calculateAccuracy() int
    }

    class TestResult {
        -int wpm
        -int accuracy
        -timestamp date
    }
    User "1" --> "*" TestResult : has
    TypingTest --> PhraseBank : fetches phrase
    TypingTest ..> TestResult : generates
```
