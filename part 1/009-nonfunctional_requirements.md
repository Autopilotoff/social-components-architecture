## Нефункциональные требования

Основываясь на бизнес-целях, функциональных требованиях и потребностях стейкхолдеров, составлен список основных нефункциональных требований. Список поделен на категории атрибутов качества, относящихся к требованиям.

1.  Доступность
    *   Сохранять данные о тренировке в оффлайн-режиме требуется до подключения/восстановления связи с сетью
    *   Обмениваться данными с датчиками(внешними устройствами) следует без участия сети, посредством bluetooth
    *   Работа уведомлений приложения (например, по тренировкам, календарю) должна быть независимой от сети
    *   Обновление приложения происходит в ночное время и в часы его неактивности, в зависимости от региона, в котором находится пользователь
    *   Непрерывное резервное копирование баз данных системы необходимо запускать раз в неделю
2.  Удобство использования
    *   Необходимыми данными для регистрации в системе являются номер телефона и email 
    *   Вход в приложение осуществляется посредством FaceId/отпечатка пальца/4-х значного кода
    *   Расположить календарь на главном экране приложения
    *   Предоставить доступ к списку участников-друзей с главного экрана
    *   Карта с участниками-друзьями должна быть доступна с главного экрана
    *   Обеспечить работу карты совместно с GPS в оффлайн-режиме, без участия сети интернет
3.  Обучаемость
    *   При первом открытии каждого окна приложения должна отображаться интерактивная инструкция (геймефицированная), подсвечивающая и объясняющая функционал
4.  Безопасность (защищенность пользовательских данных)
    *   Перед развертыванием образов контейнеров необходимо автоматически проверять их анализатором на наличие вредоносного ПО и уязвимостей, внедряющихся на стадии разработки средствами 
    *   Для гибкой настройки доступов пользователей(участников и администраторов) к сервисам необходимо использовать брокер, который способен кастомизировать политики безопасности
    *   Для обеспечения контроля входящего пользовательского трафика и возможности его ограничения необходимо использовать дополнительный прокси
    *   При входе в приложение необходимо отслеживать геопозицию пользователя и сравнивать его с домашним регионом для обнаружения и предотвращения несанкционированного входа в приложение (кражи учетных данных)
5.  Наблюдаемость
    *   Необходимо создать метрики для подсистемы Участники и подсистемы Тренировка в едином хранилище
    *   Требуется собирать данные об использовании рекомендаций тренировок и приобретения инвентаря пользователями (участниками) в общем хранилище
    *   Организовать логирование межсервисного взаимодействия (запросов, ответов)
    *   Хранить логи необходимо два месяца с возможностью оперативного доступа к ним, по истечении времени - архивировать и хранить
    *   Необходимо хранить логи обезличивая данные, предотвращая сохранение в них конфиденциальную информацию, средствами агрегаторов
    *   Требуется организовать трассировку при межсервисном взаимодействии, создав глобальный контекст запросов со сквозными идентификаторами