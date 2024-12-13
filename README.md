# GREEN-API_Test

```
https://wineperm.github.io/GREEN-API_Test/
```

Этот репозиторий содержит простую HTML-страницу, которая взаимодействует с GREEN-API для выполнения различных действий, таких как получение настроек, получение состояния экземпляра, отправка сообщений и отправка файлов по URL. Страница стилизована с помощью CSS и включает функции JavaScript для обработки API-запросов. Также включен рабочий процесс GitHub Actions для автоматического развертывания страницы на GitHub Pages при пушах в ветку `main`.

## Возможности

- **Получение настроек**: Получает настройки экземпляра.
- **Получение состояния экземпляра**: Получает состояние экземпляра.
- **Отправка сообщения**: Отправляет сообщение на указанный номер телефона.
- **Отправка файла по URL**: Отправляет файл с указанного URL на указанный номер телефона.

## Использование

1. **Клонирование репозитория**:
   ```sh
   git clone https://github.com/wineperm/GREEN-API_Test.git
   cd GREEN-API_Test
   ```

2. **Настройка переменных окружения**:
   - Создайте файл `.env` в корневом каталоге проекта.
   - Добавьте ваши `ID_INSTANCE` и `API_TOKEN_INSTANCE` в файл `.env`:
     ```env
     ID_INSTANCE=your_id_instance
     API_TOKEN_INSTANCE=your_api_token_instance
     ```

3. **Открытие HTML-файла**:
   - Откройте `index.html` в вашем браузере для взаимодействия с GREEN-API.

## GitHub Actions Workflow

Репозиторий включает рабочий процесс GitHub Actions для развертывания HTML-страницы на GitHub Pages. Рабочий процесс запускается при пушах в ветку `main`.

### Шаги рабочего процесса

1. **Проверка репозитория**:
   - Проверяет код репозитория.

2. **Установка переменных окружения**:
   - Устанавливает переменные окружения `ID_INSTANCE` и `API_TOKEN_INSTANCE` из GitHub Secrets.

3. **Развертывание на GitHub Pages**:
   - Развертывает содержимое репозитория в ветку `gh-pages` с использованием действия `peaceiris/actions-gh-pages`.

## Watch the Demo Video

[![Watch the video](https://img.youtube.com/vi/4y04DgEkNRo/0.jpg)](https://www.youtube.com/watch?v=4y04DgEkNRo)

![Alt text](https://github.com/wineperm/GREEN-API_Test/blob/main/check.jpg)

Проверка работоспособности &#8593
