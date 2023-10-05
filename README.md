# Miner Search

[English readme file](https://github.com/BlendLog/MinerSearch/blob/master/README_EN.MD)

Программа разработанная для поиска и уничтожения скрытых майнеров.
Является вспомогательным инструментом для поиска подозрительных файлов, каталогов, процессов и тд. и НЕ является антивирусом. 

### ВНИМАНИЕ! Некоторые антивирусы помечают этот проект как троян. Это ложное срабатывание, просто добавьте исполняемый файл в исключение антивируса

Версия v1.4.5
- Вывод параметров запуска задачи из планировщика
- Стороняя библиотека Microsoft.Win32.TaskScheduler больше не требуется. 
- Добавлено обнаружение и удаление руткита майнера
- Исправлен баг, когда сканируемый процесс уже завершил работу
- Исправлен баг, когда запрошенный доступ к реестру запрещен
- Лог файл записывается в корень сканируемого диска
- Требуемая версия NET Framework понижена до 4.5.2
- Исправление мелких недоработок
- Пополнение базы вредоносных записей в файле hosts

Версия v1.4.4
- Исправлен баг с невозможностью удалить найденные файлы до закрытия программы
- Улучшен алгоритм поиска майнера при статическом анализе
- Сокращено ложное срабатывание Антивирусных решений. Некоторые антивирусы всё ещё могут помечать файл как троян, просто добавьте в исключение. 
- Добавлен параметр --depth. Устанавливает максимальное значение глубины поиска при сигнатурном сканировании. Пример использования: --depth=3 (по умолчанию 8). 
- Добавлена сигнатурная проверка файлов из планировщика задач
- Добавлен счетчик запуска MinerSearch
- Добавлен параметр --winpemode. В это режиме запрашивается буква диска для сканирования. Предполагается, что это диск с зараженной системой. Сканирование процессов, реестра, задач планировщика, каталогов в профиле пользователя не производится. Далее, необходимо снова загрузится в зараженную систему и выполнить повторное сканирование. 

Версия v1.4.3
- Добавлен сигнатурное обнаружение подозрительных файлов
- Добавлена краткая информация о системе в лог
- Удаление вредоносных записей в hosts файле, а не самого файла. Подтверждение не требуется
- Исправлен баг, при котором не удается получать аргументы командной строки в связи с отключением службы WMI.
- Добавлен карантин. Кроме файлов, обнаруженных при статическом анализе, также создается txt файл с прежними путями этих файлов
- Исправить баг при неверном определении инжекта в процесс Dwm на Win 8 (не 8.1)
- Удаление пользователя John, если это не текущий пользователь
- Добавлена создание защищенных скрытых файлов от повторного заражение
- Обработка исключения TCP подключений для процессов
- Исправлен баг с ошибкой "Отказано в доступе" для некоторых файлов
- Исправлен баг с невозможностью разблокировать каталог при установленом Антивирусе
- Добавлено автоматическое удаление недействительных задач из планировщика на основе результата последнего запуска. Для лучшего результата следует перезагрузить ПК после сканирования. Параметр --remove-empty-tasks также работает.
- Добавлен параметр запуска --no-signature-scan для пропуска скнирования по сигнатурам

Версия v1.4.2
- Добавлено определение загрузки ОС
- Добавлено удаление вредоносных путей из исключения Windows Defender
- Добавлено удаление вредоносных правил из брандмауэра Windows
- Удаление каталогов и восстановление прав на них выполняется отдельно
- Сканирование файла hosts теперь выполняется в конце
- Исправлен баг с пропуском дубликатов задач в планировщике задач


Версия v1.4

- Переработан алгоритм проверки и удаления вредоносных каталогов / файлов
- Добавлена проверка планировщика задач
- Переработать алгоритм парсинга пути приложения в автозапуске из реестра
- Добавлена проверка, действительно ли процесс приостановлен
- Добавлена функция переименования вредоносных файлов процессов
- Добавлен вызов справки --help
- Переработана проверка цифровой подписи
- Текст в логе теперь не дублируется
- Исправлен баг, когда входная строка имела неверный формат
- Добавлена проверка родительского процесса

Версия v1.3

- Добавлена проверка цифровой подписи файлов
- Добавлены дополнительные разделы сканирования реестра (разделы автозапуска, appinit_dlls)
- Изменён метод ведения логов. Статистика сканирования параллельно записывается в файл в формате MinerSearch_ГГГГ_ММ_дд_мм_сс.log
- Исправлены незначительные недоработки

Для запуска требуется NET Framework 4.5.2 (до 1.4.5)


# Demo

Обнаруживает и приостанавливает вредоносные процессы, а также вспомогательне компоненты майнера, которые затруденяют его удаление.
## Screenshots

![image](https://user-images.githubusercontent.com/56220293/215475650-25d31515-d52a-485b-b194-7db63e0e9962.png)

![image2](https://user-images.githubusercontent.com/56220293/215356942-8080b05a-f324-4006-9864-6843923ff2be.png)
