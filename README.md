# Описание YaMDb
![](https://img.shields.io/badge/YaMDB-black?style=for-the-badge&logo={LOGO}&logoColor=white)

![example workflow](https://github.com/VladBorisof/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)


Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).

Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.

Произведению может быть присвоен жанр (Genre) из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор.

Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

# Шаблон env-файла
```DB_ENGINE=
DB_NAME=
POSTGRES_USER=
POSTGRES_PASSWORD=
DB_HOST=
DB_PORT=
```

# Установка
## Как запустить проект:
Клонируйте репозиторий и перейдите в него из командной строки:

![img_2.png](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
```
git clone https://github.com/VladBorisof/infra_sp2.git

cd infra_sp2
```
## Запуск с помощью Docker
```
docker-compose up -d --build
```

```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```

### Загрузка данных из фикстур
```docker-compose exec web python manage.py loaddata fixtures.json```

## Запуск с настройкой виртуального окружения:

### Для Linux:
![img.png](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

```
python3 -m venv venv

source venv/bin/activate

python3 -m pip install --upgrade pip
```

### Для Windows:
![img_1.png](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
```
python -m venv venv

venv\Scripts\activate.bat

python -m pip install --upgrade pip
```

## Установка зависимостей из файла requirements.txt:

```pip install -r requirements.txt```

## Применение миграций:

```python3 manage.py migrate```

## Запуск проекта:

```python3 manage.py runserver```

## Документация к API

К проекту по адресу http://127.0.0.1:8000/redoc/ подключена документация API YaMDb. В ней описаны возможные запросы к API и структура ожидаемых ответов. Для каждого запроса указаны уровни прав доступа: пользовательские роли, которым разрешён запрос.