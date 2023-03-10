# api_yamdb

Проект YaMDb собирает отзывы пользователей на произведения. Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка». Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Жуки» и вторая сюита Баха. Список категорий может быть расширен (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).

Произведению может быть присвоен жанр из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»).

Добавлять произведения, категории и жанры может только администратор.

Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

Пользователи могут оставлять комментарии к отзывам.

Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные пользователи.

  

# Запуск проекта в dev-режиме

- Клонируйте репозиторий
```
git@github.com:DenisLukianov21/infra_sp2.git
```
- Установите и активируйте виртуальное окружение
```
python3 -m venv venv
source /venv/bin/activate
```

- Установите зависимости из файла requirements.txt

``` pip install -r requirements.txt ```

- Перейдите в папку с файлом docker-compose.yaml и запустите контейнеры

``` docker-compose up -d --build ```
- Выполните миграции и создайте суперпользователя
```
docker-compose exec web python manage.py makemigrations
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
```

# Импорт из CSV

1.  создать терминал cmd
2.  перейти в директорию где расположен  sqlite3.exe ( cd api_yamdb)
3.  запустить из терминала sqlite3.exe и выбрать нужную БД ( sqlite3.exe db.sqlite3 )
4.  далее в терминале выбираем мод для csv командой ( .mode csv )
5.  потом импортируем нужный нам csv файл в БД ( .import название_файла.csv название_таблицы_в_которую_импортируем ) например ( .import genre.csv reviews_genre )

# Используемые технологии

- Python 3.8

- Django 2.2

- Django Rest Framework

- Simple-JWT

- PostreSQL

- Docker

# Шаблон наполнения .env
```
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

# Документация к проекту

Документация для API после установки доступна по адресу

```
http://127.0.0.1/redoc/
```

# Авторы

Илья Ховрин, 
Руслан Брылев, 
Лукьянов Денис.