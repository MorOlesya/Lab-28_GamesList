# Лабораторная работа №28. Веб-сервер на C#: список любимых игр с полным управлением

## Описание

В данной лабораторной работе было изучено:

- Использование веб-сервера на ASP.NET Core
- Закреплено понятия маршрутизации и HTTP-методов
- Научились хранить данные в памяти сервера
- Освоили новые HTTP-методы: POST, DELETE и PUT;
- Научились возвращать правильные HTTP-статусы (200, 201, 404);
- Познакомились с инструментом curl для отправки HTTP-запросов из
  терминала.

И в ходе работы было создано простое приложения для списка игр.

## Инструкция по запуску

Через терминал: `dotnet run` для запуска сервера

## Таблица всех маршрутов

| Метод  |     Маршрут     |      Описание       | Статус  |
| :----- | :-------------: | :-----------------: | :-----: |
| GET    |   /api/games    |  Получить все игры  |   200   |
| GET    | /api/games/{id} | Получить игру по id | 200/404 |
| POST   |   /api/games    |    Добавить игру    |   201   |
| DELETE | /api/games/{id} |    Удалить игру     | 204/404 |

## Примеры curl-команд

1. Получить все игры
`curl http://localhost:5227/api/games`
2. Получить игру с id=1
`curl http://localhost:5227/api/games/1`
3. Добавление игры через POST
`curl -X POST http://localhost:5227/api/games \
     -H "Content-Type: application/json" \-d "{\"title\": \"Stardew Valley\", \"genre\": \"Simulation\", \"releaseYear\": 
2016}"`
4. Обновить игру с id=2:
`curl -X PUT http://localhost:5227/api/games/2 \
     -H "Content-Type: application/json" \-d "{\"title\": \"Witcher 2: Assassins of Kings\", \"genre\": \"Action RPG\", 
\"releaseYear\": 2011}"`
5. Удалить игру с id=1:
`curl -X DELETE http://localhost:5227/api/games/1`
6. Увидеть статусный код:
`curl -i http://localhost:5000/api/games/2`