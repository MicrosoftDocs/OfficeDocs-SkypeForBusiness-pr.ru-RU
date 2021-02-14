---
title: Совместимость со среды — Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Подробные сведения о среде при планировании пути от Skype для бизнеса к Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 00173fe35d41241fb35a69f88785fa84b8bdf378
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790401"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Обнаружение среды для разных продуктов Microsoft Teams
===================================================

Обнаружение — одна из важнейших этапов, которые необходимо предпринять при планировании пути к Microsoft Teams.

Вы выполняете подробное обнаружение вашей среды, чтобы лучше понять ее текущее состояние, а также выявить сложности или (и даже далее) возможные блоки выполнения развернутого решения Teams.

## <a name="discovery-questionnaire"></a>Вопросник для анализа

В приведенном ниже примере анкеты вы можете задать несколько вопросов, чтобы подтвердить, что ваша организация готова к успешному развернутию аудиоконференций и телефонной системы с возможностями планов звонков в Teams.

Все вопросы, связанные с существующей инфраструктурой совместной работы и организацией Microsoft 365 или Office 365, сетью, конечными точками, операциями, внедрением и готовностей, включаются в анкету по обнаружению окружающей среды.

Анкета состоит из нескольких разделов, чтобы подтвердить готовность организации к развертыванию Teams в нескольких основных областях. Работайте с проектной командой, чтобы предоставить запрашиваемую информацию как можно более подробно, чтобы упростить планирование.

> [!TIP]
> Для начала скопируйте анкету в документ Microsoft Word. Постарайтесь ответить на все вопросы и получить все сведения по мере перемещения.

<a name="project-team"></a>Группа проекта
---

Запечатлейте подробные сведения о ключевых заинтересованных лицах в проекте по развернутой реализации Teams. Обратите внимание, что один человек может играть несколько ролей в проекте.

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
> | Бизнес-единицы интересов | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Сведения об организации в Microsoft 365 или Office 365
---

Настоятельно рекомендуем при работе с этим анкетой использовать активную организацию Microsoft 365 или Office 365. Если вы еще не активировали или не настроили организацию Microsoft 365 или Office 365, см. план настройки [Microsoft 365 для бизнеса.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

В таблице ниже фиксироваться информация об организации Microsoft 365 или Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Обратите внимание на производство Microsoft 365<br/>или название и ИД организации в Office 365<br/>в столбце Answer. Если у вас есть еще<br/>Несколько клиентов, связанных с<br/>в вашей организации, обратите внимание на все их ИД. | Имя клиента: <br/>ИД клиента:| |
> | В каких регионах развернуты клиенты?| | |
> | Обратите внимание на тип этих продуктов Microsoft 365 или <br/>Клиенты Office 365. Являются ли они мультитенантными <br/>или выделенный? | <input type="checkbox"> Мультитенантная<br/> <input type="checkbox"> Выделенный | |
> | Какие продукты Microsoft Online вы используете сейчас? <br/>Обратите внимание на количество пользователей, включенных для каждого из них. <br/>службу в столбце "Комментарии". | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> Skype для бизнеса <br/>&nbsp; &nbsp; &nbsp;В Интернете <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> OneDrive для бизнеса <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Другое| |
> | Какой уровень лицензии включен для Скайпа <br/>Бизнес-пользователи Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Количество пользователей <br/>для каждого SKU: |
> | Что такое текущий лес Active Directory <br/>работаете в среде? <br/>Если имеется несколько лесов, обратите внимание на подробные сведения <br/>в столбце "Прикомменты". | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | Что вы используете для каталога <br/>синхронизация сегодня? |<input type="checkbox"> Нет синхронизации (только в облаке) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Подключение <br/> <input type="checkbox"> Другое (укажите в <br/>&nbsp;&nbsp; &nbsp; Столбец "Прикомменты".)| |
> | Развернуто ли сейчас федеративное удостоверение <br/>(службы федерации Active Directory или <br/>стороне) | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если вы используете федератетное удостоверение, что такое <br/>инфраструктура федерации? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Федерация сторонних сторон <br/>&nbsp;&nbsp; &nbsp; шлюз (обратите внимание на подробные сведения) <br/>&nbsp;&nbsp; &nbsp; в столбце "Прикомменты".) | |
> | Если вы ведете активную учетную запись Microsoft 365<br/>или клиент Office 365— домен SMTP/SIP <br/>ваши целевые пользователи, связанные с клиентом? | <input type="checkbox"> Н/П — нет Microsoft 365 или<br/>&nbsp;&nbsp; &nbsp; Клиент Office 365 на месте <br/> <input type="checkbox"> Нет, SMTP/SIP пользователей <br/>&nbsp;&nbsp; &nbsp; домен не связан <br/>&nbsp;&nbsp; &nbsp; с любыми клиентами в <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365<br/> <input type="checkbox"> Да, SMTP/SIP пользователей <br/>&nbsp;&nbsp; &nbsp; домен связан <br/>&nbsp;&nbsp; &nbsp; с существующим клиентом в <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365 | |
> | Соответствуют ли имя пользователя основному SMTP-адресу? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Несогласованное | |

<a name="existing-collaboration-platform-summary"></a>Существующая сводка платформы совместной работы
---

В таблице ниже фиксироваться сведения о существующем развертывании платформы для совместной работы.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Развернута ли система Microsoft Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернута ли система Skype для бизнеса? <br/>Для локального и гибридного развертывания убедитесь, что <br/>Обратите внимание на версию и накопительный итог обновления <br/>в столбце "Комментарии". | <input type="checkbox"> Да, Microsoft 365 или <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Да, hosted, dedicated <br/>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Да, hosted, shared <br/>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли система Microsoft Exchange? <br/>Для локального и гибридного развертывания убедитесь, что <br/>Сведения о версии и подсказке заметок в комментариях <br/>. | <input type="checkbox"> Да, Microsoft 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Да, hosted, dedicated <br/>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Да, hosted, shared <br/>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли система SharePoint? <br/>Для локального и гибридного развертывания убедитесь, что <br/>Сведения о версии и подсказке заметок в комментариях <br/>. | <input type="checkbox"> Да, Microsoft 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Да, hosted, dedicated <br/>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Да, hosted, shared <br/>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Нет, другое | |
> | Развертывается ли OneDrive для бизнеса? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернуты ли у вас другие сторонние платформы? <br/>и используется уже сегодня? В этом случае обратите внимание на количество пользователей <br/>эти платформы и сведения об использовании в <br/>Столбец "Прикомменты". | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Резерв резерва <br/> <input type="checkbox"> Другое (укажите в <br/>&nbsp;&nbsp; &nbsp; Столбец "Прикомменты".) | Количество пользователей: <br/>Подробности:|
> | Вы планируете переместить пользователей из этой стороной <br/>платформы для Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Что такое текущее решение для телефонии и conferencing <br/>из пользователей, которые находятся в области действия этой инициативы? | | |
> | Развернуты ли [У вас службы SBC, поддерживают прямую маршрутику](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) <br/>для ваших офисов, которые находятся в области действия этой инициативы? Если да,<br/>обратите внимание на сведения в столбце "Комментарии".| <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||

<a name="collaboration-platform-deployment-details"></a>Сведения о развертывании платформы для совместной работы
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (при наличии)

Если применимо, зафиксировать сведения о развертывании Teams можно с помощью примера таблицы ниже. Если вы еще не развернули Teams, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каким группам пользователей доступна система Teams? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Определенные пользователи и группы пользователей <br/>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Прикомменты".) ||
> | Какие функции и модали Teams используются? | <input type="checkbox"> Беседы на основе каналов <br/> <input type="checkbox"> Приватный чат <br/> <input type="checkbox"> Гостевой доступ <br/> <input type="checkbox"> Собрания канала <br/> <input type="checkbox"> Частные собрания <br/> <input type="checkbox"> Частные вызовы <br/> <input type="checkbox"> Ad-hoc channel meetup <br/> <input type="checkbox"> Видео на собраниях <br/> <input type="checkbox"> Совместный доступ к экрану на собраниях <br/> <input type="checkbox"> Аудиоконференция <br/><input type="checkbox"> Приложения (приложения)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Вкладки<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Боты <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Соединитетели<br/><input type="checkbox"> Интеграция пользовательского облачного хранилища <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Диск, Egnyte <br/> <input type="checkbox"> Интеграция с электронной почтой каналов <br/> <input type="checkbox"> Другое (укажите в столбце "Прикомменты").) | |
> | Какие приложения вы развернули в Teams? | | |
> | Блокировали ли вы какие-то конкретные возможности Teams? <br/>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Какие используются клиенты Teams? | <input type="checkbox"> Интернет <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Кому разрешено создавать команды? | <input type="checkbox"> Все в организации <br/>&nbsp;&nbsp; &nbsp; (Этот параметр заданной по умолчанию) <br/> <input type="checkbox"> Определенные люди <br/>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Прикомменты".) | |
> | Используете ли вы в Teams функции обеспечения безопасности и соответствия требованиям? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-online-if-applicable"></a>Skype для бизнеса Online (при наличии)

Если применимо, зафиксировать сведения о развертывании Skype для бизнеса Online можно с помощью приведенной ниже таблицы. Если вы не развернули skype для бизнеса Online, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Типы пользователей, которые включены для Скайпа <br/>для бизнеса Online? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Определенные пользователи и группы пользователей <br/>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Прикомменты".) | |
> | Какие модалисти и функции сейчас <br/>используется уже сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (мгновенные сообщения/p)<br/> <input type="checkbox"> Conferencing <br/> <input type="checkbox"> Федерация <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Аудиоконференция Майкрософт <br/> <input type="checkbox"> Аудиоконференция со сторонними аудиоконференниями (примечание)<br/>&nbsp;&nbsp; &nbsp; сведения в столбце "Комментарии".) <br/> <input type="checkbox"> Планы звонков (ранее — вызовы через ПС) <br/> <input type="checkbox"> Автоотправления организации <br/> <input type="checkbox"> Очереди вызовов | |
> | Вы специально заблокировали Скайп для <br/>Возможности Business Online? <br/>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какой метод вы используете или планируете использовать? <br/>подключить телефонную систему (ранее — облачную УАСК) к <br/>через ПС? <br/>Выберите все, что применимо. | <input type="checkbox"> Планы звонков (ранее — вызовы через ПС) <br/> <input type="checkbox"> Локальное подключение к ДНР <br/>&nbsp;&nbsp; &nbsp; (использование существующего Skype для <br/>&nbsp;&nbsp; &nbsp; Business 2015 или Lync Server <br/>&nbsp;&nbsp; &nbsp; Развертывание 2013) <br/> <input type="checkbox"> Локальное подключение к ДНР <br/>&nbsp;&nbsp; &nbsp; (с помощью Cloud Connector) | |
> | Есть ли у вас телефонные номера, перенесенные в Майкрософт <br/>Это относится к планам звонков и звуку <br/>Функции для конференций. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Локальное приложение Skype для бизнеса (если применимо)

Если применимо, зафиксировать сведения о развертывании Skype для бизнеса можно с помощью приведенной ниже таблицы. Если вы не развернули локально Skype для бизнеса, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие версии Lync или Skype для бизнеса <br/> развертываются локально? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype для бизнеса Server 2015 <br/> <input type="checkbox"> Skype для бизнеса Server 2019 <br/><input type="checkbox"> Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edition | |
> | Настроено ли гибридное подключение со Skype для бизнеса Online? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Эта среда, которая находится и управляется третьей <br/>стороной? Если да, обратите внимание на сведения в <br/>Столбец "Прикомменты". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какие модалии и функции используются в настоящее время? <br/>сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (мгновенные сообщения/p) <br/> <input type="checkbox"> Conferencing <br/> <input type="checkbox"> Федерация <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Сохраняемая беседа или групповой чат <br/> <input type="checkbox"> Аудиоконференция Майкрософт <br/>&nbsp;&nbsp; &nbsp; (ранее "Телефонная" на телефонной телефонии) на <br/>&nbsp;&nbsp; &nbsp; локального сервера Lync Server или <br/>&nbsp;&nbsp; &nbsp; Развертывание Skype для бизнеса <br/> <input type="checkbox"> Аудиоконференция со сторонними <br/>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в примечастях. <br/>&nbsp;&nbsp; &nbsp; .) <br/> <input type="checkbox"> Корпоративная голосовая связь локальной <br/>&nbsp; &nbsp; &nbsp;Связь с ТСОП <br/> <input type="checkbox"> Планы звонков (ранее — вызовы через ПС) через <br/>&nbsp;&nbsp; &nbsp; Гибридное общение со Skype для бизнеса Online | |
> | Какие у вас развернуты версии пограничного сервера? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype для бизнеса Server 2015 <br/> <input type="checkbox"> Skype для бизнеса Server 2019| |
> | У вас есть Lync или Skype для бизнеса Edge <br/>развернуты в несколько центра обработки данных? <br/>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Выберите службы, которые предоставляет ваша роль Edge сегодня. | <input type="checkbox"> Доступ внешних пользователей (корпоративных пользователей) <br/> <input type="checkbox"> Удаленный доступ пользователей (анонимный) <br/>&nbsp;&nbsp; &nbsp; внешние участники собрания) <br/> <input type="checkbox"> Федерация <br/> <input type="checkbox"> Ретранслятор мультимедиа | |
> | Какие из следующих функций голосовых звонков вам <br/>есть зависимости? <br/>Обратите внимание на дополнительные зависимости в примечаниях <br/>. | <input type="checkbox"> Параметры занятости <br/> <input type="checkbox"> Call park <br/> <input type="checkbox"> "Приозвать звонок" или "групповой звонок" <br/> <input type="checkbox"> Обычные телефоны с зонами или "службы hot desking" <br/> <input type="checkbox"> Группы ответа или группы по поиску ответов <br/> <input type="checkbox"> Вид общей строки <br/> <input type="checkbox"> Частная строка <br/> <input type="checkbox"> Голосовая почта <br/> <input type="checkbox"> Звонок с помощью работы <br/> <input type="checkbox"> Номера для экстренного помощи или сведения <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Набор расширений <br/> <input type="checkbox"> автосекретарь <br/> <input type="checkbox"> Абонентский доступ <br/> <input type="checkbox"> Аналоговые устройства <br/> <input type="checkbox"> Факс <br/> <input type="checkbox"> Маскировка или изменение ИД звоня <br/> <input type="checkbox"> Маршруты с учетом расположения <br/> <input type="checkbox"> Маршрутная маршрутка с наименьшими затратами <br/> <input type="checkbox"> Телефоны с телефонами- телефонами с | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Сеть и доступ к службам Microsoft 365 и Office 365
---

В таблице ниже фиксироваться сетевой контакт организации и то, как ваши пользователи (или будут) подключены к службам Microsoft 365 и Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Действия пользователей в области миграции <br/>Получать доступ к Teams, когда они в офисе? <br/>Выберите все, что применимо. | <input type="checkbox"> Маршрутное подключение NAT <br/> <input type="checkbox"> Прокси-сервер <br/> <input type="checkbox"> Общедоступные Wi-Fi <br/> <input type="checkbox"> Управляемые (не общедоступные) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (пиринг Майкрософт) ||
> | Если доступ к Microsoft 365 или Office 365 через<br/>прокси-сервер. Можно ли обойти прокси-сервер? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Используется ли сейчас ExpressRoute? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Нет, но он планируется | |
> | Вы выполнили оценку готовности к сети? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Требуется ли пользователям использовать VPN при подключении к <br/>корпоративные ресурсы удаленно? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если используется VPN, можно ли исключить трафик Teams из <br/>VPN для прямого доступа к Microsoft 365 и службам Office 365? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Поддерживает ли ваша сеть качество обслуживания (QoS)? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Приоритет аудио- и видеопотока в Teams <br/>чтобы повысить качество работы? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | "Во всех расположениях в регионе есть доступ в Интернет", <br/>или централизована ли регрессия в Интернете по всему региону? | <input type="checkbox"> Региональный доступ к Интернету <br/> <input type="checkbox"> Централизованный доступ к <br/>&nbsp;&nbsp; &nbsp; Интернет | |

<a name="endpoints"></a>Конечные точки
---

В таблице ниже фиксироваться сведения о клиентах и конечных точках, которые используются.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие операционные системы для настольных компьютеров вы сейчас используете? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac (укажите версию в столбце "Комментарии").) <br/> <input type="checkbox"> Linux (укажите распределение в столбце Comments.) <br/><input type="checkbox"> Другое (обратите внимание на подробности в столбце "Комментарии".) | |
> | Какая версия Microsoft Office развертывается <br/>на эти устройства? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office для Mac 2011 <br/> <input type="checkbox"> Office для Mac 2016 <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце "Комментарии".) | |
> | Используемая технология развертывания Office <br/>в своей организации? | <input type="checkbox"> MSI <br/> <input type="checkbox"> "нажми и нажми ижми и вожми" | |
> | Какие мобильные устройства разрешены и поддерживаются <br/>используются ли платформы? <br/>Выберите все, что применимо. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Мобильные устройства <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце "Комментарии".) | |
> | В какой форме предоставляются мобильные устройства <br/>Выберите все, что применимо. | <input type="checkbox"> Корпоративные устройства <br/> <input type="checkbox"> Возьмите свое устройство | |
> | Какие устройства в настоящее время используют пользователи для доступа <br/>службы голосовой и видеоконференции <br/>(наушники, телефоны, видео)? | | |

<a name="operations"></a>Операции
---

В таблице ниже фиксироваться аспекты работы вашей среды.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Что такое модель операций для вашего сервера Lync Server? <br/>Skype для бизнеса Server, развертывание Microsoft 365, <br/>или развертывание Office 365 уже сегодня? | | |
> | Можете ли вы структурой текущего плана поддержки для <br/>Lync Server, Skype для бизнеса Server, Microsoft 365, <br/>или Office 365? | | |
> | Если развертывание развертывается в нескольких странах или регионах, <br/>каждая страна или регион имеют собственные ИТ-/телефонию <br/>сотрудников для работы или централизованное управление этим вопросом | <input type="checkbox"> Региональные операции и поддержка <br/> <input type="checkbox"> Централизованные операции и поддержка | |
> | Используете ли вы систему обеспечения качества связи Call Quality Methodology? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Назначены ли вам отдельные или группы <br/>Роль Quality Champion для платформы совместной работы <br/>используется? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Как следить за сервером Lync Server, Skype для <br/>Business Server, развертывание Microsoft 365 или <br/>Развертывание Office 365 | | |
> | Испытываете ли вы проблемы с качеством звонков? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как и когда вы предоставляете учебные курсы <br/>helpdesk on new services and capabilities? | | |

<a name="adoption-and-readiness"></a>Внедрение и готовность
---

Укажите в следующей таблице сведения о принятии системы персоналом и готовности вашей организации к ее использованию.

>
> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каков ваш текущий активный использование <br/>Skype для бизнеса? | **__** % всех активных пользователей в сравнении с включенными пользователями | |
> | Как ваша организация использует <br/>Skype для бизнеса? | Личные беседы <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Мгновенные мгновенные мгновенны <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызовы <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Общий доступ<br/> Собрания <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferencing<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Общий доступ<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызовы | |
> | Имеет ли ваша организация внедрение пользователей <br/>и команда управления изменениями? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как в настоящий момент измерять успех технологий <br/>Что делать, например Skype для бизнеса? | | |
> | Какой процент базы пользователей вы бы сказали, имеет <br/>Принято в Skype для бизнеса? | | |
> | Каково мнение пользователей о Skype для бизнеса? | <input type="checkbox"> Хорошо <br/> <input type="checkbox"> Нейтральный <br/> <input type="checkbox"> Плохо | |
> | Что из следующего лучше всего описывает этот вариант. <br/>стратегии, используемой для Skype для бизнеса <br/>развертывание? | <input type="checkbox"> Широкий выбор: почтовая кампания с <br/>&nbsp;&nbsp; &nbsp; ссылки на учебные курсы <br/> <input type="checkbox"> Expanded: Broad reach plus a variety <br/>&nbsp;&nbsp; &nbsp; информационных кампаний (плакаты, <br/>&nbsp;&nbsp; &nbsp; мероприятия, президенты и обучение; <br/>&nbsp;&nbsp; &nbsp; (видео, руководства пользователя, лицом к лицу) <br/> <input type="checkbox"> Tailored: Expanded, plus targeted <br/>&nbsp;&nbsp; &nbsp; обмен сообщениями и обучение по persona <br/> <input type="checkbox"> Другое <br/>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце "Комментарии".) | |
