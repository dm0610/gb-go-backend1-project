## HW08
###  Моё приложение представляет из себя простой REST API. API будет предоставлять точки для доступа к «продуктам» и управления ими.

- Создание нового продукта
- Обновление существующего продукта
- Удаление существующего продукта
- Получение существующего продукта
- Получение списка продуктов.

### API Спецификация

<p> Создать новый продукт в ответ на корректный запрос POST по пути /product,
<p> Обновить продукт в ответ на корректный запрос PUT по пути /product/{id},
<p> Удалить продукт в ответ на корректный запрос DELETE/product,
<p> Получить продукт в ответ на корректный запрос GET по пути /product/{id},
<p> Получить список продуктов в ответ на корректный запрос GET по пути /products.


#### Требуемые модули:
- mux – The Gorilla Mux router,
- pq – The PostgreSQL driver.

### Структуры таблиц:
Таблица products содержит поля:
- id – the primary key
- name – Имя продукта
- price – Цена продукта

### CI
<p> Шаги в CI:
- Lint
- Test
- Build app
- Set up Docker Buildx
- Login to DockerHub
- Build image and push to Docker Hub

### CD
<p> Шаги в CD в Heroku
- пока не сделано, в процессе.
  
### Hands-On deploy in Heroku
<p>https://productapi-01.herokuapp.com/products

<p> Пример создания записи в базе: curl -X POST -H "Content-Type: application/json" --data '{"id":1,"name":"milk","price":1.14}'  https://productapi-01.herokuapp.com/product
### Hands-On deploy in K8S
<p> Шаги в CD в Yandex Cloud
- Сделал чарты для postgresql(скачал bitnami) и для приложений. В папке deploy
- Застрял на ингрессе. Кластер-то свой поднял и развернул оба приложения, но потом вспомнил, что нужно ещё публичный DNS заказать. Пока кластер погасил 