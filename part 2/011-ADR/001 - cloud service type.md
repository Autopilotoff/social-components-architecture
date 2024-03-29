### Выбор типа облачных услуг

#### Контекст:

Необходимо выбрать тип облачных услуг, рассмотрены следующие варианты:
- IaaS (Infrastructure as a Service)
- PaaS (Platform as a Service)
- SaaS (Software as a Service)

**IaaS** - предоставление провайдером инфраструктуры (вычислительных мощностей) в аренду.

На стороне облачного провайдера - виртуализация, оборудование, системные инженеры, инфраструктура дата-центра.

На стороне клиента - администрирование ОС, администрирование БД, администрирование приложений, мониторинг, резервное копирование, ПК/ноутбуки и каналы связи, офис (рабочие места и электричество).

Особенности IaaS - можно устанавливать на сервере любые программы, производить любые операции; можно разделять ресурсы на проекты внутри аккаунта и определять правила доступа для разных пользователей; нагрузку между серверами можно распределять равномерно с помощью балансировщиков; файлы и бэкапы можно поместить в облачное хранилище; провайдеры предоставляют сервисы, которые создают резервные копии инфраструктуры и при сбоях автоматически переносят туда нагрузку.

Плюсы IaaS - экономичность (оплата только за потребляемые ресурсы, нет необходимости платить за модернизацию оборудованию и платить специалистам за это); лёгкая масштабируемость (можно регулировать потребление ресурсов автоматически); гибкость (свобода выбора под какие нужды использовать ресурсы).

Минусы IaaS - сложность (нужны специальные знания и навыки); качество работы вашей инфраструктуры зависит от надёжности и добросовестности провайдера.

IaaS подходит, когда есть сильные скачки спроса в определенные периоды времени, а также при необходимости разворачивать отдельные среды для тестирования программ (которые, после использование, можно свернуть).

**PaaS** - предварительно настроенный набор инструментов, который провайдер предоставляет клиентам для создания ими своих приложений.

На стороне облачного провайдера - виртуализация, оборудование, системные инженеры, инфраструктура дата-центра, администрирование ОС, администрирование БД.

На стороне клиента - администрирование приложений, мониторинг, резервное копирование, ПК/ноутбуки и каналы связи, офис (рабочие места и электричество).

Особенности PaaS - на платформе уже есть готовые инструменты для различных нужд клиентов (AI-инструменты, загрузка и обработка данных для ML, инструменты управления и базами данных и их анализа).

Плюсы PaaS - упрощение и удешевление процесса разработки программ; готовые, настроенные инструменты для разработки.

Минусы PaaS - меньшая степень контроля над вычислительной инфраструктурой (в сравнении с IaaS); возможности разработки ограничены тем функционалом, который предлагает провайдер.

**SaaS** - полностью готовые к работе программы, настроенные на решение задач клиента (электронная почта, конструкторы для создания сайтов, CRM-системы, сервисы видеозвонков).

На стороне облачного провайдера - виртуализация, оборудование, системные инженеры, инфраструктура дата-центра, администрирование ОС, администрирование БД, администрирование приложений, мониторинг, резервное копирование.

На стороне клиента -  ПК/ноутбуки и каналы связи, офис (рабочие места и электричество).

SaaS подходит, когда клиенту требуется типовое решение, уже имеющееся на рынке (электронная почта, CRM-система), когда нет смысла и ресурсов разрабатывать свой комплекс программ. Также подходит для краткосрочных проектов.

Плюсы SaaS - готовое решение (не нужно тратить время на разработку и нанимать специалистов); клиент может больше сосредоточиться на решении своих бизнес-задач; для получения доступа к SaaS обычно нужны только браузер и подключение к интернету.

Минусы SaaS - возможности ограничены функционалом программы; работу SaaS контролирует провайдер; ограниченные возможности интеграции с другими приложениями и сервисами.

#### Решение:

Будет использоваться **IaaS**, так как:

- необходимо максимально абстрагироваться от облачного провайдера;
- уже имеется штат специалистов и опыт разработки приложений для облаков;
- требуется гибкость в конфигурации, управлении ресурсами, доступов, настройке отдельных сред разработки.

#### Статус:

предложен

#### Последствия:

После выбора типа облачных услуг IaaS предстоит проанализировать и выбрать средства и инструменты, которые будут использоваться вокруг приложения, которые необходимо подготовить и настроить средствами команды.
