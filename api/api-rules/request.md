## Запросы API
Структура запроса:

`версия_api/сущность/id`

Например, `v2/course/123`

- GET - list, read
- POST - create
- DELETE - delete
- PUT - update
- PATCH - не-CRUD методы

Наличие/отсутствие закрывающего слеша не имеет значения.
\* Для списка и создания id не указывается.

### Фильтрация
Для фильтрации данных необходимо в GET запросе указать параметры фильтрации в ключе search, например GET /v2/contracts?search[id]=123.

### Сортировка
Для сортировки по определенному полю, нужно указать его в GET параметре sort. Для обратной сортировки подставьте знак - перед параметром, например GET /v2/contracts?sort=number, GET /v2/certificates?sort=-fio.

### Указание полей
Для списка и просмотра, предусматривается ограничение по полям (по умолчанию закружаются не все поля, а основное, например, id, для запроса большего количества полей используется параметр, указывающий на них) условно назову параметр fields.

При апдейтах указывается через fields, какие поля вернуть

### Пагинация
Для использования пагинации можно указать следующие параметры:
- per-page - количество элементов на каждой странице;
- page - текущая страница;