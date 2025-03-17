# Стартовый докер для Laravel

## Структура

- `.tmp/` - После запуска докера содержит файлы базы данных или другие файлы которые необходимо хранить локально.
- `docker/` - Папка для конфигураций и прочих файлов докера
- `laravel/` - Главная папка приложения Laravel
- `.env` - Файл содержит все переменные для докера
- `.gitignore` - Стандартный гитигнор файл
- `docker-compose.yml` - Конфигурация докера
- `readme.md` - Документация проекта

## Доступы по умолчанию
- **Laravel**
  - URL: http://localhost:8000
- **phpMyAdmin** 
  - Dashboard: http://localhost:8181
  - Login: laravel 
  - Password: laravel

## Установка

1. Поднимаем докер

```bash
docker-compose up -d
```

2. Запускаем composer

```bash
docker-compose run --rm composer bash
```

3. Устанавливаем Laravel  
   _(папка должна быть пустая, нужно удалить `laravel/.gitkeep`)_

```bash
composer create-project laravel/laravel .
```

4. Закрываем Composer

```bash
exit
```

5. В файле `laravel/.env` прописать данные для базы данных согласно параметрам которые присвоены докеру, например:

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=laravel
DB_PASSWORD=laravel
```

6. Выполнить миграцию базы данных

```bash
docker-compose run --rm artisan migrate
```

## Сервисы

### Composer

```bash
docker-compose run --rm composer bash
```

### Node.js

```bash
docker-compose run --rm node bash
```

### Artisan

```bash
docker-compose run --rm artisan <command>
```

_--rm означает, что контейнер будет удалён после выхода._

