## Описание сценариев использования приложения

### 1. _Приложение_

**Аутентификация** - окно для регистрации/входа пользователя. Если пользователя нет в системе, то предлагается зарегистрироваться, иначе аутентифицировать пользователя выбранным им способом (FaceId / Отпечаток / Код-пароль). Окно регистрации содержит поля для ввода email и телефона с их валидацией; после отправки формы отправляется SMS-код на номер телефона для его подтверждения, на почту отправляется приветственное письмо со ссылкой на подтверждения email; после ввода кода из SMS открывается окно выбора способа аутентификации.

**Календарь** - главный экран содержит компонент с календарем. На нем отображается текущий месяц с возможностью выбора другой месяц/год. Дни с тренировками маркируются. При нажатии на день открывается окно с тренировкой, с возможностью добавить/удалить тренировку, с возможностью по клику перейти в детали тренировки.

**Тренировка** - компонент для добавления/редактирования тренировки. Имеет возможность выбора вида спорта, типа тренировки, редактировать список упражнений (выбирать из списка или записывать свои). После выбора вида спорта и/или типа тренировки отображается кнопка перехода к рекомендациям. Также, при выборе места/площадки для тренировки позволяет выбрать точку на карте (или адрес). Есть функционал пригласить друга (другого участника, пользователя) на тренировку из контактов или списка друзей.

**Приглашение участника в друзья** - виджет для добавления друзей в список к пользователю. При первом открытии запрашивается запрос доступа к контактам телефона (также эти настройка доступа в настройках приложения). Виджет отображает список друзей-участников и форму глобального поиска по имени. Также есть возможность отсканировать QR-код камерой.

**Выбор инвентаря** - содержит товары для занятия спортом (продукция интернет-магазина). Товары разбиты на категории, которые отображаются плашками с иконками. Категории выбираются в зависимости от предпочтений пользователя. Данные о категориях берутся из календаря, либо отображаются популярные. Также пользователь может найти инвентарь с помощью формы поиска.

**Детали товара** - виджет отображает детальную информацию о товаре (инвентаре). Содержит описание, фотографии, характеристики, рейтинг, отзывы, кнопку для покупки. Виджет может быть переиспользован из интернет-магазина.

**Рекомендации** - отображает плашки видов спорта с наименованием и кратким описанием, также отображает новые добавленные рекомендации (ориентируясь на предпочтения пользователя, либо отображаются популярные). Пользователь выбирает вид спорта и переходит к деталям.

**Детали вида спорта** - отображается список упражнений с превью видео, а также список звезд спорта и тренеров по данному виду с возможностью просмотра данных по ним.

**Детали участника** - компонент предоставляет сведения об участнике (имя, аватар, описание, достижения), его тип (тренер/профессионал/участник), его видео-представление (для профессионалов и тренеров), его виды спорта/направления.

**Детали упражнения** - компонент отображает описание упражнения, видео-рекомендации по  выполнению, необходимый инвентарь с ссылками на интернет-магазин.

**Редактирование данных пользователя** - компонент предоставляет возможность изменить основные данные, настроить уведомления и способ входа в приложение, настроить подключение к приложению устройств считывания данных датчиков (пульса), настроить видимость данных для других пользователей.

**Карта** - компонент открывается иконкой с главного экрана приложения. Отображает текущую гео-позицию, позволяет выбрать локацию для тренировки, отметить точки, посчитать расстояние по-прямой, по маршруту (по дорогам, по точкам).

**Сравнение участников** - данный виджет позволяет выбрать участника из списка друзей (и глобального списка), сравнить данные по количеству и времени тренировок, участию в соревнованиях и занятых местах.

**Соревнование** - функционал предоставляет возможность создать соревнование, выбрать его тип (велосипед, лыжи, бег), построить маршрут на карте, добавить участников из списка друзей, настроить время и дату старта с добавлением в календарь и с уведомлением приглашенных участников.

**Уведомления** - виджет открывается иконкой с главного экрана, из шапки приложения (с отображением непрочитанных). Показывает список уведомлений. Каждое уведомление содержит кнопки управления. Например, когда приходит уведомление о приглашении на соревнование, то есть возможность добавить это соревнование себе в календарь.

**Новости** - виджет отображает блок плашек на главном экране под календарем. Новости содержат новые рекомендации по тренировкам для предпочтительных видов спорта, появление нового инвентаря, новости о прошедших соревнованиях, присоединение топ-участников (в дальнейшем, возможно добавление новостей спорта).

**Редактирование упражнений участников** - пользователь может создавать свои упражнения и включать их в свой цикл тренировок. Есть возможность добавлять, удалять, изменять созданные пользователем тренировки.

**Набор подсказок для компонентов** - для обучения пользователей функциям приложения на каждый экран (компонент) при первом его открытии отображаются подсказки на кнопки и формы с полями, что какая кнопка делает, за что отвечает компонент.

### 2. _Админка_

**Редактирование топовых участников** - CRUD для участников профессионалов и тренеров (с возможностью экспорта данных из json-коллекции).

**Редактирование рекомендаций** - CRUD для рекомендаций по тренировкам с возможностью добавления/удаления видео-контента.

**Редактирование типов тренировок** - CRUD для типов тренировок и видов спорта, функционал для редактирования связей с типами инвентаря (с возможностью экспорта данных из json-коллекции).

**Редактирование упражнений** - CRUD для упражнений (с возможностью экспорта данных из json-коллекции).

**Редактирование новостей** - CRUD для новостей, созданных вручную, выбор категорий новостей для отображения (с возможностью экспорта данных из json-коллекции).
