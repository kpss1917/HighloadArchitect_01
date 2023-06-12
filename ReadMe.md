Инструкция по запуску
1. при необходимости поменять порты в файлах:
    docker-compose.yml
        ports:
        - '8000:8000'
        ports:
        - '54322:5432'

    HttpServer/db.py
        conn = psycopg2.connect(dbname='postgres', user='postgres', password='postgres', host='postgres', port=5432)

    HttpServer/httpServer.py
        server_address = ('', 8000)

2. запустить 
        docker-compose up

3. выполнить скрипт создания таблиц
     SQL/create_tables.sql
 
4. создать пользователя
    http://localhost:8000/user/register?user=1&first_name=Petr&second_name=Petrov&birthdate=2000-02-02&sex=True&biography=hobby&city=Moskow&password=123
5. посмотреть пользователя
    http://localhost:8000/get/1
6. залогиниться
    http://localhost:8000/login?user=1&password=123
