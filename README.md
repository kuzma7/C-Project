# C-Project
# Техническое задание (ТЗ)

## 1. Назначение программы
Программа предназначена для автоматической загрузки данных из файла Excel в базу данных, такую как PostgreSQL или MySQL, используя язык программирования C#.

## 2. Основные функции программы
1. **Чтение данных из файла Excel**:
   - Поддержка форматов Excel: `.xls`, `.xlsx`.
   - Возможность выбора листа из книги Excel для загрузки данных.
   - Чтение всех строк и столбцов, либо выбор определенного диапазона.
  
2. **Обработка данных**:
   - Возможность обработки данных (например, проверка формата, валидация на соответствие типам данных БД).
   - Поддержка преобразований данных (например, приведение типов, очистка строк от пробелов).
   - Логирование ошибок при обработке данных.

3. **Интеграция с базой данных**:
   - Подключение к базе данных PostgreSQL/MySQL через строки подключения.
   - Создание таблицы в базе данных (если она еще не существует).
   - Запись данных из Excel в таблицу БД.
   - Проверка на наличие дублирующихся записей в БД (при необходимости).
   - Обработка транзакций для надежности (отмена транзакции при ошибке).

4. **Настройки программы**:
   - Возможность конфигурации через файл настроек (например, указание имени таблицы, строки подключения к БД, пути к файлу Excel).
   - Логирование процесса выполнения в файл или консоль (в зависимости от конфигурации).

## 3. Используемые технологии и библиотеки
- **Язык программирования**: C#
- **Библиотеки для работы с Excel**: `EPPlus` (или `NPOI`) для чтения и обработки Excel-файлов.
- **Подключение к базе данных**:
  - Для PostgreSQL: библиотека `Npgsql`.
  - Для MySQL: библиотека `MySqlConnector`.

## 4. Архитектура программы
1. **Модуль чтения данных**:
   - Использует библиотеку для работы с Excel для открытия и чтения данных из файла.
   - Опционально поддерживает фильтрацию данных по строкам/столбцам.

2. **Модуль обработки данных**:
   - Обрабатывает данные, проводит валидацию и преобразования (если требуется).
   
3. **Модуль записи в базу данных**:
   - Проверяет существование целевой таблицы в базе данных.
   - Вставляет данные в базу данных с поддержкой транзакций.

4. **Модуль конфигурации**:
   - Позволяет настраивать основные параметры (путь к файлу Excel, параметры подключения к БД, настройки логирования).

## 5. Требования к системе
- **Операционная система**: Windows/Linux
- **Среда разработки**: Visual Studio 2022 / Rider
- **База данных**: PostgreSQL 12+ или MySQL 8+
- **Фреймворк**: .NET 6.0 или новее
- **Дополнительные библиотеки**: EPPlus, Npgsql, MySqlConnector

## 6. Взаимодействие с пользователем
Программа должна быть консольной (CLI) с возможностью ввода параметров через командную строку или файл конфигурации:
- Путь к файлу Excel.
- Параметры подключения к базе данных.
- Имя таблицы в базе данных.

## 7. Логирование и отчеты
Программа должна вести логирование:
- Успешное подключение к базе данных.
- Успешная запись данных.
- Ошибки при подключении к базе данных.
- Ошибки при чтении данных из Excel.

## 8. Тестирование
Для тестирования необходимо использовать файлы Excel с разными структурами данных и наполнением, включая пустые строки и столбцы, неверные данные для проверки валидности.
