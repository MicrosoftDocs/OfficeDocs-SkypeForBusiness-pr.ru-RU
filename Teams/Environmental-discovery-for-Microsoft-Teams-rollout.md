---
title: Совместимость с среде Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Подробное обнаружение среды при планировании пути от Skype для бизнеса до Microsoft Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fdaafeb9042f8b76b40c797109740af5c93ef077
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635053"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Обнаружение среды для Microsoft Teams среды

Обнаружение — один из первых ключевых этапов, которые необходимо предпринять при планировании пути к Microsoft Teams.

Вы выполняете подробное обнаружение среды, чтобы лучше понять ее текущее состояние, а также выявить все сложности или ( и даже далее) возможные блоки выполнения Teams развернутого проекта.

## <a name="discovery-questionnaire"></a>Анкета обнаружения

В приведенном ниже примере анкеты приведены вопросы о том, готова ли ваша организация к успешному телефонная система аудиоконференцию и планы звонков в Teams.

Все вопросы, относящиеся к существующей инфраструктуре совместной работы и организации Microsoft 365 или Office 365 организации, сети, конечные точки, операции, а также внедрение и готовности, включаются в анкету по обнаружению среды.

Анкета состоит из нескольких разделов, чтобы подтвердить готовность организации к развертыванию Teams в нескольких основных областях. Работайте со своей проектной командой, чтобы предоставить запрашиваемую информацию как можно более подробно, чтобы упростить планирование.

> [!TIP]
> Для начала скопируйте анкету в Microsoft Word документ. Постарайтесь отвечать на все вопросы и фиксировать все сведения по мере перемещения.

### <a name="project-team"></a>Project группы

Запечатлейте подробные сведения о ключевых заинтересованных лицах Teams проекта. Обратите внимание, что один человек может играть несколько ролей в проекте.

> | Должность | Имя, адрес электронной почты, номер телефона | Расположение, часовой пояс | Комментарии |
> |---|---|---|---|
> | Ответственный спонсор | | | |
> | Начальник проектной группы | | | |
> | Руководитель/архитектор по совместной работе | | | |
> | Консультант | | | |
> | Руководитель проекта | | | |
> | Специалист по управлению изменениями/освоению | | | |
> | Руководитель по сетям | | | |
> | Руководитель по безопасности | | | |
> | Руководитель по телефонии | | | |
> | Руководитель по настольным системам | | | |
> | Руководитель службы технической поддержки | | | |
> | Руководитель по развертыванию | | | |
> | Владелец службы | | | |
> | Руководитель по обслуживанию помещений | | | |
> | Руководитель команды по работе с видео | | | |
> | Бизнес-руководства по блокам | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 или Office 365 сведения об организации

Мы настоятельно рекомендуем вам при работе с анкетой Microsoft 365 или Office 365 организации. Если вы еще не активировали или не настроили Microsoft 365 или Office 365 организации, см. планирование настройки Microsoft 365 [для бизнеса.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

В таблице ниже фиксироваться сведения о Microsoft 365 или Office 365 организации.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Обратите внимание на Microsoft 365<br/>или Office 365 название и ИД организации<br/>в столбце Answer. Если у вас есть еще<br/>несколько клиентов, связанных с<br/>в вашей организации, обратите внимание на все ИД. | Имя клиента: <br/>ИД клиента:| |
> | В каких регионах развернуты клиенты?| | |
> | Обратите внимание на тип Microsoft 365 или <br/>Office 365 клиентов. Являются ли они мультитенантными <br/>или Выделенный? | <input type="checkbox"> Многопользовательского<br/> <input type="checkbox"> Выделенный | |
> | Какие продукты Microsoft Online вы используете сейчас? <br/>Обратите внимание на количество пользователей, включенных для каждого из них <br/>в столбце Комментарии. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype для бизнеса <br/>&nbsp; &nbsp; &nbsp;В Интернете <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Онлайн <br/> <input type="checkbox">OneDrive для бизнеса <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> Других| |
> | Для какого уровня лицензии Skype <br/>Пользователи Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Количество пользователей <br/>для каждого SKU: |
> | Что такое текущий лес Active Directory <br/>функциональный уровень в среде? <br/>Если имеется несколько лесов, обратите внимание на подробные сведения <br/>в столбце Комментарии. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Что вы используете для использования в каталоге <br/>синхронизация сегодня? |<input type="checkbox"> Нет синхронизации (только в облаке) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Подключение <br/> <input type="checkbox"> Другое (укажите в <br/>&nbsp;&nbsp; &nbsp; Столбец Комментарии.)| |
> | Развернуто ли сейчас федеративное удостоверение <br/>(Службы федерации Active Directory или <br/>сторонние стороны) | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если вы используете федератное удостоверение, что такое <br/>инфраструктура федерации? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows AD FS 2012 <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows AD FS 2016 <br/> <input type="checkbox"> Федерация сторонних сторон <br/>&nbsp;&nbsp; &nbsp; шлюз (обратите внимание на подробные сведения <br/>&nbsp;&nbsp; &nbsp; в столбце Комментарии.) | |
> | Если вы ведете активный Microsoft 365<br/>или Office 365, является доменом SMTP/SIP <br/>ваши целевые пользователи, связанные с клиентом? | <input type="checkbox">Н/Н — нет Microsoft 365 или<br/>&nbsp;&nbsp; &nbsp; Office 365 клиента на месте <br/> <input type="checkbox"> Нет, SMTP/SIP пользователей <br/>&nbsp;&nbsp; &nbsp; домен не связан <br/>&nbsp;&nbsp; &nbsp; с любыми клиентами в <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365<br/> <input type="checkbox"> Да, SMTP/SIP пользователей <br/>&nbsp;&nbsp; &nbsp; домен связан <br/>&nbsp;&nbsp; &nbsp; с существующим клиентом в <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365 | |
> | Совпадают ли пользователи-пользователи с основным SMTP-адресом? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Непоследовательно | |

## <a name="existing-collaboration-platform-summary"></a>Сводка по существующей платформе совместной работы

В таблице ниже фиксироваться сведения о существующем развертывании платформы для совместной работы.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Развернута ли система Microsoft Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернута ли система Skype для бизнеса? <br/>Для локального и гибридного развертывания убедитесь, что <br/>обратите внимание на версию и накопительный итоговую версию (CU). <br/>подробные сведения в столбце Комментарии. | <input type="checkbox">Да, Microsoft 365 или <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br/>&nbsp;&nbsp; &nbsp; (Майкрософт) <br/> <input type="checkbox"> Да, hosted, dedicated <br/>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox"> Да, hosted, shared <br/>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox"> Нет, другие | |
> | Развернута ли система Microsoft Exchange? <br/>Для локального и гибридного развертывания убедитесь, что <br/>сведения о версии и подсказке в примечастях <br/>Столбца. | <input type="checkbox">Да, Microsoft 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br/>&nbsp;&nbsp; &nbsp; (Майкрософт) <br/> <input type="checkbox"> Да, hosted, dedicated <br/>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox"> Да, hosted, shared <br/>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox"> Нет, другие | |
> | Развернута ли система SharePoint? <br/>Для локального и гибридного развертывания убедитесь, что <br/>сведения о версии и подсказке в примечастях <br/>Столбца. | <input type="checkbox">Да, Microsoft 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br/>&nbsp;&nbsp; &nbsp; (Майкрософт) <br/> <input type="checkbox"> Да, hosted, dedicated <br/>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox"> Да, hosted, shared <br/>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox"> Нет, другие | |
> | Развертывается OneDrive для бизнеса развертывания? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развертываются ли другие сторонние платформы <br/>и используете уже сейчас? В этом случае обратите внимание на количество пользователей <br/>эти платформы и сведения об использовании в <br/>Столбец Комментарии. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Слабину <br/> <input type="checkbox"> Другое (укажите в <br/>&nbsp;&nbsp; &nbsp; Столбец Комментарии.) | Количество пользователей: <br/>Детали:|
> | Вы планируете переместить пользователей из этих сторонних <br/>платформы для Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Что такое текущее решение для телефонии и связи? <br/>из пользователей, которые находятся в области действия этой инициативы? | | |
> | Поддерживают ли [вы SBC развертывание прямой](./direct-routing-plan.md#supported-session-border-controllers-sbcs) маршрутии? <br/>для ваших офисов, которые находятся в области действия этой инициативы? Если да,<br/>обратите внимание на сведения в столбце Комментарии.| <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||

## <a name="collaboration-platform-deployment-details"></a>Сведения о развертывании платформы для совместной работы

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (при наличии)

Если применимо, зафиксировать сведения о развертывании Teams с помощью приведенной ниже таблицы. Если вы еще не развернули Teams, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каким группам пользователей доступна система Teams? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Определенные пользователи и группы пользователей <br/>&nbsp;&nbsp; &nbsp; (Укажите в столбце При комментарии.) ||
> | Какие Teams и модалии используются? | <input type="checkbox"> Беседы на основе каналов <br/> <input type="checkbox"> Частный чат <br/> <input type="checkbox"> Гостевой доступ <br/> <input type="checkbox"> Собрания каналов <br/> <input type="checkbox"> Частные собрания <br/> <input type="checkbox"> Частные вызовы <br/> <input type="checkbox"> Ad-hoc channel meetup <br/> <input type="checkbox"> Видео на собраниях <br/> <input type="checkbox"> Общий доступ к экрану на собраниях <br/> <input type="checkbox"> Аудиоконференций <br/><input type="checkbox"> Приложения (приложения)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Вкладки<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Ботов <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Соединители<br/><input type="checkbox"> Интеграция пользовательского облачного хранилища <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Диск, Egnyte <br/> <input type="checkbox"> Интеграция с электронной почтой каналов <br/> <input type="checkbox"> Другое (укажите в столбце Прикомменты.) | |
> | Какие приложения вы развернули в Teams? | | |
> | Блокировали ли вы какие-то конкретные возможности Teams? <br/>Если да, обратите внимание на сведения в столбце Комментарии. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Какие используются клиенты Teams? | <input type="checkbox"> Веб <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Мобильных | |
> | Кому разрешено создавать команды? | <input type="checkbox"> Все в организации <br/>&nbsp;&nbsp; &nbsp; (Этот параметр заданной по умолчанию) <br/> <input type="checkbox"> Определенные люди <br/>&nbsp;&nbsp; &nbsp; (Укажите в столбце При комментарии.) | |
> | Используете ли вы в Teams функции обеспечения безопасности и соответствия требованиям? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-online-if-applicable"></a>Skype для бизнеса Online (при наличии)

Если применимо, зафиксировать сведения о развертывании Skype для бизнеса Online можно с помощью приведенной ниже таблицы. Если вы еще не развернули Skype для бизнеса Online, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Типы пользователей, для Skype <br/>для бизнеса Online? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Определенные пользователи и группы пользователей <br/>&nbsp;&nbsp; &nbsp; (Укажите в столбце При комментарии.) | |
> | Какие модали и функции в настоящее время <br/>используется сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (мгновенные сообщения/P)<br/> <input type="checkbox"> Конференций <br/> <input type="checkbox"> Федерации <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Аудиоконференция Майкрософт <br/> <input type="checkbox"> Аудиоконференция сторонних сторон (примечание)<br/>&nbsp;&nbsp; &nbsp; подробные сведения в столбце Комментарии.) <br/> <input type="checkbox"> Планы звонков (ранее — "Вызовы через ЗВОНКОВ по ЗВОНКОВ") <br/> <input type="checkbox"> Автоотправления организации <br/> <input type="checkbox"> Очереди вызовов | |
> | Вы специально заблокировали любые Skype для <br/>Возможности Business Online? <br/>Если да, обратите внимание на сведения в столбце Комментарии. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какой метод вы используете или планируете использовать <br/>подключить телефонная система (ранее Облачная УАКС) к <br/>ДНР? <br/>Выберите все, что применимо. | <input type="checkbox"> Планы звонков (ранее — "Вызовы через ЗВОНКОВ по ЗВОНКОВ") <br/> <input type="checkbox"> Локальное подключение к STN <br/>&nbsp;&nbsp; &nbsp; (использование существующих Skype для <br/>&nbsp;&nbsp; &nbsp; Business 2015 или Lync Server <br/>&nbsp;&nbsp; &nbsp; Развертывание в 2013 г.) <br/> <input type="checkbox"> Локальное подключение к STN <br/>&nbsp;&nbsp; &nbsp; (с помощью Cloud Connector) | |
> | Есть ли у вас телефонные номера, перенесенные в Майкрософт <br/>Это относится к планам звонков и звуку <br/>Функции для conferencing. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype для бизнеса локальной (если применимо)

Если применимо, зафиксировать сведения о развертывании Skype для бизнеса с помощью приведенной ниже таблицы. Если вы еще не развернули Skype для бизнеса локально, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие версии Lync или Skype для бизнеса <br/> развертываются локально? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype для бизнеса Server 2015 г. <br/> <input type="checkbox">Skype для бизнеса Server 2019 г. <br/><input type="checkbox">Skype для бизнеса Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Издание | |
> | Настроено ли гибридное подключение со Skype для бизнеса Online? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Эта среда находится и управляется третьей <br/>Партии? Если да, обратите внимание на сведения в <br/>Столбец Комментарии. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какие модали и функции используются в настоящее время <br/>Сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (мгновенные сообщения/P) <br/> <input type="checkbox"> Конференций <br/> <input type="checkbox"> Федерации <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Сохраняемая беседа или групповой чат <br/> <input type="checkbox"> Аудиоконференция Майкрософт <br/>&nbsp;&nbsp; &nbsp; (ранее Dial in Conferencing) на <br/>&nbsp;&nbsp; &nbsp; локального сервера Lync Server или <br/>&nbsp;&nbsp; &nbsp; Skype для бизнеса развертывания <br/> <input type="checkbox"> Аудиоконференция сторонних сторон <br/>&nbsp;&nbsp; &nbsp; (Обратите внимание на подробные сведения в примечастях. <br/>&nbsp;&nbsp; &nbsp; столбец.) <br/> <input type="checkbox">Корпоративная голосовая связь с использованием локальной <br/>&nbsp; &nbsp; &nbsp;Связь с ТСОП <br/> <input type="checkbox"> Планы звонков (ранее — "Вызовы через ЗВОНКОВ по ЗВОНКОВ по ЗВОНКОВ") через <br/>&nbsp;&nbsp; &nbsp; Гибридное гибридное Skype для бизнеса Online | |
> | Какие у вас развернуты версии пограничного сервера? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype для бизнеса Server 2015 г. <br/> <input type="checkbox">Skype для бизнеса Server 2019 г.| |
> | У вас есть Lync или Skype для бизнеса Edge <br/>развернуто в несколько центра обработки данных? <br/>Если да, обратите внимание на сведения в столбце Комментарии. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Выберите службы, которые предоставляет ваша роль Edge сегодня. | <input type="checkbox"> Доступ внешних пользователей (корпоративных пользователей) <br/> <input type="checkbox"> Удаленный доступ пользователей (анонимный) <br/>&nbsp;&nbsp; &nbsp; внешние участники собрания) <br/> <input type="checkbox"> Федерации <br/> <input type="checkbox"> Ретранслятор мультимедиа | |
> | Какие из следующих функций голосовых звонков вам <br/>в настоящее время есть зависимости от? <br/>Обратите внимание на дополнительные зависимости в примечаниях. <br/>Столбца. | <input type="checkbox"> Параметры занятости <br/> <input type="checkbox"> Парк вызовов <br/> <input type="checkbox"> Выбор звонка или групповой звонок <br/> <input type="checkbox"> Обычные телефоны с регионами или "телефоны с рабочим столом" <br/> <input type="checkbox"> Группы ответа или группы по поиску <br/> <input type="checkbox"> Внешний вид общей строки <br/> <input type="checkbox"> Частная линия <br/> <input type="checkbox"> Голосовую почту <br/> <input type="checkbox"> Звонок с помощью работы <br/> <input type="checkbox"> Номера экстренных служб или информации <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Набор расширений <br/> <input type="checkbox"> Автосекретаря <br/> <input type="checkbox"> Доступ для подписчиков <br/> <input type="checkbox"> Аналоговые устройства <br/> <input type="checkbox"> Факс <br/> <input type="checkbox"> Маскировка или изменение ИД вызываемой вызовы <br/> <input type="checkbox"> Маршруты на основе расположения <br/> <input type="checkbox"> Наименее затратная маршрутия <br/> <input type="checkbox"> Телефоны с телефонами | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Сеть и доступ к Microsoft 365 и Office 365 службам

В таблице ниже фиксироваться сведения о сети организации и то, как ваши пользователи (или будут) подключены к Microsoft 365 и Office 365 службам.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Действия (и каким образом) пользователи, в области миграции <br/>получать Teams, когда они в офисе? <br/>Выберите все, что применимо. | <input type="checkbox"> Маршрутное подключение NAT <br/> <input type="checkbox"> Прокси-сервер <br/> <input type="checkbox"> Общедоступные Wi-Fi <br/> <input type="checkbox"> Управляемые (не общедоступные) Wi-Fi <br/> <input type="checkbox"> Expressroute <br/>&nbsp;&nbsp; &nbsp; (пиринг Майкрософт) ||
> | Если доступ к Microsoft 365 или Office 365 через<br/>прокси-сервер, можно ли обойти прокси-сервер? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Используется ли сейчас ExpressRoute? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Нет, но оно планируется | |
> | Вы выполнили оценку готовности сети? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Требуется ли пользователям использовать VPN при подключении к <br/>удаленные корпоративные ресурсы? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если используется VPN, можно исключить Teams трафика из <br/>VPN для напрямую Microsoft 365 и Office 365 служб? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Поддерживает ли ваша сеть качество обслуживания (QoS)? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Можно ли расставить приоритеты Teams и видеопотока <br/>чтобы повысить качество работы? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Во всех расположениях в регионе есть доступ к Интернету, <br/>или централизована ли ереси Интернета для всего региона? | <input type="checkbox"> Региональный доступ к Интернету <br/> <input type="checkbox"> Централизованный доступ к <br/>&nbsp;&nbsp; &nbsp; Интернет | |

## <a name="endpoints"></a>Конечные точки

В таблице ниже фиксироваться сведения о клиентах и конечных точках, которые используются.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие операционные системы для настольных компьютеров вы сейчас используете? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Укажите версию в столбце Комментарии.) <br/> <input type="checkbox"> Linux (укажите распределение в столбце Комментарии.) <br/><input type="checkbox"> Другое (обратите внимание на подробности в столбце Примеча ru-RU.) | |
> | Какая версия Microsoft Office развертывается <br/>на эти устройства? | <input type="checkbox">Office 2003 г. <br/> <input type="checkbox">Office 2007 г. <br/> <input type="checkbox">Office 2010 г. <br/> <input type="checkbox">Office 2013 г. <br/> <input type="checkbox">Office 2016 г. <br/> <input type="checkbox">Office для Mac 2011 г. <br/> <input type="checkbox">Office для Mac 2016 г. <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце Примеча ru-RU.) | |
> | Используемая Office развертывания <br/>в вашей организации? | <input type="checkbox"> MSI <br/> <input type="checkbox"> "нажми и нажми и запускай" | |
> | Какие мобильные устройства разрешены и поддерживаются <br/>платформы, которые используются? <br/>Выберите все, что применимо. | <input type="checkbox">Windows <br/> <input type="checkbox"> Мобильных <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце Примеча ru-RU.) | |
> | В какой форме предоставляются мобильные устройства <br/>Выберите все, что применимо. | <input type="checkbox"> Корпоративные устройства <br/> <input type="checkbox"> "Водить свое устройство" | |
> | Какие устройства в настоящее время используют пользователи для доступа <br/>службы голосовой иконференции <br/>(телефоны, гарнитуры, телефоны, видео)? | | |

## <a name="operations"></a>Операции

В таблице ниже фиксироваться аспекты работы вашей среды.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какова модель операций для Lync Server? <br/>Skype для бизнеса Server, Microsoft 365 развертывания, <br/>или Office 365 сейчас? | | |
> | Можно ли структурно обозначить текущее соглашение о поддержке для <br/>Lync Server, Skype для бизнеса Server, Microsoft 365, <br/>или Office 365? | | |
> | Если развертывание развертывается в нескольких странах или регионах, <br/>каждая страна или регион имеет собственную ИТ-телефонию <br/>с сотрудниками, с которыми вы работаете, или будет ли управление им централизованно? | <input type="checkbox"> Региональные операции и поддержка <br/> <input type="checkbox"> Централизованные операции и поддержка | |
> | Используете ли вы систему обеспечения качества связи Call Quality Methodology? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Вы написыли отдельного человека или команду <br/>Роль "Защитник качества" для платформы совместной работы <br/>используется? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Как отслеживать сервер Lync Server, Skype <br/>Business Server, Microsoft 365 развертывания или <br/>Office 365 развертывание? | | |
> | Испытываете ли вы проблемы с качеством звонков? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как и когда вы будете предоставлять учебные курсы <br/>справка по новым службам и возможностям? | | |

## <a name="adoption-and-readiness"></a>Внедрение и готовность

Укажите в следующей таблице сведения о принятии системы персоналом и готовности вашей организации к ее использованию.

>
> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каков ваш текущий активный использование <br/>Skype для бизнеса? | **__** % всех активных пользователей и включенных пользователей | |
> | Использование в организации <br/>Skype для бизнеса? | Личные беседы <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызова <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Обмена<br/> Собрания <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Конференций<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Обмена<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызова | |
> | Есть ли в вашей организации внедрение пользователей <br/>и команда управления изменениями? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как в настоящее время измерять успех технологий <br/>такие как Skype для бизнеса? | | |
> | Какой процент вашей базы пользователей, как вы думаете, имеет <br/>принято Skype для бизнеса? | | |
> | Каково мнение пользователей о Skype для бизнеса? | <input type="checkbox"> Хорошо <br/> <input type="checkbox"> Нейтральных <br/> <input type="checkbox"> Плохо | |
> | Какое из следующих лучше всего описывает разкат <br/>стратегию, используемую для Skype для бизнеса <br/>Развертывания? | <input type="checkbox"> Широкий круг: почтовая кампания с помощью <br/>&nbsp;&nbsp; &nbsp; ссылки на учебные курсы <br/> <input type="checkbox"> Расширенный: широкий спектр и разнообразные возможности <br/>&nbsp;&nbsp; &nbsp; информационных кампаний (плакаты, <br/>&nbsp;&nbsp; &nbsp; мероприятия, слева и слева) и обучение <br/>&nbsp;&nbsp; &nbsp; (видео, руководства пользователя, лицом к лицу) <br/> <input type="checkbox"> Индивидуальный: расширенный, а также целевой <br/>&nbsp;&nbsp; &nbsp; обмен сообщениями и обучение по persona <br/> <input type="checkbox"> Других <br/>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце Комментарии.) | |
