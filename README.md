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

## Структура базы данных

```mermaid
graph TD;
    UserStats[UserStats<br/>id, user_id, username, mmr, total_tests, last_test_date]
    UserProgress[UserProgress<br/>id, user_id, level, current_question, correct_answers, is_testing, last_answer_time, question_ids]
    Question[Question<br/>id, level, question_text, option1, option2, option3, option4, correct_option]
    CustomTest[CustomTest<br/>id, name, author_id, author_username, created_at]
    CustomQuestion[CustomQuestion<br/>id, test_id, question_text, option1, option2, option3, option4, correct_option]
    
    CustomTest --> CustomQuestion
    UserStats -- "Рейтинг (MMR)" --> UserProgress
    Question -- "Вопросы для тестов" --> UserProgress
    CustomTest -- "Автор" --> UserStats
```
