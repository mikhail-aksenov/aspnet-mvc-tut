# Краткое введение в ASP.NET MVC

ASP.NET MVC - веб-фреймворк с открытым исходным кодом, разработанный компанией Microsoft, входит в семейство традиционных MVC-фреймворков, таких как Ruby on Rails, Spring MVC, и подобных.

Аббревиатура MVC расшифровывается как Model-View-Controller:

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/MVC-Process.png "MVC")

*Модель* - объект предметной области (заказ, предмет одежды или деталь автомобиля).
*Представление* - способ отображения модели, как в виде HTML-страницы, так и объектов в формате
XML, JSON и подобных.
*Контроллер* - объект, связывающий действия пользователя и модели.

Для закрепления создадим сайт для службы доставки пиццы с использование ASP.NET MVC.

## Инструментарий

Для комфортной работы вам понадобятся:
* MS SQL Server 2008 R2 и выше
* MS VS 2013 и выше

## Создание таблицы в БД.

На каждый запрос пользователя создается новый контроллер и память очищается, поэтому создадим модель для пиццы.

Откроем SQL Server Management Studio и создадим базу и таблицу Pizza.

У меня получилось следующее:

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/0-table.png "Table")

## Создаение проекта в Visual Studio

Запускаем Visual Studio и выбираем `File -> New -> Project`. Выбираем `Web`, вводим название и жмем OK.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/1-project-creation.png "Project creation")

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/2-project-creation.png "Project creation")

## Создание модели

Теперь сопоставим таблицу в SQL Server с классом в ASP.NET MVC. Нажимаем правой кнопкой на папку `Models` и выбираем `New Item`.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/3-model-creation.png "Model creation")

Выберем имя класс для контекста подключения к БД, например, PizzaContext.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/3-1-model-creation.png "Model creation")

Укажем Code First from Database. Класс сгенерируется по описанию полей в таблице.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/3-2-model-creation.png "Model creation")

Создадим новое подключение к SQL серверу и выберем таблицу Pizza.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/3-3-model-creation.png "Model creation")

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/3-4-model-creation.png "Model creation")

Теперь класс Pizza - модель, а класс PizzaContext - контекст подключения к БД.

## Создание контроллера и представлений

Теперь создадим контроллер и представления. Щелкнем правой кнопкой мыши по папке `Controllers` и выберем `New Scaffolded Item`.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/4-scaffold.png "Scaffold")


![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/4-1-scaffold.png "Scaffold")

Укажем модель и контекст. Я выбрал асинхронные контроллеры, потому что они более эффективно используют ресурсы,
но это необязательно. Также выберем `Layout`.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/4-2-scaffold.png "Scaffold")

Если генерация не выполнилась, то прочитайте внимательно текст ошибки, разберитесь и попробуйте снова.

## Демо

Запустите проект и в адресной допишите к адресу `Pizzas`.

![alt text](https://github.com/mikhail-aksenov/aspnet-mvc-tut/blob/master/images/5-demo.png "Demo")

## Литература для самостоятельной работы

[ASP.NET MVC](http://www.asp.net/mvc).