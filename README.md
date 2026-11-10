# 🐧 Linux Mastery
### Полный справочник Linux для системного администратора и DevOps-инженера

![Linux](https://img.shields.io/badge/Linux-Administrator-FCC624?logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-Server-E95420?logo=ubuntu&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-Scripting-4EAA25?logo=gnubash&logoColor=white)
![DevOps](https://img.shields.io/badge/DevOps-Handbook-blue)

Практический справочник по администрированию Linux. Содержит основные команды, примеры использования, конфигурации, диагностику, автоматизацию и рекомендации по безопасности.

**Основная платформа:** Ubuntu Server 22.04 / 24.04 LTS, Debian 12/13.

**Для кого:**
- Linux System Administrators
- Junior DevOps Engineers
- Infrastructure Engineers
- IT Support Engineers
- Начинающие Linux-администраторы

---

# 📚 Содержание

1. [Знакомство с Linux](#1-знакомство-с-linux)
2. [Терминал и командная строка](#2-терминал-и-командная-строка)
3. [Файловая система Linux](#3-файловая-система-linux)
4. [Работа с файлами и каталогами](#4-работа-с-файлами-и-каталогами)
5. [Поиск файлов и информации](#5-поиск-файлов-и-информации)
6. [Права доступа и владельцы](#6-права-доступа-и-владельцы)
7. [Пользователи и группы](#7-пользователи-и-группы)
8. [Управление процессами](#8-управление-процессами)
9. [Systemd и управление службами](#9-systemd-и-управление-службами)
10. [Логи и журналирование](#10-логи-и-журналирование)
11. [Управление пакетами](#11-управление-пакетами)
12. [Сеть и диагностика](#12-сеть-и-диагностика)
13. [SSH и удалённое администрирование](#13-ssh-и-удалённое-администрирование)
14. [Диски и файловые системы](#14-диски-и-файловые-системы)
15. [LVM и RAID](#15-lvm-и-raid)
16. [Bash и автоматизация](#16-bash-и-автоматизация)
17. [Cron и планировщик задач](#17-cron-и-планировщик-задач)
18. [Переменные окружения](#18-переменные-окружения)
19. [Архивирование и резервное копирование](#19-архивирование-и-резервное-копирование)
20. [Firewall и безопасность](#20-firewall-и-безопасность)
21. [Nginx и веб-сервер](#21-nginx-и-веб-сервер)
22. [Мониторинг системы](#22-мониторинг-системы)
23. [Диагностика неисправностей](#23-диагностика-неисправностей)
24. [Загрузка Linux и архитектура](#24-загрузка-linux-и-архитектура)
25. [Docker и контейнеризация](#25-docker-и-контейнеризация)
26. [Git для Linux-администратора](#26-git-для-linux-администратора)
27. [Полезные конфигурационные файлы](#27-полезные-конфигурационные-файлы)
28. [Полезные сочетания команд](#28-полезные-сочетания-команд)
29. [Типовые аварийные ситуации](#29-типовые-аварийные-ситуации)
30. [Чек-лист Linux Administrator](#30-чек-лист-linux-administrator)

---

# 1. Знакомство с Linux

## 1.1. Что такое Linux

Linux — семейство операционных систем на базе ядра Linux.

Основные компоненты:

| Компонент | Назначение |
|---|---|
| Kernel | Ядро операционной системы |
| Shell | Интерфейс взаимодействия с системой |
| Bash | Командная оболочка |
| Systemd | Инициализация и управление службами |
| GNU Coreutils | Основные системные утилиты |
| Filesystem | Организация хранения данных |
| Package Manager | Управление программным обеспечением |

## 1.2. Популярные дистрибутивы

| Дистрибутив | Основа | Применение |
|---|---|---|
| Ubuntu | Debian | Серверы, облака, Desktop |
| Debian | Независимый | Серверы |
| Rocky Linux | RHEL-compatible | Enterprise |
| AlmaLinux | RHEL-compatible | Enterprise |
| Fedora | Независимый | Разработка |
| Arch Linux | Независимый | Продвинутые пользователи |

## 1.3. Узнать информацию о системе

```bash
# Информация о системе
uname -a

# Версия ядра
uname -r

# Архитектура
uname -m

# Информация о дистрибутиве
cat /etc/os-release

# Версия Ubuntu
lsb_release -a

# Имя компьютера
hostname

# Информация о системе
hostnamectl

# Время работы системы
uptime

# Текущая дата
date

# Часовой пояс
timedatectl
```

## 1.4. Обновление системы

```bash
# Обновить список пакетов
sudo apt update

# Обновить установленные пакеты
sudo apt upgrade

# Полное обновление с изменением зависимостей
sudo apt full-upgrade

# Удалить ненужные зависимости
sudo apt autoremove

# Очистить кэш пакетов
sudo apt clean

# Перезагрузка
sudo reboot

# Выключение
sudo poweroff
```

---

# 2. Терминал и командная строка

## 2.1. Основные команды

| Команда | Назначение | Пример |
|---|---|---|
| `pwd` | Текущая директория | `pwd` |
| `whoami` | Текущий пользователь | `whoami` |
| `id` | UID/GID | `id` |
| `date` | Дата и время | `date` |
| `clear` | Очистить терминал | `clear` |
| `history` | История команд | `history` |
| `man` | Руководство | `man ls` |
| `help` | Помощь Bash | `help cd` |
| `which` | Путь к программе | `which python3` |
| `type` | Тип команды | `type cd` |
| `alias` | Псевдонимы | `alias ll='ls -lah'` |

## 2.2. Получение справки

```bash
# Руководство
man ls

# Краткая справка
ls --help

# Найти команду в документации
apropos network

# Поиск справочных страниц
man -k systemd

# Выход из man
q
```

## 2.3. История команд

```bash
# Показать историю
history

# Последние 20 команд
history 20

# Очистить историю текущей сессии
history -c

# Выполнить предыдущую команду
!!

# Повторить команду под номером 100
!100

# Найти предыдущую команду по тексту
!ssh
```

## 2.4. Полезные сочетания клавиш

| Сочетание | Действие |
|---|---|
| `Ctrl + C` | Прервать команду |
| `Ctrl + Z` | Приостановить процесс |
| `Ctrl + D` | Завершить ввод / выход |
| `Ctrl + L` | Очистить экран |
| `Ctrl + A` | Начало строки |
| `Ctrl + E` | Конец строки |
| `Ctrl + U` | Удалить до начала строки |
| `Ctrl + K` | Удалить до конца строки |
| `Ctrl + R` | Поиск в истории |
| `Tab` | Автодополнение |
| `!!` | Последняя команда |

---

# 3. Файловая система Linux

## 3.1. Основные каталоги

| Каталог | Назначение |
|---|---|
| `/` | Корневая директория |
| `/bin` | Основные исполняемые программы |
| `/sbin` | Системные программы |
| `/boot` | Файлы загрузчика и ядра |
| `/dev` | Устройства |
| `/etc` | Конфигурации |
| `/home` | Домашние каталоги пользователей |
| `/root` | Домашний каталог root |
| `/lib` | Системные библиотеки |
| `/media` | Автоматические точки монтирования |
| `/mnt` | Временные точки монтирования |
| `/opt` | Дополнительное ПО |
| `/proc` | Виртуальная файловая система процессов и ядра |
| `/sys` | Информация об устройствах и ядре |
| `/tmp` | Временные файлы |
| `/usr` | Пользовательские программы и данные |
| `/var` | Изменяемые данные |
| `/run` | Данные текущего запуска системы |

## 3.2. Важные подкаталоги

```text
/etc/ssh/                 SSH configuration
/etc/fstab                Mount configuration
/etc/hosts                Local hostname resolution
/etc/hostname             System hostname
/etc/passwd               User accounts
/etc/shadow               Password hashes
/etc/group                Groups
/etc/sudoers              Sudo configuration

/var/log/                 System logs
/var/cache/               Application caches
/var/lib/                 Application state
/var/www/                 Web applications
/var/tmp/                 Temporary files

/home/user/               User directory
/root/                    Root directory

/usr/bin/                 Executable programs
/usr/local/bin/           Locally installed programs
/usr/local/sbin/          Local administration programs

/opt/                     Third-party applications
```

## 3.3. Абсолютные и относительные пути

Абсолютный путь:

```bash
/etc/ssh/sshd_config
```

Относительный путь:

```bash
./project/config.py
```

Специальные обозначения:

| Обозначение | Значение |
|---|---|
| `.` | Текущий каталог |
| `..` | Родительский каталог |
| `~` | Домашний каталог |
| `/` | Корень файловой системы |
| `-` | Предыдущий каталог в `cd -` |

---

# 4. Работа с файлами и каталогами

## 4.1. Создание каталогов

```bash
# Создать каталог
mkdir project

# Создать несколько каталогов
mkdir logs backups scripts

# Создать вложенные каталоги
mkdir -p /opt/project/logs/archive

# Создать каталог с определёнными правами
mkdir -m 750 private
```

## 4.2. Создание файлов

```bash
# Создать пустой файл
touch file.txt

# Создать файл через echo
echo "Hello Linux" > file.txt

# Добавить текст в конец
echo "New line" >> file.txt

# Создать файл через cat
cat > file.txt
```

Разница между перенаправлениями:

| Оператор | Назначение |
|---|---|
| `>` | Перезаписать файл |
| `>>` | Добавить в конец |
| `<` | Передать файл на вход |
| `2>` | Перенаправить stderr |
| `2>>` | Добавить stderr в файл |
| `&>` | Перенаправить stdout и stderr |
| `2>&1` | Направить stderr туда же, куда stdout |

Примеры:

```bash
# Перезаписать файл
echo "Test" > output.txt

# Дописать строку
echo "Second line" >> output.txt

# Сохранить ошибки
command 2> errors.log

# Сохранить вывод и ошибки
command > output.log 2>&1

# Отбросить вывод
command > /dev/null 2>&1
```

## 4.3. Копирование и перемещение

```bash
# Копирование файла
cp file.txt backup.txt

# Копирование каталога
cp -r project project_backup

# Сохранить атрибуты
cp -a project/ backup/

# Подробный вывод
cp -v file.txt backup.txt

# Перемещение
mv file.txt /tmp/

# Переименование
mv old.txt new.txt
```

## 4.4. Удаление

```bash
# Удалить файл
rm file.txt

# Удалить каталог
rmdir empty_directory

# Удалить каталог с содержимым
rm -r directory

# Принудительное удаление
rm -rf directory
```

⚠️ `rm -rf` опасна. Перед её использованием обязательно проверяй путь.

Особенно опасны команды с переменными, пустыми значениями и неправильно сформированными путями.

## 4.5. Просмотр содержимого файлов

```bash
# Весь файл
cat file.txt

# Постраничный просмотр
less file.txt

# Первые 10 строк
head file.txt

# Последние 10 строк
tail file.txt

# Последние 50 строк
tail -n 50 file.txt

# Следить за изменениями файла
tail -f application.log

# Последние 100 строк и наблюдение
tail -n 100 -f application.log

# Нумерация строк
nl -ba file.txt

# Подсчитать строки, слова и символы
wc file.txt

# Только количество строк
wc -l file.txt
```

## 4.6. Сравнение файлов

```bash
# Сравнить два файла
diff file1.txt file2.txt

# Сравнение с контекстом
diff -u file1.txt file2.txt

# Побайтовое сравнение
cmp file1.txt file2.txt

# Хеш файла
sha256sum file.txt
```

---

# 5. Поиск файлов и информации

## 5.1. Find

Поиск файлов и каталогов.

```bash
# Найти файл
find /etc -name "ssh_config"

# Поиск без учёта регистра
find /etc -iname "SSH_CONFIG"

# Найти все .log
find /var/log -type f -name "*.log"

# Найти только каталоги
find /opt -type d

# Найти только файлы
find /opt -type f

# Файлы больше 100 MB
find / -type f -size +100M 2>/dev/null

# Файлы старше 7 дней
find /var/log -type f -mtime +7

# Файлы, изменённые за последние сутки
find /var/log -type f -mtime -1

# Найти и удалить временные файлы
find /tmp -type f -name "*.tmp" -delete

# Найти файлы и вывести размер
find /var/log -type f -exec du -h {} \;
```

## 5.2. Grep

Поиск текста.

```bash
# Найти слово в файле
grep "error" application.log

# Без учёта регистра
grep -i "error" application.log

# Показать номера строк
grep -n "error" application.log

# Рекурсивный поиск
grep -r "listen" /etc/nginx/

# Исключить регистр
grep -ri "failed" /var/log/

# Показать строки без совпадений
grep -v "INFO" application.log

# Показать количество совпадений
grep -c "error" application.log

# Контекст до и после совпадения
grep -C 3 "error" application.log

# Несколько шаблонов
grep -E "error|warning|failed" application.log
```

## 5.3. Locate

```bash
# Найти файл
locate nginx.conf

# Обновить базу поиска
sudo updatedb
```

`locate` использует базу данных, поэтому недавно созданные файлы могут отсутствовать в результатах.

## 5.4. Комбинирование поиска

```bash
# Найти ошибки в логах
grep -ri "error" /var/log/

# Найти большие логи
find /var/log -type f -size +50M

# Найти файлы конфигурации nginx
find /etc/nginx -type f

# Найти файлы, содержащие IP-адрес
grep -rn "192.168.1.10" /etc/
```

---

# 6. Права доступа и владельцы

## 6.1. Структура прав

Каждый файл имеет три категории доступа:

- User — владелец.
- Group — группа.
- Others — остальные пользователи.

Три базовых права:

| Право | Символ | Значение |
|---|---|---|
| Read | `r` | Чтение |
| Write | `w` | Запись |
| Execute | `x` | Выполнение |

Пример:

```text
-rwxr-xr--
```

Разбор:

```text
-    Тип объекта
rwx  Владелец
r-x  Группа
r--  Остальные
```

## 6.2. Числовые права

| Право | Значение |
|---|---:|
| `r` | 4 |
| `w` | 2 |
| `x` | 1 |

Примеры:

| Права | Значение |
|---|---|
| `777` | Все имеют полный доступ |
| `755` | Владелец полный, остальные чтение и выполнение |
| `750` | Владелец полный, группа чтение и выполнение |
| `700` | Только владелец |
| `644` | Владелец запись, остальные чтение |
| `640` | Владелец чтение/запись, группа чтение |
| `600` | Только владелец чтение/запись |

## 6.3. Chmod

```bash
# Установить права 755
chmod 755 script.sh

# Установить права 644
chmod 644 config.txt

# Разрешить выполнение владельцу
chmod u+x script.sh

# Запретить запись группе
chmod g-w file.txt

# Разрешить чтение всем
chmod a+r file.txt

# Рекурсивно изменить права
chmod -R 755 directory/
```

⚠️ Не используй `chmod -R 777` как универсальное решение проблем с доступом.

## 6.4. Chown

```bash
# Изменить владельца
sudo chown user file.txt

# Изменить владельца и группу
sudo chown user:group file.txt

# Только группа
sudo chown :group file.txt

# Рекурсивно
sudo chown -R user:group /opt/project/
```

## 6.5. Специальные права

### SUID

Программа выполняется с эффективными правами владельца файла.

```bash
chmod u+s program
```

### SGID

Для исполняемого файла позволяет запускать его с эффективной группой файла. Для каталога обеспечивает наследование группы новыми объектами.

```bash
chmod g+s directory/
```

### Sticky Bit

На каталоге позволяет пользователям удалять только собственные файлы (при соблюдении остальных условий доступа).

```bash
chmod +t /shared/
```

Пример:

```text
drwxrwxrwt
```

## 6.6. ACL

Дополнительные права доступа.

```bash
# Установить ACL
sudo setfacl -m u:alex:rwx /opt/project

# Разрешить группе чтение
sudo setfacl -m g:developers:r /opt/project

# Посмотреть ACL
getfacl /opt/project

# Удалить ACL пользователя
sudo setfacl -x u:alex /opt/project

# Удалить все ACL
sudo setfacl -b /opt/project
```

---

# 7. Пользователи и группы

## 7.1. Информация о пользователях

```bash
# Текущий пользователь
whoami

# Информация о пользователе
id

# Все группы
groups

# Все пользователи
cat /etc/passwd

# Все группы системы
cat /etc/group

# Последние входы
last

# Кто сейчас работает в системе
who

# Информация о последнем входе
lastlog
```

## 7.2. Создание пользователей

```bash
# Создать пользователя
sudo adduser alex

# Создать пользователя без интерактивного мастера
sudo useradd -m alex

# Создать пользователя с Bash
sudo useradd -m -s /bin/bash alex

# Изменить пароль
sudo passwd alex

# Заблокировать аккаунт
sudo passwd -l alex

# Разблокировать аккаунт
sudo passwd -u alex
```

## 7.3. Управление пользователями

```bash
# Изменить имя пользователя
sudo usermod -l newname oldname

# Добавить пользователя в группу
sudo usermod -aG sudo alex

# Изменить домашнюю директорию
sudo usermod -d /home/newhome -m alex

# Изменить оболочку
sudo usermod -s /bin/bash alex

# Удалить пользователя
sudo userdel alex

# Удалить пользователя вместе с домашним каталогом
sudo userdel -r alex
```

Важно: при добавлении пользователя в дополнительные группы используй `-aG`, а не просто `-G`, иначе можно заменить весь список дополнительных групп.

## 7.4. Управление группами

```bash
# Создать группу
sudo groupadd developers

# Добавить пользователя
sudo usermod -aG developers alex

# Посмотреть участников
getent group developers

# Удалить группу
sudo groupdel developers
```

## 7.5. Sudo

```bash
# Выполнить команду с повышенными правами
sudo apt update

# Открыть root shell
sudo -i

# Выполнить команду от другого пользователя
sudo -u www-data whoami

# Проверить доступные sudo-права
sudo -l

# Редактировать sudoers
sudo visudo
```

Для отдельного пользователя предпочтительнее создавать файл:

```bash
sudo visudo -f /etc/sudoers.d/alex
```

Пример содержимого:

```text
alex ALL=(ALL:ALL) ALL
```

---

# 8. Управление процессами

## 8.1. Просмотр процессов

```bash
# Все процессы
ps aux

# Дерево процессов
ps -ef --forest

# Найти процесс
ps aux | grep nginx

# Найти PID
pgrep nginx

# Информация о процессе
ps -p 1234 -f

# Процессы пользователя
ps -u www-data
```

## 8.2. Мониторинг

```bash
# Мониторинг процессов
top

# Более удобный мониторинг
htop

# Память
free -h

# Нагрузка
uptime

# CPU
lscpu

# Информация о памяти
cat /proc/meminfo
```

## 8.3. Управление процессами

```bash
# Завершить процесс
kill 1234

# Принудительно завершить
kill -9 1234

# Завершить процесс по имени
pkill nginx

# Завершить процессы по имени
killall nginx

# Отправить SIGTERM
kill -15 1234

# Отправить SIGKILL
kill -9 1234

# Посмотреть доступные сигналы
kill -l
```

Основные сигналы:

| Сигнал | Номер | Назначение |
|---|---:|---|
| SIGHUP | 1 | Hangup |
| SIGINT | 2 | Прерывание |
| SIGQUIT | 3 | Завершение с core dump |
| SIGKILL | 9 | Принудительное завершение |
| SIGTERM | 15 | Корректное завершение |
| SIGSTOP | 19 | Остановка процесса |
| SIGCONT | 18 | Продолжение процесса |

Предпочтительно сначала использовать SIGTERM. SIGKILL применяй, если процесс не реагирует на корректное завершение.

## 8.4. Фоновые процессы

```bash
# Запустить в фоне
./script.sh &

# Приостановить процесс
Ctrl + Z

# Продолжить в фоне
bg

# Вернуть на передний план
fg

# Список задач
jobs

# Запустить процесс с игнорированием SIGHUP
nohup ./script.sh > output.log 2>&1 &
```

Для постоянных серверных приложений предпочтительнее использовать systemd, а не `nohup`.

## 8.5. Приоритеты процессов

```bash
# Запустить с приоритетом
nice -n 10 ./script.sh

# Изменить приоритет
renice 5 -p 1234

# Посмотреть приоритет
ps -o pid,ni,pri,comm -p 1234
```

---

# 9. Systemd и управление службами

Systemd — система инициализации и управления службами в большинстве современных Linux-дистрибутивов.

## 9.1. Основные команды

```bash
# Статус службы
sudo systemctl status nginx

# Запустить
sudo systemctl start nginx

# Остановить
sudo systemctl stop nginx

# Перезапустить
sudo systemctl restart nginx

# Перечитать конфигурацию без перезапуска
sudo systemctl reload nginx

# Автозапуск
sudo systemctl enable nginx

# Отключить автозапуск
sudo systemctl disable nginx

# Запустить и добавить в автозагрузку
sudo systemctl enable --now nginx

# Список служб
systemctl list-units --type=service

# Список всех служб
systemctl list-unit-files --type=service

# Проверить состояние
systemctl is-active nginx

# Проверить автозапуск
systemctl is-enabled nginx
```

## 9.2. Создание собственной службы

Пример Python-приложения.

Создать файл:

```bash
sudo nano /etc/systemd/system/myapp.service
```

Содержимое:

```ini
[Unit]
Description=My Python Application
After=network.target

[Service]
Type=simple
User=myapp
Group=myapp

WorkingDirectory=/opt/myapp

ExecStart=/opt/myapp/venv/bin/python /opt/myapp/app.py

Restart=on-failure
RestartSec=5

Environment=PYTHONUNBUFFERED=1

[Install]
WantedBy=multi-user.target
```

Применение:

```bash
# Перечитать конфигурации systemd
sudo systemctl daemon-reload

# Запустить службу
sudo systemctl start myapp

# Включить автозапуск
sudo systemctl enable myapp

# Проверить статус
sudo systemctl status myapp

# Посмотреть логи
sudo journalctl -u myapp -f
```

## 9.3. Важные параметры systemd

| Параметр | Назначение |
|---|---|
| `Description` | Описание |
| `After` | Порядок запуска |
| `Requires` | Обязательная зависимость |
| `Wants` | Необязательная зависимость |
| `User` | Пользователь службы |
| `Group` | Группа |
| `WorkingDirectory` | Рабочий каталог |
| `ExecStart` | Команда запуска |
| `ExecStop` | Команда остановки |
| `ExecReload` | Перезагрузка конфигурации |
| `Restart` | Политика перезапуска |
| `RestartSec` | Задержка перезапуска |
| `Environment` | Переменные окружения |
| `EnvironmentFile` | Файл переменных |
| `WantedBy` | Цель установки |

## 9.4. Просмотр параметров службы

```bash
# Основные параметры
systemctl show nginx

# Команда запуска
systemctl show nginx -p ExecStart

# Пользователь
systemctl show nginx -p User

# Окружение
systemctl show nginx -p Environment

# Список зависимостей
systemctl list-dependencies nginx

# Проверка конфигурации unit
systemd-analyze verify /etc/systemd/system/myapp.service
```

## 9.5. Состояние загрузки

```bash
# Время загрузки
systemd-analyze

# Анализ времени запуска служб
systemd-analyze blame

# Критическая цепочка
systemd-analyze critical-chain
```

---

# 10. Логи и журналирование

## 10.1. Основные каталоги

```text
/var/log/
/var/log/syslog
/var/log/auth.log
/var/log/kern.log
/var/log/dpkg.log
/var/log/apt/
/var/log/nginx/
/var/log/journal/
```

Названия файлов зависят от дистрибутива и конфигурации.

## 10.2. Journalctl

```bash
# Все журналы
journalctl

# Последние события
journalctl -n 50

# Следить за логами
journalctl -f

# Логи службы
journalctl -u nginx

# Последние 100 записей службы
journalctl -u nginx -n 100

# Логи в реальном времени
journalctl -u nginx -f

# Логи за сегодня
journalctl --since today

# Логи за последний час
journalctl --since "1 hour ago"

# Логи за определённый период
journalctl --since "2026-11-10 10:00" --until "2026-11-10 12:00"

# Ошибки и более серьёзные сообщения
journalctl -p err

# Логи текущей загрузки
journalctl -b

# Логи предыдущей загрузки
journalctl -b -1

# Логи ядра
journalctl -k
```

## 10.3. Dmesg

```bash
# Сообщения ядра
dmesg

# Последние сообщения
dmesg | tail -n 50

# Ошибки
dmesg --level=err,warn

# Время в читаемом формате
dmesg -T

# Следить за сообщениями
dmesg -w
```

## 10.4. Logrotate

Конфигурация:

```bash
/etc/logrotate.conf
/etc/logrotate.d/
```

Пример:

```text
/var/log/myapp/*.log {
    daily
    rotate 7
    compress
    delaycompress
    missingok
    notifempty
    copytruncate
}
```

Проверка:

```bash
# Проверить конфигурацию
sudo logrotate -d /etc/logrotate.conf

# Принудительный запуск
sudo logrotate -f /etc/logrotate.conf
```

---

# 11. Управление пакетами

## 11.1. APT

```bash
# Обновить список пакетов
sudo apt update

# Обновить пакеты
sudo apt upgrade

# Установить пакет
sudo apt install nginx

# Удалить пакет
sudo apt remove nginx

# Удалить пакет и конфигурации
sudo apt purge nginx

# Удалить ненужные зависимости
sudo apt autoremove

# Найти пакет
apt search nginx

# Информация о пакете
apt show nginx

# Список установленных пакетов
apt list --installed

# Проверить установленный пакет
dpkg -l nginx

# Показать файлы пакета
dpkg -L nginx

# Узнать, какому пакету принадлежит файл
dpkg -S /usr/sbin/nginx
```

## 11.2. Работа с DEB

```bash
# Установить DEB
sudo dpkg -i package.deb

# Исправить зависимости
sudo apt --fix-broken install

# Удалить пакет
sudo dpkg -r package

# Информация о пакете
dpkg -I package.deb
```

## 11.3. Репозитории

Основные конфигурации:

```text
/etc/apt/sources.list
/etc/apt/sources.list.d/
```

После изменения репозиториев:

```bash
sudo apt update
```

Не добавляй неизвестные репозитории и не отключай проверку подписей пакетов без веской причины.

---

# 12. Сеть и диагностика

## 12.1. Сетевые интерфейсы

```bash
# IP-адреса
ip addr

# Краткий список интерфейсов
ip -br addr

# Сетевые интерфейсы
ip link

# Маршруты
ip route

# Таблица маршрутизации
ip route show

# Соседние устройства
ip neigh

# Имя хоста
hostname -I
```

## 12.2. Настройка IP

Пример временного назначения адреса:

```bash
sudo ip addr add 192.168.1.100/24 dev eth0
```

Удаление:

```bash
sudo ip addr del 192.168.1.100/24 dev eth0
```

Включение интерфейса:

```bash
sudo ip link set eth0 up
```

Отключение:

```bash
sudo ip link set eth0 down
```

Эти изменения не являются постоянными.

## 12.3. Проверка доступности

```bash
# Проверить сервер
ping 8.8.8.8

# Проверить DNS
ping google.com

# Ограничить количество пакетов
ping -c 4 8.8.8.8

# Проверить маршрут
traceroute google.com

# Альтернатива
tracepath google.com
```

## 12.4. Проверка портов

```bash
# Просмотр открытых TCP/UDP портов
sudo ss -tulpn

# Только TCP
sudo ss -tlnp

# Только UDP
sudo ss -ulnp

# Установленные соединения
ss -tun

# Проверить конкретный порт
sudo ss -tulpn | grep :80

# Проверить порт локально
nc -zv 127.0.0.1 80

# Проверить удалённый порт
nc -zv example.com 443
```

Основные параметры `ss`:

| Параметр | Назначение |
|---|---|
| `-t` | TCP |
| `-u` | UDP |
| `-l` | Listening |
| `-n` | Не преобразовывать адреса и порты в имена |
| `-p` | Показать процесс |
| `-a` | Все сокеты |

## 12.5. DNS

```bash
# DNS-запрос
dig google.com

# Только IP
dig +short google.com

# A-запись
dig A example.com

# MX-записи
dig MX example.com

# NS-записи
dig NS example.com

# Проверить DNS-сервер
dig @8.8.8.8 example.com

# Альтернатива
nslookup example.com

# Проверить локальную конфигурацию
cat /etc/resolv.conf

# Проверить настройки systemd-resolved
resolvectl status
```

## 12.6. Curl и HTTP

```bash
# GET-запрос
curl https://example.com

# Только заголовки
curl -I https://example.com

# Подробная диагностика
curl -v https://example.com

# Проверить HTTP-код
curl -o /dev/null -s -w "%{http_code}\n" https://example.com

# POST-запрос
curl -X POST https://example.com/api

# Отправить JSON
curl -X POST https://example.com/api \
-H "Content-Type: application/json" \
-d '{"name":"Alex"}'

# Проверить TLS
curl -Iv https://example.com
```

## 12.7. Tcpdump

```bash
# Посмотреть сетевые пакеты
sudo tcpdump

# Определённый интерфейс
sudo tcpdump -i eth0

# TCP-пакеты
sudo tcpdump tcp

# Порт 80
sudo tcpdump port 80

# Порт 443
sudo tcpdump port 443

# Трафик определённого IP
sudo tcpdump host 192.168.1.10

# Сохранить в PCAP
sudo tcpdump -i eth0 -w traffic.pcap

# Читать PCAP
sudo tcpdump -r traffic.pcap
```

## 12.8. Сетевая конфигурация Ubuntu

Netplan:

```bash
ls -l /etc/netplan/
```

Пример статического IP:

```yaml
network:
  version: 2
  ethernets:
    ens18:
      dhcp4: false
      addresses:
        - 192.168.1.100/24
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses:
          - 1.1.1.1
          - 8.8.8.8
```

Применение:

```bash
sudo netplan generate
sudo netplan try
sudo netplan apply
```

На удалённом сервере при изменении сети используй `netplan try` и имей резервный способ доступа.

---

# 13. SSH и удалённое администрирование

## 13.1. Подключение

```bash
# Подключение
ssh user@192.168.1.100

# Указать порт
ssh -p 2222 user@server

# Указать приватный ключ
ssh -i ~/.ssh/id_ed25519 user@server

# Подробная диагностика
ssh -v user@server

# Расширенная диагностика
ssh -vvv user@server
```

## 13.2. Генерация ключей

```bash
# Создать ED25519 ключ
ssh-keygen -t ed25519

# Посмотреть публичный ключ
cat ~/.ssh/id_ed25519.pub

# Копировать ключ на сервер
ssh-copy-id user@server
```

Публичный ключ можно размещать на сервере. Приватный ключ никому не передавай.

## 13.3. SSH Config

Файл:

```bash
nano ~/.ssh/config
```

Пример:

```sshconfig
Host myserver
    HostName 192.168.1.100
    User admin
    Port 22
    IdentityFile ~/.ssh/id_ed25519
```

Теперь подключение:

```bash
ssh myserver
```

## 13.4. SSH Server

Конфигурация:

```bash
sudo nano /etc/ssh/sshd_config
```

Пример настроек:

```text
PermitRootLogin no
PubkeyAuthentication yes
PasswordAuthentication no
```

Важно: отключай парольную авторизацию только после проверки, что вход по ключу работает и есть резервный доступ.

Проверка:

```bash
# Проверить конфигурацию
sudo sshd -t

# Перечитать конфигурацию
sudo systemctl reload ssh
```

## 13.5. Передача файлов

```bash
# Копирование файла на сервер
scp file.txt user@server:/home/user/

# Скачать файл
scp user@server:/home/user/file.txt .

# Копирование каталога
scp -r project/ user@server:/opt/

# Синхронизация
rsync -avz project/ user@server:/opt/project/
```

## 13.6. Права SSH

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519
chmod 644 ~/.ssh/id_ed25519.pub
chmod 600 ~/.ssh/authorized_keys
```

---

# 14. Диски и файловые системы

## 14.1. Информация о дисках

```bash
# Список дисков
lsblk

# Подробная информация
lsblk -f

# Информация о разделах
sudo fdisk -l

# UUID и типы файловых систем
sudo blkid

# Использование дисков
df -h

# Использование inode
df -i

# Размер каталогов
du -sh /var/log

# Размер всех каталогов
du -h --max-depth=1 /var
```

## 14.2. Создание разделов

⚠️ Следующие операции могут уничтожить данные на выбранном диске. Тщательно проверяй устройство.

Пример:

```bash
# Найти диск
lsblk

# Открыть fdisk
sudo fdisk /dev/sdb
```

Основные команды внутри fdisk:

| Команда | Назначение |
|---|---|
| `m` | Справка |
| `p` | Показать разделы |
| `n` | Новый раздел |
| `d` | Удалить раздел |
| `w` | Сохранить изменения |
| `q` | Выйти без сохранения |

## 14.3. Создание файловой системы

```bash
# Создать ext4
sudo mkfs.ext4 /dev/sdb1

# Создать XFS
sudo mkfs.xfs /dev/sdb1

# Посмотреть файловые системы
lsblk -f
```

## 14.4. Монтирование

```bash
# Создать каталог
sudo mkdir -p /mnt/data

# Подключить раздел
sudo mount /dev/sdb1 /mnt/data

# Посмотреть подключённые диски
findmnt

# Отключить
sudo umount /mnt/data
```

## 14.5. Автоматическое монтирование

Файл:

```bash
sudo nano /etc/fstab
```

Узнать UUID:

```bash
sudo blkid /dev/sdb1
```

Пример строки:

```text
UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx /mnt/data ext4 defaults,nofail 0 2
```

Проверка:

```bash
sudo findmnt --verify
sudo mount -a
```

Перед перезагрузкой обязательно проверь корректность `/etc/fstab`.

## 14.6. Проверка дисков

```bash
# SMART-информация
sudo smartctl -a /dev/sda

# Проверка SMART
sudo smartctl -H /dev/sda

# Проверка температуры NVMe
sudo nvme smart-log /dev/nvme0
```

Для использования `smartctl` и `nvme` могут потребоваться пакеты `smartmontools` и `nvme-cli`.

---

# 15. LVM и RAID

## 15.1. LVM

LVM позволяет гибко управлять дисковым пространством.

Основные компоненты:

| Компонент | Значение |
|---|---|
| PV | Physical Volume |
| VG | Volume Group |
| LV | Logical Volume |

Схема:

```text
Physical Disk
     |
     v
Physical Volume
     |
     v
Volume Group
     |
     v
Logical Volume
     |
     v
Filesystem
     |
     v
Mount Point
```

## 15.2. Основные команды LVM

```bash
# Создать Physical Volume
sudo pvcreate /dev/sdb

# Создать Volume Group
sudo vgcreate vg_data /dev/sdb

# Создать Logical Volume
sudo lvcreate -L 10G -n lv_data vg_data

# Показать PV
sudo pvs

# Показать VG
sudo vgs

# Показать LV
sudo lvs

# Создать файловую систему
sudo mkfs.ext4 /dev/vg_data/lv_data

# Увеличить LV
sudo lvextend -L +5G /dev/vg_data/lv_data

# Увеличить LV и ext4
sudo lvextend -r -L +5G /dev/vg_data/lv_data
```

## 15.3. RAID

Основные уровни:

| RAID | Особенности |
|---|---|
| RAID 0 | Скорость, без отказоустойчивости |
| RAID 1 | Зеркалирование |
| RAID 5 | Распределённая чётность |
| RAID 6 | Двойная чётность |
| RAID 10 | Зеркалирование + чередование |

Пример просмотра:

```bash
cat /proc/mdstat
```

⚠️ RAID не заменяет резервное копирование.

---

# 16. Bash и автоматизация

## 16.1. Создание скрипта

```bash
nano script.sh
```

Пример:

```bash
#!/bin/bash

echo "Hello Linux"
```

Сделать исполняемым:

```bash
chmod +x script.sh
```

Запустить:

```bash
./script.sh
```

## 16.2. Переменные

```bash
NAME="Linux"
VERSION=24

echo "$NAME"
echo "$VERSION"
```

Правильно:

```bash
NAME="Ubuntu"
echo "$NAME"
```

Неправильно:

```bash
NAME = "Ubuntu"
```

Пробелы вокруг `=` при присваивании недопустимы.

## 16.3. Ввод данных

```bash
#!/bin/bash

read -p "Enter your name: " NAME

echo "Hello, $NAME"
```

## 16.4. Условия

```bash
#!/bin/bash

if [ -f /etc/passwd ]; then
    echo "File exists"
else
    echo "File not found"
fi
```

Основные проверки:

| Оператор | Значение |
|---|---|
| `-f` | Обычный файл |
| `-d` | Каталог |
| `-e` | Объект существует |
| `-r` | Доступен для чтения |
| `-w` | Доступен для записи |
| `-x` | Доступен для выполнения |
| `-z` | Строка пустая |
| `-n` | Строка не пустая |
| `-eq` | Равно |
| `-ne` | Не равно |
| `-gt` | Больше |
| `-lt` | Меньше |

## 16.5. Циклы

### For

```bash
for i in 1 2 3 4 5
do
    echo "$i"
done
```

### While

```bash
COUNTER=1

while [ "$COUNTER" -le 5 ]
do
    echo "$COUNTER"
    ((COUNTER++))
done
```

## 16.6. Функции

```bash
#!/bin/bash

greet() {
    echo "Hello, $1"
}

greet "Linux"
```

## 16.7. Аргументы скрипта

```bash
#!/bin/bash

echo "Script: $0"
echo "First argument: $1"
echo "Second argument: $2"
echo "All arguments: $@"
echo "Arguments count: $#"
```

## 16.8. Exit Code

```bash
# Код завершения предыдущей команды
echo $?
```

Основные значения:

| Код | Значение |
|---|---|
| `0` | Успешно |
| `1` | Общая ошибка |
| `2` | Ошибка использования команды |
| `126` | Команда найдена, но не исполняется |
| `127` | Команда не найдена |
| `130` | Прерывание через Ctrl+C |
| `137` | Завершение через SIGKILL |
| `143` | Завершение через SIGTERM |

## 16.9. Безопасный шаблон Bash

```bash
#!/usr/bin/env bash

set -Eeuo pipefail

LOG_FILE="/var/log/my_script.log"

log() {
    echo "[$(date '+%F %T')] $*" | tee -a "$LOG_FILE"
}

if [[ -f /etc/passwd ]]; then
    log "System file exists"
else
    log "System file not found"
    exit 1
fi
```

## 16.10. Pipe

Передача результата одной команды другой.

```bash
ps aux | grep nginx

cat application.log | grep error

ls -lah | sort

df -h | grep /dev
```

Принцип:

```text
COMMAND 1 | COMMAND 2 | COMMAND 3
```

## 16.11. AWK

Обработка текстовых данных.

```bash
# Вывести первый столбец
awk '{print $1}' file.txt

# Вывести первый и третий столбцы
awk '{print $1, $3}' file.txt

# Вывести строки, где значение больше 100
awk '$2 > 100' file.txt

# Разделитель :
awk -F: '{print $1}' /etc/passwd
```

## 16.12. Sed

```bash
# Заменить первое совпадение в строке
sed 's/old/new/' file.txt

# Заменить все совпадения
sed 's/old/new/g' file.txt

# Удалить третью строку
sed '3d' file.txt

# Вывести определённую строку
sed -n '5p' file.txt
```

---

# 17. Cron и планировщик задач

## 17.1. Cron

```bash
# Открыть расписание текущего пользователя
crontab -e

# Посмотреть расписание
crontab -l

# Удалить расписание
crontab -r

# Расписание другого пользователя
sudo crontab -u root -l
```

## 17.2. Формат Cron

```text
* * * * * command
| | | | |
| | | | +--- День недели
| | | +----- Месяц
| | +------- День месяца
| +--------- Час
+----------- Минута
```

Примеры:

```cron
# Каждую минуту
* * * * * command

# Каждые 5 минут
*/5 * * * * command

# Каждый час
0 * * * * command

# Каждый день в 03:00
0 3 * * * command

# Каждый понедельник в 08:00
0 8 * * 1 command

# Каждое воскресенье в полночь
0 0 * * 0 command
```

## 17.3. Пример резервного копирования

```cron
0 2 * * * /usr/local/bin/backup.sh >> /var/log/backup.log 2>&1
```

Cron использует ограниченное окружение. Лучше указывать абсолютные пути к исполняемым файлам.

## 17.4. Systemd Timers

Альтернатива Cron.

```bash
systemctl list-timers
```

Таймеры позволяют использовать возможности systemd, включая зависимости, журналирование и контроль состояния задач.

---

# 18. Переменные окружения

## 18.1. Просмотр переменных

```bash
# Все переменные
env

# Все переменные Bash
printenv

# Конкретная переменная
echo "$PATH"

# Текущий пользователь
echo "$USER"

# Домашний каталог
echo "$HOME"
```

## 18.2. Создание переменных

```bash
# Локальная переменная
NAME="Linux"

# Экспортировать
export NAME="Linux"

# Удалить переменную
unset NAME
```

## 18.3. PATH

PATH определяет каталоги, в которых система ищет исполняемые файлы.

```bash
echo "$PATH"
```

Добавление каталога:

```bash
export PATH="$PATH:/opt/myapp/bin"
```

## 18.4. Файлы окружения

```text
/etc/environment
/etc/profile
/etc/profile.d/
/etc/bash.bashrc
~/.bashrc
~/.profile
```

---

# 19. Архивирование и резервное копирование

## 19.1. Tar

```bash
# Создать архив
tar -cvf backup.tar /opt/project

# Создать gzip-архив
tar -czvf backup.tar.gz /opt/project

# Создать bzip2-архив
tar -cjvf backup.tar.bz2 /opt/project

# Распаковать
tar -xvf backup.tar

# Распаковать gzip
tar -xzvf backup.tar.gz

# Посмотреть содержимое
tar -tzvf backup.tar.gz
```

Основные параметры:

| Параметр | Значение |
|---|---|
| `c` | Создать архив |
| `x` | Распаковать |
| `v` | Подробный вывод |
| `f` | Имя архива |
| `z` | Gzip |
| `j` | Bzip2 |
| `J` | XZ |

## 19.2. Rsync

```bash
# Синхронизация каталога
rsync -av /source/ /destination/

# Синхронизация на сервер
rsync -avz /opt/project/ user@server:/backup/project/

# Удалять файлы, которых нет в источнике
rsync -av --delete /source/ /destination/

# Сухой запуск
rsync -avn /source/ /destination/
```

⚠️ `--delete` может удалить данные в каталоге назначения. Сначала проверяй результат с `-n`.

## 19.3. Проверка контрольных сумм

```bash
sha256sum backup.tar.gz
sha256sum -c checksums.txt
```

## 19.4. Правила резервного копирования

Рекомендуется придерживаться схемы 3-2-1:

- 3 копии данных.
- 2 разных типа носителей.
- 1 копия вне основного помещения или инфраструктуры.

Обязательно проверяй возможность восстановления из резервной копии.

---

# 20. Firewall и безопасность

## 20.1. UFW

```bash
# Статус
sudo ufw status

# Подробный статус
sudo ufw status verbose

# Разрешить SSH
sudo ufw allow OpenSSH

# Разрешить порт 80
sudo ufw allow 80/tcp

# Разрешить HTTPS
sudo ufw allow 443/tcp

# Разрешить конкретный порт
sudo ufw allow 8000/tcp

# Запретить порт
sudo ufw deny 8080/tcp

# Удалить правило
sudo ufw delete allow 8000/tcp

# Включить
sudo ufw enable

# Отключить
sudo ufw disable

# Сбросить правила
sudo ufw reset
```

⚠️ Перед включением UFW на удалённом сервере обязательно разреши SSH.

## 20.2. Fail2ban

```bash
# Установка
sudo apt install fail2ban

# Статус
sudo systemctl status fail2ban

# Список jail
sudo fail2ban-client status

# Статус SSH jail
sudo fail2ban-client status sshd
```

Конфигурацию рекомендуется размещать в:

```text
/etc/fail2ban/jail.local
```

## 20.3. Проверка открытых портов

```bash
sudo ss -tulpn
```

## 20.4. Проверка обновлений безопасности

```bash
sudo apt update
apt list --upgradable
```

## 20.5. Проверка прав SSH

```bash
sudo sshd -t
sudo sshd -T
```

## 20.6. Минимальные рекомендации

- Не работать постоянно под root.
- Использовать SSH-ключи.
- Ограничивать сетевые порты.
- Своевременно устанавливать обновления.
- Использовать принцип минимальных привилегий.
- Не хранить пароли в открытом виде.
- Не давать приложениям лишние права.
- Настроить резервное копирование.
- Проверять логи авторизации.
- Контролировать доступ к конфигурациям и секретам.

---

# 21. Nginx и веб-сервер

## 21.1. Установка

```bash
sudo apt update
sudo apt install nginx
```

## 21.2. Управление

```bash
sudo systemctl status nginx

sudo systemctl start nginx

sudo systemctl stop nginx

sudo systemctl restart nginx

sudo systemctl reload nginx

sudo systemctl enable nginx
```

## 21.3. Основные каталоги

```text
/etc/nginx/
/etc/nginx/nginx.conf
/etc/nginx/sites-available/
/etc/nginx/sites-enabled/
/var/log/nginx/access.log
/var/log/nginx/error.log
/var/www/html/
```

## 21.4. Проверка конфигурации

```bash
sudo nginx -t
```

## 21.5. Пример Reverse Proxy

```nginx
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://127.0.0.1:8000;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## 21.6. Активировать сайт

```bash
sudo ln -s /etc/nginx/sites-available/myapp \
/etc/nginx/sites-enabled/myapp

sudo nginx -t

sudo systemctl reload nginx
```

## 21.7. Просмотр логов

```bash
sudo tail -f /var/log/nginx/access.log

sudo tail -f /var/log/nginx/error.log
```

## 21.8. Проверка портов

```bash
sudo ss -tulpn | grep nginx
```

---

# 22. Мониторинг системы

## 22.1. CPU

```bash
lscpu

top

htop

mpstat -P ALL 1
```

`mpstat` входит в пакет `sysstat`.

## 22.2. RAM

```bash
free -h

cat /proc/meminfo

vmstat 1
```

## 22.3. Диски

```bash
df -h

df -i

du -sh /var/log

lsblk
```

## 22.4. Системная нагрузка

```bash
uptime

top

vmstat 1
```

Load Average — средняя нагрузка системы за 1, 5 и 15 минут.

Важно: Load Average — не прямой процент загрузки CPU. В него входят выполняемые и находящиеся в непрерываемом ожидании задачи.

## 22.5. Мониторинг дискового I/O

```bash
iostat -xz 1
```

## 22.6. Мониторинг сети

```bash
ip -s link

ss -s

iftop

nload

tcpdump
```

## 22.7. Prometheus Node Exporter

Node Exporter собирает системные метрики для Prometheus.

Проверка:

```bash
systemctl status prometheus-node-exporter
```

Проверка метрик:

```bash
curl http://localhost:9100/metrics
```

Полезные метрики:

```text
node_cpu_seconds_total
node_memory_MemAvailable_bytes
node_filesystem_avail_bytes
node_load1
node_load5
node_load15
node_network_receive_bytes_total
node_network_transmit_bytes_total
node_boot_time_seconds
```

---

# 23. Диагностика неисправностей

Одна из важнейших компетенций системного администратора — не просто запускать команды, а последовательно находить причину проблемы.

## 23.1. Сервер не отвечает

Проверить:

```bash
ping SERVER_IP

ip addr

ip route

ip neigh

traceroute SERVER_IP
```

## 23.2. Сайт не открывается

Проверить:

```bash
# DNS
dig example.com

# HTTP
curl -I http://example.com

# HTTPS
curl -Iv https://example.com

# Открытые порты
sudo ss -tulpn

# Firewall
sudo ufw status

# Nginx
sudo systemctl status nginx

# Логи Nginx
sudo journalctl -u nginx -n 100
```

## 23.3. Служба не запускается

```bash
sudo systemctl status myapp

sudo journalctl -u myapp -n 100

sudo journalctl -u myapp -xe

systemctl cat myapp

systemd-analyze verify /etc/systemd/system/myapp.service
```

## 23.4. Заканчивается место на диске

```bash
df -h

df -i

sudo du -xhd1 /var

sudo du -xhd1 /

sudo find /var -type f -size +100M
```

## 23.5. Заканчивается оперативная память

```bash
free -h

top

ps aux --sort=-%mem | head

cat /proc/meminfo

journalctl -k | grep -i -E 'oom|out of memory'
```

## 23.6. Высокая загрузка CPU

```bash
top

htop

ps aux --sort=-%cpu | head

uptime

mpstat 1
```

## 23.7. Не работает SSH

```bash
sudo systemctl status ssh

sudo sshd -t

sudo ss -tulpn | grep :22

sudo journalctl -u ssh -n 100

sudo ufw status
```

## 23.8. Процесс занимает порт

```bash
sudo ss -tulpn

sudo lsof -i :8000

sudo fuser -v 8000/tcp
```

## 23.9. Не работает DNS

```bash
cat /etc/resolv.conf

resolvectl status

dig example.com

dig @1.1.1.1 example.com

getent hosts example.com
```

---

# 24. Загрузка Linux и архитектура

## 24.1. Этапы загрузки

```text
BIOS / UEFI
     |
     v
Bootloader (GRUB)
     |
     v
Linux Kernel
     |
     v
Initramfs
     |
     v
Root Filesystem
     |
     v
Systemd (PID 1)
     |
     v
System Services
     |
     v
Login
```

## 24.2. GRUB

Основная конфигурация:

```text
/etc/default/grub
/boot/grub/grub.cfg
```

После изменения исходной конфигурации:

```bash
sudo update-grub
```

Не редактируй сгенерированный `grub.cfg` вручную без необходимости.

## 24.3. Kernel

```bash
# Версия ядра
uname -r

# Информация о ядре
uname -a

# Загруженные модули
lsmod

# Информация о модуле
modinfo ext4

# Загрузка модуля
sudo modprobe module_name

# Удаление модуля
sudo modprobe -r module_name
```

## 24.4. Виртуальные файловые системы

| Каталог | Назначение |
|---|---|
| `/proc` | Информация о процессах и ядре |
| `/sys` | Устройства и параметры ядра |
| `/dev` | Файлы устройств |

Примеры:

```bash
cat /proc/cpuinfo

cat /proc/meminfo

cat /proc/uptime

ls /sys/class/net/

ls /dev/
```

## 24.5. Cgroups и Namespaces

Это важные механизмы изоляции и ограничения ресурсов.

Cgroups позволяют ограничивать и учитывать:

- CPU.
- RAM.
- I/O.
- Количество процессов.

Namespaces обеспечивают изоляцию:

- PID.
- Network.
- Mount.
- User.
- IPC.
- UTS.
- Cgroup.

Они лежат в основе контейнеризации Linux.

---

# 25. Docker и контейнеризация

## 25.1. Установка и проверка

```bash
docker --version

docker info

docker ps

docker images
```

## 25.2. Основные команды

```bash
# Скачать образ
docker pull nginx

# Запустить контейнер
docker run -d --name web -p 8080:80 nginx

# Все контейнеры
docker ps -a

# Остановить
docker stop web

# Запустить
docker start web

# Перезапустить
docker restart web

# Удалить контейнер
docker rm web

# Удалить образ
docker rmi nginx
```

## 25.3. Логи и диагностика

```bash
# Логи контейнера
docker logs web

# Логи в реальном времени
docker logs -f web

# Войти внутрь
docker exec -it web bash

# Если Bash отсутствует
docker exec -it web sh

# Информация о контейнере
docker inspect web

# Использование ресурсов
docker stats
```

## 25.4. Docker Compose

```bash
docker compose up -d

docker compose down

docker compose ps

docker compose logs -f

docker compose restart

docker compose pull
```

## 25.5. Dockerfile

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]
```

Сборка:

```bash
docker build -t myapp:latest .
```

Запуск:

```bash
docker run -d --name myapp myapp:latest
```

---

# 26. Git для Linux-администратора

## 26.1. Основные команды

```bash
# Проверить версию
git --version

# Инициализировать репозиторий
git init

# Клонировать репозиторий
git clone https://github.com/user/project.git

# Статус
git status

# Добавить файл
git add README.md

# Добавить всё
git add .

# Создать коммит
git commit -m "Initial commit"

# Посмотреть историю
git log

# Список веток
git branch

# Создать ветку
git branch develop

# Переключиться
git switch develop

# Отправить изменения
git push origin main

# Получить изменения
git pull
```

## 26.2. SSH для GitHub

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"

cat ~/.ssh/id_ed25519.pub
```

Добавить публичный ключ в настройки GitHub.

Проверить:

```bash
ssh -T git@github.com
```

---

# 27. Полезные конфигурационные файлы

| Файл | Назначение |
|---|---|
| `/etc/passwd` | Пользователи |
| `/etc/shadow` | Хеши паролей и параметры паролей |
| `/etc/group` | Группы |
| `/etc/sudoers` | Настройки sudo |
| `/etc/hostname` | Имя системы |
| `/etc/hosts` | Локальное разрешение имён |
| `/etc/fstab` | Автоматическое монтирование |
| `/etc/ssh/sshd_config` | SSH-сервер |
| `/etc/ssh/ssh_config` | SSH-клиент |
| `/etc/resolv.conf` | DNS-конфигурация |
| `/etc/environment` | Переменные окружения |
| `/etc/profile` | Настройки shell |
| `/etc/crontab` | Системный Cron |
| `/etc/logrotate.conf` | Ротация логов |
| `/etc/sysctl.conf` | Параметры ядра |
| `/etc/hosts.allow` | Настройки TCP Wrappers, если поддерживаются |
| `/etc/netplan/` | Сетевая конфигурация Ubuntu |
| `/etc/systemd/system/` | Пользовательские unit-файлы systemd |
| `/etc/nginx/` | Конфигурации Nginx |

---

# 28. Полезные сочетания команд

## 28.1. Найти самые большие каталоги

```bash
sudo du -xhd1 /var | sort -h
```

## 28.2. Найти самые большие файлы

```bash
sudo find / -xdev -type f -printf '%s %p\n' 2>/dev/null \
| sort -nr | head -20
```

## 28.3. Найти процессы по CPU

```bash
ps aux --sort=-%cpu | head -10
```

## 28.4. Найти процессы по RAM

```bash
ps aux --sort=-%mem | head -10
```

## 28.5. Проверить все listening-порты

```bash
sudo ss -tulpn
```

## 28.6. Найти ошибки в логах

```bash
sudo journalctl -p err -b
```

## 28.7. Проверить свободное место

```bash
df -h && df -i
```

## 28.8. Проверить состояние основных служб

```bash
systemctl --failed
```

## 28.9. Проверить сетевые подключения

```bash
ss -s
```

## 28.10. Проверить использование памяти

```bash
free -h
```

## 28.11. Проверить состояние дисков и разделов

```bash
lsblk -f
```

## 28.12. Проверить время работы

```bash
uptime
```

## 28.13. Найти файлы, изменённые за последние сутки

```bash
find /var/log -type f -mtime -1
```

## 28.14. Проверить ошибки загрузки

```bash
journalctl -b -p err
```

## 28.15. Найти процессы, использующие конкретный файл

```bash
sudo lsof /var/log/syslog
```

---

# 29. Типовые аварийные ситуации

Практические сценарии, которые должен уметь решать Linux Administrator.

| Проблема | Что проверять |
|---|---|
| Сервер недоступен | Сеть, IP, маршруты, firewall |
| Не работает SSH | sshd, порт 22, firewall, ключи |
| Сайт не открывается | DNS, Nginx, TLS, порты |
| Служба не запускается | systemctl, journalctl |
| Заканчивается диск | df, du, find |
| Заканчивается RAM | free, top, OOM Killer |
| Высокая загрузка CPU | top, htop, ps |
| Порт занят | ss, lsof, fuser |
| Не работает DNS | dig, resolvectl |
| Не монтируется диск | lsblk, blkid, fstab, mount |
| Нет доступа к файлу | id, ls -l, chmod, chown, getfacl |
| Cron не выполняется | crontab, системные логи, окружение |
| Docker не запускается | docker logs, inspect, systemctl |
| Ошибка обновления APT | apt, dpkg, репозитории |
| Служба постоянно перезапускается | systemd, journalctl, exit code |
| Сервер не загружается | GRUB, initramfs, kernel, filesystem |

## Алгоритм диагностики

При возникновении проблемы:

1. Воспроизвести проблему.
2. Проверить состояние сервиса.
3. Проверить логи.
4. Проверить конфигурацию.
5. Проверить права доступа.
6. Проверить ресурсы системы.
7. Проверить сеть, если проблема связана с подключением.
8. Определить первопричину.
9. Исправить проблему.
10. Проверить результат.
11. Зафиксировать причину и решение.

Не ограничивайся перезапуском службы. Перезапуск может временно скрыть проблему, но не устранить её.

---

# 30. Чек-лист Linux Administrator

Используй этот список для самопроверки.


---

# 🎯 Итог

Цель изучения Linux — не запомнить сотни команд.

Главное — научиться самостоятельно:

- Администрировать серверы.
- Обеспечивать безопасность.
- Управлять сервисами.
- Диагностировать неисправности.
- Работать с сетями.
- Управлять дисками.
- Автоматизировать рутинные задачи.
- Разворачивать приложения.
- Контролировать состояние инфраструктуры.

**Linux — фундамент системного администрирования и DevOps.**

---

## 📖 Полезная документация

- [Ubuntu Server Documentation](https://documentation.ubuntu.com/server/)
- [Debian Administrator's Handbook](https://debian-handbook.info/)
- [Linux man-pages](https://man7.org/linux/man-pages/)
- [GNU Bash Manual](https://www.gnu.org/software/bash/manual/)
- [Systemd Documentation](https://www.freedesktop.org/software/systemd/man/latest/)
- [Arch Linux Wiki](https://wiki.archlinux.org/)
- [Docker Documentation](https://docs.docker.com/)
- [Nginx Documentation](https://nginx.org/en/docs/)
- [Red Hat Enterprise Linux Documentation](https://docs.redhat.com/)

---

**Linux Mastery | System Administration & DevOps Handbook**

*Keep learning. Keep building. Keep automating.*
