# Odoo Helper Windows

Набір скриптів для автоматизації розгортання та керування Odoo на Windows.

## Можливості

- Автоматичне встановлення Odoo та всіх залежностей
- Керування віртуальним середовищем
- Керування базами даних
- Оновлення та встановлення модулів
- Створення резервних копій
- Запуск тестів

## Встановлення

1. Запустіть PowerShell від імені адміністратора
2. Перейдіть до директорії зі скриптом
3. Виконайте команду:

```powershell
.\install.ps1 -OdooVersion "15.0" -InstallPath "C:\odoo15"
```

Додаткові параметри:
- `-PostgresVersion` - версія PostgreSQL (за замовчуванням "13")
- `-PostgresPort` - порт PostgreSQL (за замовчуванням "5432")
- `-OdooPort` - порт Odoo (за замовчуванням "8069")
- `-PostgresUser` - користувач PostgreSQL (за замовчуванням "odoo")
- `-PostgresPassword` - пароль PostgreSQL (за замовчуванням "odoo")
- `-PostgresHost` - хост PostgreSQL (за замовчуванням "localhost")

## Використання

Після встановлення ви можете використовувати наступні команди:

### Керування модулями

```powershell
# Оновлення модуля
odoo-helper addons update base

# Встановлення модуля
odoo-helper addons install sale

# Список модулів
odoo-helper addons list
```

### Керування базами даних

```powershell
# Створення резервної копії
odoo-helper db backup mydb

# Відновлення з резервної копії
odoo-helper db restore newdb path/to/backup.zip

# Список баз даних
odoo-helper db list
```

### Керування сервером

```powershell
# Запуск сервера
odoo-helper server start

# Запуск тестів
odoo-helper server test sale
```

### Керування віртуальним середовищем

```powershell
# Активація віртуального середовища
odoo-helper venv enter

# Встановлення pip пакетів
odoo-helper venv pip install requests
```

## Структура проекту

Після встановлення буде створено наступну структуру:

```
C:\odoo15\              # Коренева директорія (залежить від InstallPath)
├── tools\              # Директорія з інструментами
│   └── odoo-helper.psm1  # PowerShell модуль з командами
├── conf\               # Конфігураційні файли
│   ├── odoo.conf        # Основна конфігурація
│   └── odoo.test.conf   # Конфігурація для тестів
├── logs\               # Директорія для логів
├── data\               # Директорія для даних
├── backups\            # Директорія для резервних копій
├── custom_addons\      # Директорія для користувацьких модулів
├── odoo\               # Директорія з Odoo
└── venv\               # Віртуальне середовище Python

## Вимоги

- Windows 10/11
- PowerShell 5.1 або вище
- Права адміністратора для встановлення

## Ліцензія

MIT