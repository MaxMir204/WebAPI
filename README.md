
---

# 📦 Web API для PostgreSQL

REST API, созданный на **ASP.NET Core**, для управления **клиентами** и их **заказами**.

---

## ✅ Функциональность

* Подключение и работа с **PostgreSQL**
* **CRUD**-операции для таблиц клиентов и заказов
* Получение данных с **фильтрацией и пагинацией**
* Использование **Dependency Injection**
* Интерактивная документация через **Swagger**

---

## 🛠️ Используемые технологии

* [.NET 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
* ASP.NET Core 8.0
* Entity Framework Core 9.0.4
* [Npgsql](https://www.npgsql.org/) — драйвер PostgreSQL
* Swagger (Swashbuckle)
* Встроенный DI-контейнер ASP.NET Core
* xUnit — модульное тестирование

---

## 🚀 Запуск проекта

1. Настройте строку подключения в `appsettings.json`:

   ```json
   "ConnectionStrings": {
     "DefaultConnection": "Host=localhost;Port=port;Database=mydb;Username=myuser;Password=mypassword"
   }
   ```

2. Установите зависимости:

   ```bash
   dotnet restore
   ```

3. Установите инструменты EF Core:

   ```bash
   dotnet tool install --global dotnet-ef
   ```

4. Примените миграции к базе данных:

   ```bash
   dotnet ef database update
   ```

5. Запустите проект:

   ```bash
   dotnet run --project API
   ```

6. Откройте браузер и перейдите по адресу:

   ```
   https://localhost:<порт>
   ```

---

## 📡 Поддерживаемые запросы

### 🔹 Clients

| Метод    | Endpoint                | Описание                                   |
| -------- | ----------------------- | ------------------------------------------ |
| `GET`    | `/api/Clients`          | Получение списка всех клиентов             |
| `GET`    | `/api/Clients/{id}`     | Получение клиента по ID                    |
| `GET`    | `/api/Clients/filtered` | Получение клиентов по фильтру с пагинацией |
| `POST`   | `/api/Clients`          | Создание нового клиента                    |
| `PUT`    | `/api/Clients/{id}`     | Редактирование клиента по ID               |
| `DELETE` | `/api/Clients/{id}`     | Удаление клиента по ID                     |

### 🔹 Orders

| Метод    | Endpoint                                    | Описание                                                     |
| -------- | ------------------------------------------- | ------------------------------------------------------------ |
| `GET`    | `/api/Orders`                               | Получение списка всех заказов (без информации о клиенте)     |
| `GET`    | `/api/Orders/{id}`                          | Получение заказа по ID                                       |
| `GET`    | `/api/Orders/filtered`                      | Получение заказов по фильтру с пагинацией                    |
| `GET`    | `/api/Orders/total-cost-of-birthday-orders` | Сумма заказов со статусом «Выполнен» в день рождения клиента |
| `GET`    | `/api/Orders/average-costs-by-hour`         | Средний чек по каждому часу (в порядке убывания)             |
| `POST`   | `/api/Orders`                               | Создание нового заказа                                       |
| `PUT`    | `/api/Orders/{id}`                          | Редактирование заказа по ID                                  |
| `DELETE` | `/api/Orders/{id}`                          | Удаление заказа по ID                                        |

---

## 🧪 Тесты

* Все методы контроллеров покрыты **unit-тестами** с использованием `xUnit` (проект `Tests`)

---
