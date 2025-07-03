# Тестирование API (REST и SOAP) в Postman

## 🛠 Инструменты
- **Postman**  
  - [Коллекция REST-запросов](https://drive.google.com/file/d/15xk0_-mDFAgxMSv6NjpVGxE9tuSpj5-P/view?usp=drive_link)
  - [Коллекция SOAP-запросов](https://drive.google.com/file/d/1ellEzPZeZ2wm7DmxYFhr_-lD4L6umhSK/view?usp=drive_link)
- **Swagger**: [Документация API](https://qa.demoshopping.ru/api-docs/)

## 📚 Тест-документация
### Тест-кейсы Postman
[![Postman Tests](https://img.shields.io/badge/Postman-Test_Cases-blue)](https://drive.google.com/file/d/1uObbbVbZ6eIVaFGu_0OHU3-TWdLMDphn/view?usp=sharing)  

## 🐞 Найденные дефекты
### Баг #1: 400 ошибка при валидной регистрации
**Шаги воспроизведения:**
1. Отправить POST-запрос на {{base_url}}/register:
```json
{
  "username": "кошка",
  "password": "{{password}}"
}
```
**Ожидаемый результат:**  
Код 200, создание пользователя.  
**Фактический результат:**  
```json
{
  "error": "Неверные данные пользователя",
  "validationErrors": ["Логин должен содержать от 3 до 15 символов"]
}
```

### Баг #2: 200 ответ на несуществующий URL
**URL:** `GET http://qa.demoshopping.ru/users (вместо https)  
**Ожидаемый результат:** 404 Not Found  
**Фактический результат:** 200 OK с пустым телом.

---

## 📊 Статистика тестирования
- Протестировано эндпоинтов: 22
- Найдено дефектов: 8
