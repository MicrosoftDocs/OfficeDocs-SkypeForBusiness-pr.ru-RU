---
title: Совместимость среды — Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Как выполнить подробное обнаружение окружающей среды при планировании перехода от Skype для бизнеса к Microsoft Teams.
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
ms.openlocfilehash: 348a0e615f5ef876bfdd62b71adb30f6bf242dd6
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562608"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Обнаружение окружающей среды для развертывания Microsoft Teams

Обнаружение — это один из первых ключевых шагов, которые необходимо выполнить при планировании перехода на Microsoft Teams.

Вы выполняете подробное обнаружение среды, чтобы лучше понять ее текущее состояние и выявить любые сложности или ( еще больше) возможные блоки выполнения развертывания Teams.

## <a name="discovery-questionnaire"></a>Анкета обнаружения

В приведенном ниже примере анкеты приводится набор вопросов, которые помогут убедиться, что ваша организация готова к успешному развертыванию аудиоконференций и телефонной системы с возможностями планов звонков в Teams.

Все вопросы, связанные с существующей инфраструктурой совместной работы и Организацией Microsoft 365 или Office 365, сетью, конечными точками, операциями, внедрением и готовностью, включаются в анкету по обнаружению окружающей среды.

Анкета разделена на несколько разделов, чтобы подтвердить готовность вашей организации к развертыванию Teams в нескольких основных областях. Обратитесь к проектной группе, чтобы предоставить запрашиваемую информацию как можно более подробно, чтобы упростить планирование.

> [!TIP]
> Для начала можно скопировать анкету в документ Microsoft Word. Попробуйте ответить на все вопросы и записать все сведения по мере перехода.

### <a name="project-team"></a>Команда project

Запишите подробные сведения о ключевых заинтересованных лицах проекта развертывания Teams. Обратите внимание, что один человек может играть несколько ролей в проекте.

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
> | Потенциальные клиенты бизнес-подразделений | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Сведения о microsoft 365 или Office 365 организации

Мы настоятельно рекомендуем иметь активную организацию Microsoft 365 или Office 365 по мере работы с этой анкетой. Если вы еще не активировали или не настроите Microsoft 365 или Office 365 организации, см. статью "Планирование настройки [Microsoft 365 для бизнеса"](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Используйте следующую таблицу для сбора сведений о Microsoft 365 или Office 365 организации.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Обратите внимание на рабочую среду Microsoft 365<br/>или Office 365 организации и идентификатор<br/>в столбце "Ответ". Если у вас есть еще<br/>несколько клиентов, связанных с<br/>Запишите все идентификаторы в вашей организации. | Имя клиента: <br/>Идентификатор клиента:| |
> | В каких регионах развернуты клиенты?| | |
> | Обратите внимание на тип этих microsoft 365 или <br/>Office 365 клиентов. Являются ли они мультитенантным <br/>Или выделено? | <input type="checkbox"> Многопользовательского<br/> <input type="checkbox"> Выделенный | |
> | Какие продукты Microsoft Online вы используете сейчас? <br/>Обратите внимание на количество пользователей, включенных для каждого <br/>в столбце "Комментарии". | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype для бизнеса <br/>&nbsp; &nbsp; &nbsp;В Интернете <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive для бизнеса <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Других| |
> | Какой уровень лицензии включен для Skype <br/>Пользователи Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Число пользователей <br/>для каждого номера SKU: |
> | Что такое текущий лес Active Directory? <br/>функциональный уровень в среде? <br/>Если имеется несколько лесов, обратите внимание на подробные сведения. <br/>в столбце "Примечания". | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Что вы используете для каталога? <br/>синхронизация сегодня? |<input type="checkbox"> Без синхронизации (только в облаке) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Подключения <br/> <input type="checkbox"> Другое (укажите в <br/>&nbsp;&nbsp; &nbsp; Столбец комментариев.)| |
> | Развернуто ли сейчас федеративное удостоверение <br/>(службы федерации Active Directory (AD FS) или <br/>сторонние поставщики) | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если вы используете федеративное удостоверение, что такое <br/>инфраструктура федерации? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Сторонняя федерация <br/>&nbsp;&nbsp; &nbsp;шлюз (обратите внимание на подробные сведения <br/>&nbsp;&nbsp; &nbsp;в столбце Comments.) | |
> | Если вы в настоящее время поддерживаете активную службу Microsoft 365<br/>или Office 365 клиента— это домен SMTP/SIP <br/>ваши целевые пользователи, связанные с клиентом? | <input type="checkbox"> Н/А — нет Microsoft 365 или<br/>&nbsp;&nbsp; &nbsp;Office 365 клиента на месте <br/> <input type="checkbox"> Нет, SMTP/SIP пользователей <br/>&nbsp;&nbsp; &nbsp;домен не связан <br/>&nbsp;&nbsp; &nbsp;с любыми клиентами в <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365<br/> <input type="checkbox"> Да, SMTP/SIP пользователей <br/>&nbsp;&nbsp; &nbsp;домен связан <br/>&nbsp;&nbsp; &nbsp;с существующим клиентом в <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365 | |
> | Совпадают ли имена пользователей с основным SMTP-адресом? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Непоследовательно | |

## <a name="existing-collaboration-platform-summary"></a>Сводка по существующей платформе совместной работы

Используйте следующую таблицу для сбора сведений о существующем развертывании платформы совместной работы.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Развернута ли система Microsoft Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернута ли система Skype для бизнеса? <br/>Для локальных и гибридных развертываний убедитесь, что <br/>Обратите внимание на версию и накопительный пакет обновления (CU). <br/>сведения в столбце "Примечания". | <input type="checkbox"> Да, Microsoft 365 или <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Да, в локальной среде <br/> <input type="checkbox"> Да, в сети, выделено <br/>&nbsp;&nbsp; &nbsp;(Майкрософт) <br/> <input type="checkbox"> Да, размещено, выделено <br/>&nbsp;&nbsp; &nbsp;(сторонние поставщики) <br/> <input type="checkbox"> Да, размещено, с общим доступом <br/>&nbsp;&nbsp; &nbsp;(сторонние поставщики) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли система Microsoft Exchange? <br/>Для локальных и гибридных развертываний убедитесь, что <br/>Сведения о версии и накопительных пакетах обновления запишите в примечаниях. <br/>Столбца. | <input type="checkbox"> Да, Microsoft 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Да, в локальной среде <br/> <input type="checkbox"> Да, в сети, выделено <br/>&nbsp;&nbsp; &nbsp;(Майкрософт) <br/> <input type="checkbox"> Да, размещено, выделено <br/>&nbsp;&nbsp; &nbsp;(сторонние поставщики) <br/> <input type="checkbox"> Да, размещено, с общим доступом <br/>&nbsp;&nbsp; &nbsp;(сторонние поставщики) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли система SharePoint? <br/>Для локальных и гибридных развертываний убедитесь, что <br/>Сведения о версии и накопительных пакетах обновления запишите в примечаниях. <br/>Столбца. | <input type="checkbox"> Да, Microsoft 365 <br/> <input type="checkbox"> Да, гибридная (с <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 или <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Да, в локальной среде <br/> <input type="checkbox"> Да, в сети, выделено <br/>&nbsp;&nbsp; &nbsp;(Майкрософт) <br/> <input type="checkbox"> Да, размещено, выделено <br/>&nbsp;&nbsp; &nbsp;(сторонние поставщики) <br/> <input type="checkbox"> Да, размещено, с общим доступом <br/>&nbsp;&nbsp; &nbsp;(сторонние поставщики) <br/> <input type="checkbox"> Нет, другое | |
> | Развертывается OneDrive для бизнеса развертывания? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернуты ли другие сторонние платформы? <br/>и используются сегодня? Если да, обратите внимание на количество пользователей <br/>эти платформы и сведения об использовании в <br/>Столбец комментариев. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> Слабину <br/> <input type="checkbox"> Другое (укажите в <br/>&nbsp;&nbsp; &nbsp; Столбец комментариев.) | Количество пользователей: <br/>Детали:|
> | Вы планируете переместить пользователей из этих сторонних поставщиков <br/>платформы в Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Что такое текущее решение для телефонии и конференц-связи? <br/>из пользователей, которые находятся в области действия для этой инициативы? | | |
> | Поддерживают ли [вы SBC, поддерживающие прямую маршрутизацию](./direct-routing-plan.md#supported-session-border-controllers-sbcs) ? <br/>Для ваших офисов, которые находятся в области действия этой инициативы? Если да,<br/>Обратите внимание на подробные сведения в столбце "Примечания".| <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||

## <a name="collaboration-platform-deployment-details"></a>Сведения о развертывании платформы совместной работы

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (при наличии)

Если применимо, запишите сведения о развертывании Teams с помощью приведенной ниже примера таблицы. Если вы еще не развернули Teams, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каким группам пользователей доступна система Teams? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Конкретные пользователи и группы пользователей <br/>&nbsp;&nbsp; &nbsp;(Укажите в столбце "Примечания".) ||
> | Какие функции и модальности Teams используются? | <input type="checkbox"> Беседы на основе каналов <br/> <input type="checkbox"> Частный чат <br/> <input type="checkbox"> Гостевой доступ <br/> <input type="checkbox"> Собрания канала <br/> <input type="checkbox"> Частные собрания <br/> <input type="checkbox"> Частные вызовы <br/> <input type="checkbox"> Ad-hoc channel meetup <br/> <input type="checkbox"> Видео на собраниях <br/> <input type="checkbox"> Демонстрация экрана на собраниях <br/> <input type="checkbox"> Аудиоконференций <br/><input type="checkbox"> Приложения (приложения)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Вкладки<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Ботов <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Соединители<br/><input type="checkbox"> Интеграция пользовательского облачного хранилища <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Диск, Egnyte <br/> <input type="checkbox"> Интеграция с электронной почтой канала <br/> <input type="checkbox"> Другое (укажите в столбце "Примечания").) | |
> | Какие приложения вы развернули в Teams? | | |
> | Блокировали ли вы какие-то конкретные возможности Teams? <br/>Если да, запишите сведения в столбце "Комментарии". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Какие используются клиенты Teams? | <input type="checkbox"> Веб <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Кому разрешено создавать команды? | <input type="checkbox"> Все сотрудники организации <br/>&nbsp;&nbsp; &nbsp;(Это параметр по умолчанию) <br/> <input type="checkbox"> Конкретные пользователи <br/>&nbsp;&nbsp; &nbsp;(Укажите в столбце "Примечания".) | |
> | Используете ли вы в Teams функции обеспечения безопасности и соответствия требованиям? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-online-if-applicable"></a>Skype для бизнеса Online (при наличии)

Если применимо, запишите сведения о развертывании Skype для бизнеса Online с помощью приведенной ниже примера таблицы. Если вы еще не развернули Skype для бизнеса Online, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие типы пользователей включены для Skype <br/>для Business Online? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Конкретные пользователи и группы пользователей <br/>&nbsp;&nbsp; &nbsp;(Укажите в столбце "Примечания".) | |
> | Какие модификаторы и функции в настоящее время доступны <br/>используется сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (im/P)<br/> <input type="checkbox"> Конференций <br/> <input type="checkbox"> Федерации <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Аудиоконференции Майкрософт <br/> <input type="checkbox"> Аудиоконференции сторонних производителей (примечание)<br/>&nbsp;&nbsp; &nbsp;сведения в столбце "Примечания".) <br/> <input type="checkbox"> Планы звонков (ранее — вызовы ТСОП) <br/> <input type="checkbox"> Автосекретари организации <br/> <input type="checkbox"> Очереди вызовов | |
> | Вы специально заблокируют любой Skype для <br/>Возможности Business Online? <br/>Если да, запишите сведения в столбце "Комментарии". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какой метод вы используете или планируете использовать для <br/>подключить телефонную систему (ранее облачную УАТС) к <br/>ТСОП? <br/>Выберите все, что применимо. | <input type="checkbox"> Планы звонков (ранее — вызовы ТСОП) <br/> <input type="checkbox"> Локальное подключение к ТСОП <br/>&nbsp;&nbsp; &nbsp;(использование существующего Skype для <br/>&nbsp;&nbsp; &nbsp; Business 2015 или Lync Server <br/>&nbsp;&nbsp; &nbsp;Развертывание в 2013 г.) <br/> <input type="checkbox"> Локальное подключение к ТСОП <br/>&nbsp;&nbsp; &nbsp;(с помощью Cloud Connector) | |
> | Есть ли у вас телефонные номера, перенесенные в Майкрософт <br/>Это применимо к тарифным планам и аудио <br/>Функции конференц-связи. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype для бизнеса локально (если применимо)

Если применимо, запишите сведения о развертывании Skype для бизнеса с помощью приведенной ниже примера таблицы. Если вы еще не развернули Skype для бизнеса локально, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие версии Lync или Skype для бизнеса <br/> в настоящее время развертываются локально? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype для бизнеса Server 2015 г. <br/> <input type="checkbox">Skype для бизнеса Server 2019 г. <br/><input type="checkbox">Skype для бизнеса Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Издание | |
> | Настроено ли гибридное подключение со Skype для бизнеса Online? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Размещается ли эта среда и управляется ли она третьей средой? <br/>Партии? Если да, запишите сведения в <br/>Столбец комментариев. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какие модиалы и функции используются в настоящее время <br/>Сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (im/P) <br/> <input type="checkbox"> Конференций <br/> <input type="checkbox"> Федерации <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Сохраняемый чат или групповой чат <br/> <input type="checkbox"> Аудиоконференции Майкрософт <br/>&nbsp;&nbsp; &nbsp;(прежнее название — Dial in Conferencing) на устройстве <br/>&nbsp;&nbsp; &nbsp;локальный сервер Lync Server или <br/>&nbsp;&nbsp; &nbsp;Skype для бизнеса развертывания <br/> <input type="checkbox"> Аудиоконференции сторонних производителей <br/>&nbsp;&nbsp; &nbsp;(Обратите внимание на подробные сведения в примечаниях <br/>&nbsp;&nbsp; &nbsp;столбец.) <br/> <input type="checkbox">Корпоративная голосовая связь с использованием локальной среды <br/>&nbsp; &nbsp; &nbsp;Связь с ТСОП <br/> <input type="checkbox"> Планы звонков (ранее — вызовы ТСОП) через <br/>&nbsp;&nbsp; &nbsp; Гибридное использование Skype для бизнеса Online | |
> | Какие у вас развернуты версии пограничного сервера? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype для бизнеса Server 2015 г. <br/> <input type="checkbox">Skype для бизнеса Server 2019 г.| |
> | У вас есть Lync или Skype для бизнеса Edge <br/>развернуты в нескольких центрах обработки данных? <br/>Если да, запишите сведения в столбце "Комментарии". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Выберите службы, которые предоставляет ваша роль Edge. | <input type="checkbox"> Доступ внешних пользователей (корпоративных пользователей) <br/> <input type="checkbox"> Удаленный доступ пользователей (анонимный) <br/>&nbsp;&nbsp; &nbsp;внешние участники собрания) <br/> <input type="checkbox"> Федерации <br/> <input type="checkbox"> Ретранслятор мультимедиа | |
> | Какие из следующих функций голосовых вызовов вы выполняете <br/>в настоящее время имеются зависимости от? <br/>Обратите внимание на дополнительные зависимости в примечаниях <br/>Столбца. | <input type="checkbox"> Параметры занятости <br/> <input type="checkbox"> Парковка вызовов <br/> <input type="checkbox"> Отправка звонка или групповой звонок <br/> <input type="checkbox"> Телефоны общего пользования или "горячее обслуживание" <br/> <input type="checkbox"> Группы ответа или группы поиска <br/> <input type="checkbox"> Внешний вид общей строки <br/> <input type="checkbox"> Частная линия <br/> <input type="checkbox"> Голосовую почту <br/> <input type="checkbox"> Звонок с помощью работы <br/> <input type="checkbox"> Номера экстренных служб или информационных номеров <br/>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Набор расширений <br/> <input type="checkbox"> Автосекретаря <br/> <input type="checkbox"> Доступ подписчика <br/> <input type="checkbox"> Аналоговые устройства <br/> <input type="checkbox"> Факс <br/> <input type="checkbox"> Маскирование или изменение идентификатора вызывающего абонента <br/> <input type="checkbox"> Маршрутизация на основе расположения <br/> <input type="checkbox"> Наименее затратная маршрутизация <br/> <input type="checkbox"> Телефоны для лифтов | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Сеть и доступ к службам Microsoft 365 и Office 365

Используйте следующую таблицу, чтобы получить сведения о сети вашей организации и способе подключения пользователей к Microsoft 365 и Office 365 служб.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Как (или как) будут выполняться действия пользователей в области миграции <br/>Получить доступ к Teams, когда они находятся в офисе? <br/>Выберите все, что применимо. | <input type="checkbox"> Перенаправленное подключение NAT <br/> <input type="checkbox"> Прокси-сервер <br/> <input type="checkbox"> Общедоступные Wi-Fi <br/> <input type="checkbox"> Управляемые (не общедоступные) Wi-Fi <br/> <input type="checkbox"> Expressroute <br/>&nbsp;&nbsp; &nbsp;(Пиринг Майкрософт) ||
> | Если доступ к Microsoft 365 или Office 365 через<br/>Прокси-сервер, есть ли способ обойти прокси-сервер? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Используется ли сейчас ExpressRoute? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Нет, но оно планируется | |
> | Вы выполнили оценку готовности сети? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Требуется ли пользователям использовать VPN при подключении к <br/>корпоративные ресурсы удаленно? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если используется VPN, можно ли исключить трафик Teams из <br/>VPN для прямого доступа к Microsoft 365 и Office 365 Services? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Поддерживает ли ваша сеть качество обслуживания (QoS)? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Можно ли определить приоритеты аудио- и видеопотока Teams <br/>Чтобы обеспечить высокое качество работы? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | У всех расположений в регионе есть исходящий трафик Из Интернета. <br/>или интернет-исходящий трафик централизован для всего региона? | <input type="checkbox"> Региональный доступ к Интернету <br/> <input type="checkbox"> Централизованный доступ к <br/>&nbsp;&nbsp; &nbsp;Интернет | |

## <a name="endpoints"></a>Конечные точки

Используйте следующую таблицу для сбора сведений об используемом клиенте и конечных точках.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие операционные системы для настольных компьютеров вы сейчас используете? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (укажите версию в столбце "Примечания"). <br/> <input type="checkbox"> Linux (укажите дистрибутив в столбце Comments).) <br/><input type="checkbox"> Другое (обратите внимание на сведения в столбце Comments.) | |
> | Какая версия Microsoft Office развернута <br/>на эти устройства? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office для Mac 2011 г. <br/> <input type="checkbox">Office для Mac 2016 г. <br/> <input type="checkbox"> Другое (обратите внимание на сведения в столбце Comments.) | |
> | Какая технология развертывания Office используется <br/>в вашей организации? | <input type="checkbox"> MSI <br/> <input type="checkbox"> "Нажми и запускай" | |
> | Что такое разрешенные и поддерживаемые мобильные устройства <br/>Используются ли платформы? <br/>Выберите все, что применимо. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Мобильных <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Другое (обратите внимание на сведения в столбце Comments.) | |
> | В какой форме предоставляются мобильные устройства <br/>Выберите все, что применимо. | <input type="checkbox"> Корпоративные устройства <br/> <input type="checkbox"> Использование собственного устройства | |
> | Какие устройства пользователи в настоящее время используют для доступа <br/>голосовые службы и службы конференц-связи <br/>(наборы телефонов, гарнитуры, видео)? | | |

## <a name="operations"></a>Операции

Используйте следующую таблицу, чтобы получить подробные сведения об операционных аспектах среды.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какая у вас модель операций для Lync Server? <br/>Skype для бизнеса Server, развертывание Microsoft 365, <br/>или Office 365 развертывание сегодня? | | |
> | Можно ли указать текущее соглашение о поддержке для <br/>Lync Server, Skype для бизнеса Server, Microsoft 365, <br/>или Office 365? | | |
> | Если развертывание выполняется в нескольких странах или регионах, <br/>имеет ли каждая страна или регион собственную ИТ/телефонию. <br/>с сотрудниками, с которыми необходимо работать, или управление этим решением будет выполняться централизованно? | <input type="checkbox"> Региональные операции и поддержка <br/> <input type="checkbox"> Централизованные операции и поддержка | |
> | Используете ли вы систему обеспечения качества связи Call Quality Methodology? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Назначено ли пользователю или команде <br/>Роль "Лидеров качества" для платформы совместной работы <br/>используется? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Как отслеживать сервер Lync Server, Skype для <br/>Business Server, развертывание Microsoft 365 или <br/>Office 365 развертывания? | | |
> | Испытываете ли вы проблемы с качеством звонков? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как и когда вы предоставляете обучение <br/>служба технической поддержки по новым службам и возможностям? | | |

## <a name="adoption-and-readiness"></a>Внедрение и готовность

Укажите в следующей таблице сведения о принятии системы персоналом и готовности вашей организации к ее использованию.

>
> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каков текущий активный режим использования <br/>Skype для бизнеса? | **__** % от общего числа активных и включенных пользователей | |
> | Как ваша организация использует <br/>Skype для бизнеса? | Личные беседы <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызова <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Обмена<br/> Собрания <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Конференций<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Обмена<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызова | |
> | Есть ли в вашей организации внедрение пользователей <br/>и команда по управлению изменениями? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как в настоящее время измерить успешность технологии <br/>развертывание, например Skype для бизнеса? | | |
> | Какой процент пользовательской базы, как вы скажем, имеет <br/>принято ли Skype для бизнеса? | | |
> | Каково мнение пользователей о Skype для бизнеса? | <input type="checkbox"> Хорошо <br/> <input type="checkbox"> Нейтральных <br/> <input type="checkbox"> Плохо | |
> | Что из следующего лучше всего описывает развертывание <br/>стратегия, используемая для Skype для бизнеса <br/>Развертывания? | <input type="checkbox"> Широкий охват: электронная почтовая кампания с помощью <br/>&nbsp;&nbsp; &nbsp;ссылки на учебные материалы <br/> <input type="checkbox"> Развернуто: широкий охват плюс разнообразные <br/>&nbsp;&nbsp; &nbsp;информационных кампаний (плакаты, <br/>&nbsp;&nbsp; &nbsp;события, лидеры) и обучение <br/>&nbsp;&nbsp; &nbsp;(видео, руководства пользователя, лично) <br/> <input type="checkbox"> Адаптировано: развернуто, а также целевое <br/>&nbsp;&nbsp; &nbsp;обмен сообщениями и обучение по пользователю <br/> <input type="checkbox"> Других <br/>&nbsp;&nbsp; &nbsp;(Обратите внимание на подробные сведения в столбце "Комментарии".) | |
