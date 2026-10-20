# Диаграммы

## Диаграмма последовательности

```mermaid
sequenceDiagram
    actor User_sender as Пользователь-отправитель
    participant System as Система
    participant Model as ML-модель
    actor User_receiver as Пользователь-получатель

    User_sender->>System: Отправить сообщение пользователю-получателю
    System->>Model: Передать текст
    Model-->>System: Вернуть категорию (спам | обычное | осторожно)
    System->>User_receiver: Отправить сообщение с меткой
    System-->>User_sender: Сообщение отправлено
```

## Диаграмма классов

```mermaid
classDiagram
    class User {
        +int id
        +string name
    }

    class Message {
        +int id
        +string text
        +string category
    }

    class ClassificationResult {
        +string category
        +float confidence
    }

    User "1" --> "*" Message
    Message "1" --> "1" ClassificationResult
```