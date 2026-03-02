# tippitytappity-design

tippitytappity is a program to practice typing


## Data model

```mermaid
classDiagram
  typing <|-- typingStats
  class typing{
        - name: string
        - email: string
        - password: string
        + login(user: string, pass: string) boolean
        + get_email() string
  }
  class typingStats{
        - Accurary: int
        - Speed (WPM): int
  }
```
