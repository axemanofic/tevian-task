1. Транзакции

На многих запросах висят "не нужные" транзакции. Например все методы "GET" обернуты декоратором with_transaction
из-за чего приложение провисает

2. Название PK для сущностей
В каждом API методе должно быть указано название PK для сущности. Например для таблицы "users" PK должно быть "id"

3. db.connect()
Приложение не запускалось из-за того что соединение с базой данных было уже открыто.

4. Poetry и другие
Следует использовать современные менеджеры зависимостей, например Poetry. 
Почему? При запуске приложения было обнаружено что метода app.before_first_request уже нет в новой версии Flask.
Чтобы это исправить рекомендую использовать Poetry для синхронизации версий зависимостей между разработчиками.

5. Swagger
Лучше использовать автодокументирование через код или собирать openapi.json. Далее все эти изменения подтянутся в Swagger UI
