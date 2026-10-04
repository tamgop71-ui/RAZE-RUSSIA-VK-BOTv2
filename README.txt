RAZE RUSSIA VK BOT — MYSQL FRESH BUILD
======================================

Эта версия сделана под Bothost/PHP 8.2 + MySQL.
SQLite больше НЕ используется.

ПРИЧИНА
-------
В предыдущем архиве бот требовал pdo_sqlite. На сервере у тебя настроены
MYSQL_* переменные, поэтому новый вариант работает напрямую через MySQL.

1. Создай НОВЫЙ репозиторий.
2. Загрузи bot.php.
3. Загрузи database.sql и импортируй его в уже созданную БД.
4. В Bothost поставь команду запуска:
   php bot.php
5. Перезапусти контейнер.

ПЕРЕМЕННЫЕ
----------
MYSQL_DATABASE = имя БД
MYSQL_HOST     = адрес MySQL
MYSQL_PASSWORD = пароль MySQL
MYSQL_PORT     = 3306
MYSQL_USER     = пользователь MySQL
OWNER_IDS      = 831772755
TZ             = Europe/Moscow
VK_GROUP_ID    = 241953865
VK_TOKEN       = токен сообщества

НЕ ПУБЛИКУЙ VK_TOKEN И ПАРОЛЬ MYSQL.

ИСПРАВЛЕНО
----------
- /help, !help, .help, /помощь, !помощь, /команды
- !staff / /staff / !состав
- !admin и !gadmin реально выдают роль 80
- глобальные команды работают даже для новой беседы
- /sysrole
- /sysban
- /sysunban
- /sysmute
- /sysunmute
- /syskick
- /sysstaff
- поддерживается !help@club...
- MySQL вместо SQLite
- PDO MySQL
- понятная ошибка при проблеме подключения к БД

ПЕРВАЯ ПРОВЕРКА
---------------
После запуска от OWNER_IDS:

/help
/staff
/admin 123456789
/staff
/sysrole 123456789 100
/sysstaff

ВАЖНО
------
Бот должен быть запущен как постоянный CLI-процесс.
Если Bothost показывает restarting, первым делом смотри логи процесса.
Нормальный первый вывод начинается примерно так:

=== RAZE RUSSIA BOT FULL BUILD - NO REPLY_TO ===

При проблеме MySQL бот теперь пишет:
MYSQL CONNECTION ERROR: ...

При отсутствии переменной:
ERROR: MySQL variables are required: ...

Токен в код не записан.
