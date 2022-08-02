# diplom
[План тестирования](https://github.com/PavelStet/diplom/blob/main/documents/plan.md)

### Запуск приложения

Для запуска приложения необходим **Docker**

**Примечание**: Приложение запускалось через Docker на локальной машине.

* склонировать репозиторий ```https://github.com/PavelStet/diplom.git```
* запустить docker container ```docker-compose up -d --force-recreate```.
*   Дождаться пока контейнеры запустятся
* в терминале IntelliJ IDEA запустить SUT:
    - с использованием БД MySQL
      командой ```java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar artifacts/aqa-shop.jar```
    - с использованием БД PostgreSQL
      командой ```java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar artifacts/aqa-shop.jar```
* запустить автотесты командой:
    - для конфигурации БД MySql:  
      ```./gradlew clean test "-Ddb.url=jdbc:mysql://localhost:3306/app" ```
    - для конфигурации БД PostgreSQL:  
      ```./gradlew clean test "-Ddb.url=jdbc:postgresql://localhost:5432/app" ```

* запустить отчеты командой:

```./gradlew allureServe (запуск и открытие отчетов)```