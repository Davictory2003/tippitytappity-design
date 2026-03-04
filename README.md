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
        -List<TestResult> history
        +login(user, pass) bool
        +getHistory() List~TestResult~
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
        -User user
        +startTest(user: User)
        +calculateWPM() int
        +calculateAccuracy() int
        +generateResult() TestResult
    }

    class TestResult {
        -int wpm
        -int accuracy
        -timestamp date
        -string phraseText
    }

    User "1" --> "*" TestResult : stores history
    TypingTest --> PhraseBank : fetches phrase
    TypingTest "1" --> "1" User : associated with
    TypingTest ..> TestResult : creates
```
