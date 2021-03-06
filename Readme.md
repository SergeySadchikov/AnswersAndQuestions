# СЕРВИС ВОПРОСОВ И ОТВЕТОВ

## Описание системы
Система реализована на PHP с использованием фреймворков Laravel и Bootstrap. В качестве СУБД использована система MySQL.


### Описание основных каталогов
app - здесь располагается собственно ваше приложение.
bootstrap - содержит файлы, которые осуществляют первоначальную загрузку (bootstraping) фреймворка и настраивают автозагрузку классов.
config - здесь находятся конфигурационные файлы приложения.
database - каталог для файлов миграций БД и "посева" данных.
public - является DocumentRoot домена вашего приложения и содержит статические файлы - css, js, изображения и т.п.
resources - здесь находятся шаблоны (Views), файлы локализации.
- resources/views/auth - шаблоны аутентификации
- resources/views/FAQ/layouts - родительские шаблоны приложения
- resources/views/FAQ - шаблоны приложения (пользовательская часть)
- resources/views/FAQ/admin - шаблоны приложения (интерфейс администратора)

routes - здесь находятся файлы маршрутизации
routes/web - директория маршрутов данного приложения
storage - этот каталог должен иметь права для записи в него извне и в нём Laravel хранит скомпилированные Blade-шаблоны, файлы сессии, файловый кэш и другие сгенерированные файлы, нужные для работы.
vendor - в этот каталог Composer устанавливает пакеты, указанные в composer.json.

### Папка приложения
В каталоге app находятся классы вашего Laravel-приложения. Этот каталог имеет неймспейс FAQ и классы в нём автозагружаются согласно стандарту 
PRS-4. Внутри находятся несколько дополнительных каталогов, таких как Console, Http и Providers.Первые два каталога содержат классы, предоставляющие API к вашему приложению по протоколам CLI (командная строка) и HTTP (работа через браузер). В Console находятся классы Artisan-команд, а в Http - контроллеры, фильтры и реквесты, т.е. классы 
валидации пользовательского ввода. Каталог Providers содержит различные вспомогательные механизмы вашего приложения (хелперы и сервисы). 
Дополнительно созданный каталог Repositories - позволяет вынести логику обращения к базе данных в отдельные классы. Также, каталог app содержит модели данного приложения:

### Структура базы данных
Структура базы данных приложения разработана с помощью СУБД MySQL.
####  Таблицы
- Users
- Authors
- Categories
- Questions
- Answers

## Описание интерфейса.


#### Пользовательская часть
- Пользователи могут просматривать категории, вопросы и ответы.
- Любой пользователь может задать вопрос, указав своё имя, адрес электронной почты, выбрав категорию и написав текст вопроса.
- Вопросы без ответов не публикуются на сайте.

### Интерфейс Администратора

- Просматривать список администраторов.
- Создавать новых администраторов.
- Изменять пароли существующих администраторов.
- Удалять существующих администраторов.
- Просматривать список тем. По каждой теме в списке видно сколько всего вопросов в ней, сколько опубликовано, сколько без ответов.
- Создавать новые темы.
- Удалять существующие темы и все вопросы в них.
- Просматривать вопросы в каждой теме. По каждому вопросу видно дату создания, статус (ожидает ответа / опубликован / скрыт).
- Удалять любой вопрос из темы.
- Скрывать опубликованные вопросы.
- Публиковать скрытые вопросы.
- Редактировать автора, текст вопроса и текст ответа.
- Перемещать вопрос из одной темы в другую.
- Добавлять ответ на вопрос с публикацией на сайте, либо со скрытием вопроса.
- Видеть список всех вопросов без ответа во всех темах в порядке их добавления. И иметь возможность их редактировать и удалять.

*По умолчанию создан один администратор  name: admin, password: admin.
Поле password хешируется.*

