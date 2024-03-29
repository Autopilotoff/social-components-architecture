### Выбор баз данных

#### Контекст:

Сведения о типах БД, которые необходимо распределить (выбрать) для каждой части системы:

| Тип БД | Акцент | Представители |
| --- | --- | --- |
| Ключ-значение | Быстрый и малозатратный доступ, Поиск данных, Масштабируемость | Redis, Memcached, Amazon, DynamoDB, Riak, LevelDB |
| Документоориентированные БД | Гибкость данных, Высокая доступность, Быстрая разработка | MongoDB, RethinkDB, CouchDB |
| Колоночные БД | Высокая производительность, Упрощение сегментации, Масштабирование данных | Cassandra, HBase, ClickHouse |
| NewSQL | Горизонтальная масштабируемость, Высокая доступность, Большая производительность, Репликации, Небольшой функционал, Гибкость, Немалое потребление ресурсов  | SingleStore (MemSQL), VoltDB, Spanner, Calvin, CockroachDB, FaunaDB, yugabyteDB |
| Многомодельные БД | Линейная масштабируемость, Расширяемость моделей без изменений базовой структуры | ArangoDB, OrientDB, Couchbase |
| Реляционная | Целостность, Полнота, Повышенная точность, ACID-принципы | MySQL, MariaDB, PostgreSQL, SQLite |

Будут рассмотрены следующие документоориентированные БД:

| Критерий | MongoDB | CouchDB |
| --- | --- | --- |
| Репликация | Репликации вида master-slave, репликационные множества | Поддерживается ad-hoc - репликация, возможна настройка перекресной репликации между серверами  |
| Лицензирование | AGPL v3. Можно модифицировать, но обязательно публиковать, или покупать лицензию. Доступна тех.поддержка и обучение то 10х | Apache License 2.0. Отсутствие ограничений на использование и модификацию. Изменения и исходный код  публиковать необязательно. Доступна коммерческая тех. поддержка |
| Протокол интерфейса | Бинарный протокол на основе BSON. Требуются специальные драйверы | HTTP JSON REST интерфейс. Предпочтительно использование специальных драйверов |
| Структура БД | Документы разделяются на коллекции по типу (напоминает реляционные БД) | Все документы равнозначны и в самой БД не существует каких-либо разделений |
| Представления | Запросы вида WHERE из SQL. Существуют индексы по полям | Map/Reduce, создаются на JavaScript. Функция Map вызывается для всех документов в БД, что не всегда оптимально |
| Индексирование | Обновляет индексы сразу при редактировании документа | Производит индексацию для любого запроса, только при вызове запроса, обновляя все измененные документы, что может занять много времени при большом объеме БД |
| Способ хранения данных | Memory-mapped файлы. База хранится во множестве файлов | Хранятся в одном файле, запись осуществляется только в конец файла, старые ревизии и удаленные документы остаются в файле. Можно вызвать операцию удаления старых данных из файла (без блокировки БД) |
| Шардинг | Поддерживается начиная с версии 1.6 | Базово отсутствует |
| Безопасность | Рекомендуется использовать сервера БД в доверенной среде и не полагаться на встроенные в сервер средства безопасности. Аутентификация поддерживается в реплицированных множествах с версии 1.7.5 | Аутентификация на основе OAuth и базовая аутентификация HTTP |

Будут рассмотрены следующие реляционные БД:

| БД | Плюсы | Минусы | Предназначение |
| --- | --- | --- | --- |
| SQLite | хранение в одном файле, что облегчает перемещение; стандартизированность (использует SQL с некоторыми убранными функциями) | отсутствие пользовательского управления (отсутствие возможности управлять связями в таблицах в соответствии с привилегиями); невозможность дополнительной настройки | встроенные приложения; система доступа к дисковой памяти; тестирование |
| MySQL | простота установки, низкий порок входа; поддержка большей части функционала SQL; безопасность; мощность и масштабируемость (акцент на работу с большими объемами данных); скорость (за счет пренебрежения некоторыми стандартами) | ограничения функциональности; вопросы надёжности (некоторые операции реализованы менее надёжно, чем в других РСУБД); застой в продвижении и совершенствовании | распределённые операции; реализация требований высокой безопасности; веб-сайты и приложения; кастомные решения |
| PostgreSQL | полная SQL-совместимость; сообщество подержки; поддержка сторонними организациями; расширяемость (за счет встроенного функционала, например, хранимых процедур); объектно-ориентированность | производительность (не самая высокая при чтении данных); высокий порог входа | приоритет на надежность и целостность данных; сложные процедуры (за счет расширяемости); интеграция (легкое перемещение на другое решение) |

Будут рассмотрены следующие комбинированные типы БД:

| Критерий | SingleStore | VoltDB |
| --- | --- | --- |
| Лицензия | проприетарная | AGPL v3.0 и пользовательское соглашение |
| Версия | 8.0 | 12.0 (2022) |
| Язык |  SQL, для выполнения SQL-запросов осуществляет кодогенерацию в C++ | SQL, запросы в системе компилируются в форму хранимых процедур на Java |
| Особенности | Реализован синтаксис MySQL, дополнительно поддержаны тип JSON и пространственные типы и операции. Поддержано ведение журнала упреждающей записи, за счёт его применения на ведомых узлах реализована репликация (перенос с ведущего узла внесённых и изменённых данных). Облачное представление SingleStoreDB доступно во всех ведущих общедоступных облачных средах по всему миру. Имеет ведущие в отрасли сертификаты безопасности, в том числе ISO/IEC 27001, SOC 2, тип 2. Стоимость от 0.65$/час. | ACID-совместима, ориентирована на OLTP-нагрузки. Поддерживается синхронная репликация между сегментами. Используются непрерывные снимки. Есть коммерческая версия (с обеспечением высокой доступности, поддержкой экспорта данных). Объемная документация. Использует хранилище в памяти, чтобы максимизировать пропускную способность, избегая дорогостоящего доступа к диску. Дальнейший прирост производительности достигается за счет сериализации всего доступа к данным, что позволяет избежать многих трудоемких функций традиционных баз данных, таких как блокировка, фиксация и ведение журналов транзакций. |


#### Решение:

Будут выбраны следующие типы баз данных для частей системы:

| Сервис | Тип БД | Обоснование |
| --- | --- | --- |
| Тренировка | Документоориентированная | Требуется обеспечить высокую доступность данных |
| Календарь | Реляционная | Равная по интенсивности запись и чтение данных, требуется целостность данных |
| Датчики | Документоориентированная | Требуется эффективный поиск данных, масштабируемость, высокая доступность |
| Участники | Реляционная | Требуется целостность, согласованность, соблюдение ACID |
| Соревнование | NewSQL | Необходима эффективная запись, обработка больших объемов данных, быстрый отклик  |
| Новости | Документоориентированная | Приоритет на высокую доступность |

Будут выбраны следующие БД:

| Тип БД | БД | Обоснование |
| --- | --- | --- |
| Документоориентированная | MongoDB | Важна скорость доступа к данным, структура данных, надежность структуры хранения данных |
| Реляционная | PostgreSQL | Приоритет на надежность и целостность данных, широту возможностей и расширения |
| NewSQL | SingleStore |  Наличие поддержки 24/7, низкий порог входа по настройкам, интеграция с самыми распростаненными облачными провайдерами |

#### Статус:

предложен

#### Последствия:

Повышенное потребление ресурсов для NewSQL БД (обусловлено важностью обеспечения работы социальных компонентов системы). Возможно, предстоит нанять/обучить команду для работы с типами баз данных, которые еще не были использованы в компании.