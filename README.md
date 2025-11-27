# Лабораторна робота №5  
## Юніт-тестування класу BoardGame (MSTest)

Цей репозиторій містить два проєкти:
1. **Основний проєкт** — реалізація класу `BoardGame` (з Лабораторної №4).
2. **Тестовий проєкт** — набір юніт-тестів `BoardGameTests`, написаних за допомогою MSTest.

---

## 📌 Мета роботи
Опанувати створення модульних тестів, навчитися покривати бізнес-логіку за допомогою юніт-тестування та аналізувати коректність роботи класів.

---

## 📦 Структура репозиторію

```
/ProjectRoot
├── BoardGameApp/               – основний проєкт
│   └── BoardGame.cs            – реалізація класу
│
├── BoardGameTests/             – тестовий проєкт MSTest
│   └── BoardGameTests.cs       – тести до всіх методів класу
│
└── README.md
```

---

## 🧩 Опис класу BoardGame

Клас моделює настільну гру та містить:

- Назву, видавця, жанр  
- Кількість гравців  
- Ціну й знижку  
- Перевантажені конструктори  
- Методи `DisplayInfo()`, `PlayDemo()`, `GetDiscountedPrice()`, `ToString()`  
- Статичний метод `TryParse()`  

### UML-діаграма основного класу

```
BoardGame
-----------------------------------
+ Name : string
+ Publisher : string
+ Genre : string
+ Players : int
+ Price : decimal
+ DiscountRate : decimal
-----------------------------------
+ BoardGame()
+ BoardGame(name : string)
+ BoardGame(name : string, genre : string, price : decimal)
+ BoardGame(name : string, publisher : string, genre : string,
            players : int, price : decimal)
-----------------------------------
+ DisplayInfo() : string
+ PlayDemo() : string
+ GetDiscountedPrice() : decimal
+ ToString() : string
+ static TryParse(input : string, out game : BoardGame) : bool
```

---

## 🧪 Опис тестового класу BoardGameTests

Тестовий проєкт містить **20 юніт-тестів**, що покривають:

- усі конструктори  
- усі властивості  
- коректні сценарії  
- помилкові сценарії  
- поведінку методів  
- статичну логіку  

### UML-структура тестового класу

```
BoardGameTests --> BoardGame
-------------------------------------------------------
+ Ctor_Full_SetAllFields()
+ Ctor_NoParams_DefaultValues()
+ Ctor_OneParam_NameSet()
+ Ctor_ThreeParams_SetFields()

+ DisplayInfo_NoExceptions()
+ DisplayInfo_Short_NoExceptions()
+ DisplayInfo_WithPublisher_NoExceptions()

+ GetDiscountedPrice_Throws_WhenNegative()
+ GetDiscountedPrice_WorksCorrectly()

+ Parse_CorrectString_ReturnsObject()
+ Parse_Empty_ThrowsArgumentException()
+ Parse_InvalidFields_ThrowsFormatException()

+ PlayDemo_NoExceptions()

+ Property_SetGenre()
+ Property_SetPlayers()

+ Static_DiscountRate_Invalid_Throws()
+ Static_DiscountRate_Valid_Set()

+ ToString_ReturnsCorrectFormat()

+ TryParse_Correct_ReturnsTrue()
+ TryParse_Wrong_ReturnsFalse()
-------------------------------------------------------
```

---

## ▶️ Запуск тестів

### Через Visual Studio:
```
Test → Run All Tests
```

### Через термінал:
```
dotnet test
```

---

## ✔️ Результати виконання тестів
Усі 20 тестів успішно проходять, що підтверджує коректність реалізації функціоналу класу `BoardGame`.

---

## 📄 Ліцензія
Проєкт створено для навчальних цілей у межах дисципліни  
**«Об’єктно-орієнтоване програмування»**.
