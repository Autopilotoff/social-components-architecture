Ссылка на презентацию

https://docs.google.com/presentation/d/19-l8pRnCyid7GYth1cqJkYVAlhWJ2BhnnV0qjVK7itE/edit?usp=sharing

### План презентации

- О себе 2
- Компания и бизнес-цели 4-6
- Функциональные требования 7-8
- Атрибуты качества 9-10
- Базовая архитектура 11-12
- Инфраструктура 13
- Риски реализации 14-15
- Стоимость владения 16-17

---

### Речь

-- о себе --

всем добрый день еще раз, меня зовут Булатов Иван, я backend-разработчик, работаю в банке, занимаюсь проектом, связанным с валютными операциями между резидентами и нерезидентами страны.

я пошел на курс по архитектуре чтобы начать глобальнее смотреть на системы в целом, чтобы научиться проектировать большие нагруженные приложения, хотел начать понимать из чего они состоят и какие они могут быть, это очень интересно.

пройдя курс я уже применяю новые знания во время работы, когда происходит планирование и и грумминги.

-- к работе -- 

В рамках дипломной работы предстояло сделать и обосновать архитектуру приложения для компании по предложенному описанию (заданию) и списку требований.

я расскажу
(слайд - структура презентации)
Сначала - о компании и ее бизнес целях, далее - о функциональных требования и атрибутах качества, потом - рассмотрим базовую архитектуру и инфраструктуру, расскажу про риски реализации и стоимость владения системой.

Компания занимается производством и продажей спортивных товаров и инвентаря.
Предстояло создать приложение для стимулирования спроса на товары и продвижения своей продукции и популяризации спорта в целом.
(слайд-общая картинка компании)

В качестве стратегических целей определены:
(слайд-цели)
- Популяризация и продвижение продукции
- Освоение новых каналов для информирования клиентов

(- Предоставление клиентам возможности достижения целей в спорте)
(- Стимулирование людей соревноваться с собой и другими)
(- Повышение вовлечённости в здоровый образ жизни)

А операционные цели это:
- Реализация социальных компонентов в приложение
- Формирование социальных групп по интересам

(- Организация самоподдержки между участниками)
(- Формирование образа бренда)

Так как занятия спортом это тренировки и соревнования, а для этого предпочтительно составлять расписание, то отсюда появляются первые функциональные требования: реализовать компоненты Календаря, Тренировки и Участников, компоненты создания соревнований и приглашения друзей для участия. Еще нужен компонент карты для построения маршрутов с отслеживанием GPS-координат.

(слайд с картинками)

Чтобы продвигать товары компании предложено добавить компоненты рекомендаций по тренировкам, компоненты новостей и уведомлений, и сделать единый запоминающийся стиль приложения.

Основываясь на бизнес-целях, функциональных требованиях и потребностях стейкхолдеров (а основными стейкхолдерами являются пользователи и компания с командой), составлен список атрибутов качества и нефункциональных требований.

(слайд - атрибуты качества который нефункциональные требования)

Главными атрибутами обозначены доступность и удобство использования, так как они обеспечивают вовлеченность и интерес использовать приложение.
Так же обозначены безопасность и наблюдаемость, соответственно, для обеспечения конфиденциальности данных, организации мониторинга и аналитики процессов.

Известно, что 90% всех систем компании находится в облаке и компания охотно адаптирует новые технологии и хочет быть свободной в выборе облачных провайдеров под свои задачи. Чтобы соответствовать тренду компании основой станет микросервисная архитектура, DDD и принцип прототипирования (MVP).

Исходя из этого создано представление базовой архитектуры.

(слайд - упрощенная картинка базовой архитектуры)

На ней отображены основные части системы и связи.

Предполагается, что у компании уже есть сервисы, работающие с продукцией, нотификациями и поддержкой, поэтому они будут интегрированы в приложение.
В качестве типа облачных услуг выбрана инфраструктура как сервис (IaaS), так как необходимо максимально абстрагироваться от облачного провайдера (cloud agnostic), уже имеется штат специалистов и опыт разработки приложений для облачной инфраструктуры, а еще требуется гибкость конфигурации (управлении ресурсами, доступами).

В качестве способа хранения данных взяты три типа баз: документоориентированная, реляционная и newSql-хранилище.

(слайд - таблицы "компонент-сервис, тип БД")

Для компонентов Календарь, участники, Пользователи - выбран реляционный тип баз данных, потому что здесь в первую очередь требуется целостность и согласованность.
Для компонентов Тренировки, Рекомендации, Датчики, Новости, Карта - выбран документоориентированный тип, потому что здесь приоритетом является доступность, быстрый отклик, нужно без задержек просматривать информацию о тренировках и рекомендациях, а еще необходима гибкость моделирования данных.
А для аналитики и соревнований предусмотрено комбинированное распределенное newSql-хранилище, так как необходим быстрый отклик и обработка больших объемов данных (это статистика, данные с датчиков, информация об участниках).

С точки зрения инфраструктуры создано следующее представление:

(слайд - инфраструктурное представление)

Для самых нагруженных и требующих стабильности работы подсистем используется по три стэнда (dev, test, prod) с разделением по сервисам и базам. Также предусмотрены отдельные стенды для тестирования фронтовой части приложения и тестирования работы со статистикой.

Что касается рисков реализации проекта. В общем виде рисками являются неокупаемость вложенных ресурсов и ухудшение имиджа компании.

(слайд про риски)

Если детальнее на них посмотреть, то:
- К бизнесовым следует отнести риск разрастания объема работ, потому что может происходить постоянное бесконтрольное добавление функций в проект. Из-за этого может стать непонятным дата выхода проекта. Следует до начала работ обговорить и зафиксировать требования и объем, плюс регулярно проверять соблюдение плана.
- К техническим следует отнести риски связанные с известными уязвимостями систем. Они минимизируются с помощью статических средств проверки кодовой базы и во время выполнения, инструментов профилирования, инструментами стресс-тестирования и тестирования на нелегальное проникновение, а также применения принципа "наименьших привилегий" (установление границ между привилегированными и непривилегированными частями системы, как подсистемой участников с пользователями и тренировками с рекомендациями).

Перейдем к завершающей части, к стоимости владения системой.

(слайд-стоимость владения)

Составлены две таблицы, это расходы на инфраструктуру и зарплаты.
Получилось, что наибольшие расходы будут на IaaS и ELK, а зарплаты были взяты как ориентировочные округленные значения.
Посчитав зарплату, я обратил внимание и немного засомневался правильно ли я выбрал IaaS вместо PaaS, потому что расходы на зарплату специалиста devOps-ера и расходы на PaaS значительно различаются, но важно было отталкиваться от требований, а также можно оптимизировать время работы сотрудников, воспользовавшись опытом и наработками команд компании.

доп.слайды
- про ADR
- про таблицу "Тип БД, БД"
- про каждое из представлений
- про план разработки
- про сценарии использования
- про другие риски бизнесовые и технические


