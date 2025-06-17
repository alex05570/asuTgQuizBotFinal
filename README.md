# ASU Quiz Bot 🤖

Telegram-бот для тестирования знаний Java, Python и SQL с разными уровнями сложности.

## Функции

- Тесты по Java, Python и SQL (Junior/Middle/Senior)
- Создание и прохождение пользовательских тестов
- Система рейтинга MMR и таблица лидеров
- Подробные объяснения к ответам

## Установка

```bash
# Клонировать репозиторий
# Установить зависимости
pip install -r requirements.txt

# Создать файл .env
echo 'BOT_TOKEN="ваш_токен_бота"' > .env

# Запустить
python main.py
```

## Стек технологий

- Python 3.x
- python-telegram-bot
- SQLAlchemy
- SQLite
- python-dotenv

## Структура проекта

- `bot.py` - основной файл бота
- `database.py` - работа с БД
- `*_questions.py` - вопросы по языкам
- `custom_tests.py` - пользовательские тесты
- `asu_quiz.db` - база данных SQLite
- `.env` - токен бота
