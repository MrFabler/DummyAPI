# DummyAPI
В этом файле представленно описание тестирования проекта DummyAPI


## Оглавление
1. [Описание Проекта](#Описание-Проекта)
2. [POST](#POST)




## Описание Проекта 
https://dummyapi.io/ представляет собой сервис для тестирования API. Для выполнения запросов необходимо сгенерировать app-id, путём регистрация на сайтеВ качестве объекта тестирования были взят объект **POST**

### POST
___
#### GET /post ( Get list )
Возвращает список публикаций по дате создания


**Response Body**

**List**
```js
{
  data: Array(Model)
  total: number(total items in DB)
  page: number(current page)
  limit: number(number of items on page)
}
```

**Post Preview**
```js
{
  id: string(autogenerated)
  text: string(length: 6-50, preview only)
  image: string(url)
  likes: number(init value: 0)
  tags: array(string)
  publishDate: string(autogenerated)
  owner: object(User Preview)
}
```

___
#### POST /post/create 
Создаёт новую публикацию от пользователя. Возвращает информацию о публикации


**Request Body**
Ключи owner и post обязательны.
```js
{
text: string(length: 6-50, preview only)
image: string(url)
likes: number(init value: 0)
tags: array(string)
owner: string(User id)
}
```

**Response Body**
```js
{
id: string(autogenerated)
text: string(length: 6-1000)
image: string(url)
likes: number(init value: 0)
link: string(url, length: 6-200)
tags: array(string)
publishDate: string(autogenerated)
owner: object(User Preview)
}
```

## Майнд-карта
Данная майнд-карта представляет собой набор тестов для тестирования объекта **POST**. Подробная проверка расписана для **Get List**, **Create Post**, **Update Post**, **Delete Post**

Карту можно [скачать](https://github.com/MrFabler/DummyAPI/blob/main/DummyAPIGitHub.xmind)

## Коллекция ручных тестов в Postman
В соответствии с майнд-картой были составлены ручные тесты.

Скачать коллекцию можно [тут](https://github.com/MrFabler/DummyAPI/blob/main/DummyAPI.postman_collection_For_Github.json)

## Коллекция авто-тестов в Postman
Также были оформлены авто-тесты для проверки цикла GET/POST/PUT/DELETE

Скачать коллекцию можно [тут](https://github.com/MrFabler/DummyAPI/blob/main/DummyAPI_Auto_Test.postman_collection_For_Github.json)

## Окружение
Для тестов было создано отдельное окружение. Оно обязательно для работы тестов.

Скачать окружение [тут](https://github.com/MrFabler/DummyAPI/blob/main/DummyAPI_environment.postman_environment_For_Github.json)
