## Описание сценариев использования приложения

### 1. _Приложение_

**Аутентификация** - окно для регистрации/входа пользователя. Если пользователя нет в системе, то предлагается зарегистрироваться, иначе аутентифицировать пользователя выбранным им способом (FaceId / Отпечаток / Код-пароль). Окно регистрации содержит поля для ввода email и телефона с их валидацией; после отправки формы отправляется смс-код на номер телефона для его подтверждения, на почту отправляется приветственное письмо со ссылкой на подтверждения email; после ввода кода из смс открывается окно выбора способа аутентификации.

**Календарь** - главный экран содержит компонент с календарем. На нем отображается текущий месяц с возможностью выбора другой месяц/год. Дни с тренировками маркируются. При нажатии на день открывается окно с тренировкой, с возможностью добавить/удалить тренировку, с возможностью по клику перейти в детали тренировки.

**Тренировка** - компонент для добавления/редактирования тренировки. Имеет возможность выбора вида спорта, типа тренировки, редактировать список упражнений (выбирать из списка или записывать свои). После выбора вида спорта и/или типа тренировки отображается кнопка перехода к рекомендациям. Также, при выборе места/площадки для тренировки позволяет выбрать точку на карте (или адрес). Есть функционал пригласить друга (другого участника, пользователя) на тренировку из контактов или списка друзей.

**Пригласить участника** - виджет для добавления друзей в список к пользователю. При первом открытии запрашивается запрос доступа к контактам телефона (также эти настройка доступка в настройках приложения). Виджет отображает список друзей-участников и форму глобального поиска по имени. Также есть возможность отсканировать QR-код камерой.

**Выбор инвентаря** - содержит товары для занятия спортом (продукция интернет-магазина). Товары разбиты на категории, которые отображаются плашками с иконками. Категории выбираются в зависимости от предпочтений пользователя. Данные о категориях берутся из календаря, либо отображаются популярные. Также пользователь может найти инвентарь с помощью формы поиска.

**Детали товара** - виджет отображает детальную информацию о товаре (инвентаре). Содержит описание, фотографии, характеристики, рейтинг, отзывы, кнопку для покупки. Виджет может быть переиспользован из интернет-магазина.

**Рекомендации** - отображает плашки видов спорта с наименованием и кратким описанием, также отображает новые добавленные рекомендации (ориентируясь на предпочтения пользователя, либо отображаются популярные). Пользователь выбирает вид спорта и переходит к деталям.

**Детали вида спорта** - отображается список упражнений с превью видео, а также список звезд спорта и тренеров по данному виду с возможностью просмотра данных по ним.

**Детали участника** - 

### 2. _Админка_