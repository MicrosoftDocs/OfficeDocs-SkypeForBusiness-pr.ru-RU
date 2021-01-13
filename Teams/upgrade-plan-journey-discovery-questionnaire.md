---
title: Обновление Microsoft Teams | Оценка среды, вопросы об обнаружении
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Используйте это руководство, чтобы узнать о требованиях для правильной оценки текущей среды для перехода на Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3d1349cf32e652cc308bb85c187db90303aa959
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808959"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>Анкета обнаружения: оценка среды

В следующих наборах таблиц приводится список вопросов, которые помогут вам оценить среду [перед обновлением до Teams:](upgrade-plan-journey-evaluate-environment.md)

- [Сведения об организации в Microsoft 365 или Office 365](#microsoft-365-or-office-365-organization-details)
- [Существующая сводка платформы совместной работы](#existing-collaboration-platform-summary)
- [Сведения о развертывании платформы для совместной работы](#collaboration-platform-deployment-details)
- [Сеть и доступ к службам Microsoft 365 или Office 365](#networking-and-access-to-microsoft-365-or-office-365-services)
- [Конечные точки](#endpoints)
- [Операции](#operations)
- [Внедрение и готовность](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Сведения об организации в Microsoft 365 или Office 365

Настоятельно рекомендуем при работе с анкетой использовать активную организацию Microsoft 365 или Office 365. Если вы еще не активировали или не настроили организацию Microsoft 365 или Office 365, см. план настройки [Microsoft 365 для бизнеса.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

В таблице ниже фиксироваться информация об организации Microsoft 365 или Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Обратите внимание на организацию, которая является производственной: Microsoft 365 или Office 365. <br>имя и ИД в столбце Answer <br/>Если у вас несколько клиентов <br>связанные с вашей организацией, <br>обратите внимание на все ИД. | Имя клиента: <br/>ИД клиента:| |
> | В каких регионах развернуты клиенты?| | |
> | Являются ли эти клиенты Microsoft 365 или Office 365 Multitenant или <br>Выделенный? | <input type="checkbox"> Мультитенантная<br/> <input type="checkbox"> Выделенный | |
> | Какие продукты Microsoft Online вы используете сейчас? <br/>Обратите внимание на количество пользователей, включенных для каждого из них. <br>в столбце "Комментарии". | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> Skype для бизнеса <br>&nbsp; &nbsp; &nbsp;В Интернете <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> OneDrive для бизнеса <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Другое| |
> | Какой уровень лицензии включен для Skype <br>Бизнес-пользователи Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> Автономный режим | Количество пользователей <br>для каждого SKU: |
> | Что такое текущий лес Active Directory <br>работаете в среде? <br/>Если имеется несколько лесов, обратите внимание на подробные сведения <br>в столбце "Прикомменты". | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | Что вы используете для каталога <br>синхронизация сегодня? |<input type="checkbox"> Нет синхронизации (только в облаке) <br/> <input type="checkbox"> Azure Active Directory <br>&nbsp;&nbsp; &nbsp; Подключение <br/> <input type="checkbox"> Другое (укажите в <br>&nbsp;&nbsp; &nbsp; Столбец "Прикомменты".)| |
> | Развернуто ли сейчас федеративное удостоверение <br/>(службы федерации Active Directory или <br>стороне) | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если вы используете федератетное удостоверение, что такое <br>инфраструктура федерации? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Федерация сторонних сторон <br>&nbsp;&nbsp; &nbsp; шлюз <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в <br>&nbsp;&nbsp; &nbsp; Столбец "Прикомменты".) | |
> | Если у вас активный Microsoft 365 или Office 365 <br>— это домен SMTP/SIP вашего <br>для целевых пользователей, связанных с клиентом? | <input type="checkbox"> Н/П — нет Microsoft 365 или Office 365 <br>&nbsp;&nbsp; &nbsp; клиент на месте <br/> <input type="checkbox"> Нет, SMTP/SIP пользователей <br>&nbsp;&nbsp; &nbsp; домен не связан <br>&nbsp;&nbsp; &nbsp; с любыми клиентами в <br>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365 <br/> <input type="checkbox"> Да, SMTP/SIP пользователей <br>&nbsp;&nbsp; &nbsp; домен связан <br>&nbsp;&nbsp; &nbsp; с существующим клиентом <br>&nbsp;&nbsp; &nbsp; в Microsoft 365 или Office 365 | |
> | Соответствуют ли имя пользователя основному SMTP-адресу? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Несогласованное | |

## <a name="existing-collaboration-platform-summary"></a>Существующая сводка платформы совместной работы

В таблице ниже фиксироваться сведения о существующем развертывании платформы для совместной работы.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Развернута ли система Microsoft Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернута ли система Skype для бизнеса? <br/>Для локального и гибридного развертывания убедитесь, что <br>Обратите внимание на версию и накопительный итог обновления <br>в столбце "Прикомменты". | <input type="checkbox"> Да, Microsoft 365 или Office 365 <br/> <input type="checkbox"> Да, гибридная (с Microsoft 365 или Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Да, hosted, dedicated <br>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Да, hosted, shared (third party) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли система Microsoft Exchange? <br/>Для локального и гибридного развертывания убедитесь, что <br>Сведения о версии и подсказке заметок в комментариях <br>. | <input type="checkbox"> Да, Microsoft 365 или Office 365 <br/> <input type="checkbox"> Да, гибридная (с Microsoft 365 или Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Да, hosted, dedicated <br>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Да, hosted, shared <br>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли система SharePoint? <br/>Для локального и гибридного развертывания убедитесь, что <br>Сведения о версии и подсказке заметок в комментариях <br>. | <input type="checkbox"> Да, Microsoft 365 или Office 365 <br/> <input type="checkbox"> Да, гибридная (с Microsoft 365 или Office 365) <br/> <input type="checkbox"> Да, локально <br/> <input type="checkbox"> Да, выделенный веб-сайт <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Да, hosted, dedicated <br>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Да, hosted, shared <br>&nbsp;&nbsp; &nbsp; (third party) <br/> <input type="checkbox"> Нет, другое | |
> | Развернута ли служба Microsoft 365 или Office 365 OneDrive для бизнеса? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Развернуты ли у вас другие сторонние платформы? <br>и используется уже сегодня? В этом случае обратите внимание на количество пользователей <br>эти платформы и сведения об использовании в комментариях <br>. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Резерв резерва <br/> <input type="checkbox"> Другое (укажите в прикомментах) <br>&nbsp;&nbsp; &nbsp; .) | Количество пользователей: <br/>Подробности:|
> | Планируете ли вы переместить пользователей из этой стороной <br>платформы для Teams? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Что такое текущее решение для телефонии и conferencing <br>из пользователей, которые находятся в области действия этой инициативы? | | |
> | У вас есть [SBCs, которые](direct-routing-plan.md#supported-session-border-controllers-sbcs) поддерживают прямую маршрутику, развернутую для ваших офисов, в рамках данной инициативы? <br>Если это так, обратите внимание на сведения в столбце "Примечия".| <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||

## <a name="collaboration-platform-deployment-details"></a>Сведения о развертывании платформы для совместной работы

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (при наличии)

Если применимо, зафиксировать сведения о развертывании Teams можно с помощью приведенной ниже таблицы. Если вы еще не развернули Teams, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каким группам пользователей доступна система Teams? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Определенные пользователи и группы пользователей <br>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Прикомменты" ||
> | Какие функции и модали Teams используются? | <input type="checkbox"> Беседы на основе каналов <br/> <input type="checkbox"> Приватный чат <br/> <input type="checkbox"> Гостевой доступ <br/> <input type="checkbox"> Собрания канала <br/> <input type="checkbox"> Частные собрания <br/> <input type="checkbox"> Частные вызовы <br/> <input type="checkbox"> Ad-hoc channel meetup <br/> <input type="checkbox"> Видео на собраниях <br/> <input type="checkbox"> Совместный доступ к экрану на собраниях <br/> <input type="checkbox"> Аудиоконференция <br/><input type="checkbox"> Приложения (приложения)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Вкладки<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Боты <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Соединитетели<br><input type="checkbox"> Интеграция пользовательского облачного хранилища <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google Drive, Egnyte <br/> <input type="checkbox"> Интеграция с электронной почтой каналов <br/> <input type="checkbox"> Другое (укажите в столбце "Прикомменты").) | |
> | Какие приложения вы развернули в Teams? | | |
> | Блокировали ли вы какие-то конкретные возможности Teams? <br/>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Какие используются клиенты Teams? | <input type="checkbox"> Интернет <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Кому разрешено создавать команды? | <input type="checkbox"> Все в организации <br>&nbsp;&nbsp; &nbsp; (Этот параметр заданной по умолчанию) <br/> <input type="checkbox"> Определенные люди <br>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Прикомменты".) | |
> | Используете ли вы в Teams функции обеспечения безопасности и соответствия требованиям? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-online-if-applicable"></a>Skype для бизнеса Online (при наличии)

Если применимо, зафиксировать сведения о развертывании Skype для бизнеса Online можно с помощью приведенной ниже таблицы. Если вы не развернули skype для бизнеса Online, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Типы пользователей, которые включены для Скайпа <br>для бизнеса Online? | <input type="checkbox"> Все пользователи в организации <br/> <input type="checkbox"> Определенные пользователи и группы пользователей <br>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Прикомменты" | |
> | Какие модали и функции сейчас <br>используется уже сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (мгновенные сообщения/p)<br/> <input type="checkbox"> Собрания <br/> <input type="checkbox"> Федерация <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Аудиоконференция Майкрософт <br/> <input type="checkbox"> Аудиоконференция со сторонними <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце "Комментарии".) <br/> <input type="checkbox"> Планы звонков (ранее — вызовы через ПС) <br/> <input type="checkbox"> Автоотправления организации <br/> <input type="checkbox"> Очереди вызовов | |
> | Вы специально заблокировали Скайп для <br>Возможности Business Online? <br>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какой метод вы используете или планируете использовать? <br>подключить телефонную систему (ранее — облачную УАСК) к <br>через ПС? <br/>Выберите все, что применимо. | <input type="checkbox"> Планы звонков (ранее — вызовы через ПС) <br/> <input type="checkbox"> Локальное подключение через ДНР (использование существующих) <br>&nbsp;&nbsp; &nbsp; Skype для бизнеса 2015 или Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; развертывание) <br/> <input type="checkbox"> Локальное подключение через ДНР (с помощью Cloud Connector) | |
> | Есть ли у вас телефонные номера, перенесенные в Майкрософт <br/>Это относится к планам звонков и звуку <br>Функции для конференций. | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Локальное приложение Skype для бизнеса (если применимо)

Если применимо, зафиксировать сведения о развертывании Skype для бизнеса можно с помощью приведенной ниже таблицы. Если вы не развернули локально Skype для бизнеса, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие версии Lync или Skype для бизнеса сейчас <br>развертываются локально? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype для бизнеса Server 2015 <br/> <input type="checkbox"> Skype для бизнеса Server 2019 <br/> <input type="checkbox"> Skype для бизнеса Cloud Connector Edition | |
> | Настроено ли гибридное подключение со Skype для бизнеса Online? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Эта среда находится и управляется третьей стороной? <br/>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Какие модалии и функции используются в настоящее время? <br>сегодня? | <input type="checkbox"> Обмен мгновенными сообщениями и присутствие (мгновенные сообщения/p) <br/> <input type="checkbox"> Собрания <br/> <input type="checkbox"> Федерация <br/> <input type="checkbox"> Запись собрания <br/> <input type="checkbox"> Сохраняемая беседа или групповой чат <br/> <input type="checkbox"> Аудиоконференция Майкрософт <br>&nbsp;&nbsp; &nbsp; (ранее "Телефонная" на телефонной телефонии) на <br>&nbsp;&nbsp; &nbsp; локального сервера Lync Server или <br>&nbsp;&nbsp; &nbsp; Развертывание Skype для бизнеса <br/> <input type="checkbox"> Аудиоконференция со сторонними <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце "Комментарии") <br/> <input type="checkbox"> Корпоративная голосовая связь с использованием локальной ННП <br>&nbsp;&nbsp; &nbsp; подключение <br/> <input type="checkbox"> Планы звонков (ранее — вызовы через ПС) через <br>&nbsp;&nbsp; &nbsp; Гибридное общение со Skype для бизнеса Online | |
> | Какие у вас развернуты версии пограничного сервера? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype для бизнеса Server 2015 <br/> <input type="checkbox"> Skype для бизнеса Server 2019 | |
> | Развернуты ли у вас Lync или Skype для бизнеса Edge <br>в несколько центра обработки данных? <br/>Если это так, обратите внимание на сведения в столбце "Примечия". | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Выберите службы, которые предоставляет ваша роль Edge сегодня. | <input type="checkbox"> Доступ внешних пользователей (корпоративных пользователей) <br/> <input type="checkbox"> Удаленный доступ пользователей (анонимный внешний доступ) <br>&nbsp;&nbsp; &nbsp; участники собрания) <br/> <input type="checkbox"> Федерация <br/> <input type="checkbox"> Ретранслятор мультимедиа | |
> | Какие из следующих функций голосовых звонков вам <br>есть зависимости? <br/>Обратите внимание на дополнительные зависимости в примечаниях <br>. | <input type="checkbox"> Параметры занятости <br/> <input type="checkbox"> Парковка вызовов <br/> <input type="checkbox"> "Приозвать звонок" или "групповой звонок" <br/> <input type="checkbox"> Обычные телефоны с зонами или "службы hot desking" <br/> <input type="checkbox"> Группы ответа или группы по поиску ответов <br/> <input type="checkbox"> Вид общей строки <br/> <input type="checkbox"> Частная строка <br/> <input type="checkbox"> Голосовая почта <br/> <input type="checkbox"> Звонок с помощью работы <br/> <input type="checkbox"> Номера для экстренного помощи или сведения <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Набор расширений <br/> <input type="checkbox"> автосекретарь <br/> <input type="checkbox"> Абонентский доступ <br/> <input type="checkbox"> Аналоговые устройства <br/> <input type="checkbox"> Факс <br/> <input type="checkbox"> Маскировка или изменение ИД звоня <br/> <input type="checkbox"> Маршруты с учетом расположения <br/> <input type="checkbox"> Маршрутная маршрутка с наименьшими затратами <br/> <input type="checkbox"> Телефоны с телефонами- телефонами с | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Сеть и доступ к службам Microsoft 365 или Office 365

В таблице ниже фиксироваться сетевой контакт организации и то, как ваши пользователи (или будут) подключены к службам Microsoft 365 или Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Действия пользователей в области миграции <br>Получать доступ к Teams, когда они в офисе? <br/>Выберите все, что применимо. | <input type="checkbox"> Маршрутное подключение NAT <br/> <input type="checkbox"> Прокси-сервер <br/> <input type="checkbox"> Общедоступный Wi-Fi <br/> <input type="checkbox"> Управляемые (не общедоступные) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (пиринг Майкрософт) ||
> | Если доступ к Microsoft 365 или Office 365 находится через прокси-сервер, есть ли <br>как-либо обойти прокси-сервер? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Используется ли сейчас ExpressRoute? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет <br/> <input type="checkbox"> Нет, но он планируется | |
> | Вы выполнили оценку готовности к сети? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Требуется ли пользователям использовать VPN при подключении к <br>корпоративные ресурсы удаленно? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Если используется VPN, можно ли исключить трафик Teams из <br>VPN для прямого доступа к Microsoft 365 или службам Office 365? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Поддерживает ли ваша сеть качество обслуживания (QoS)? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Можно ли вы расставить приоритеты для аудио- и видеопотока Teams <br>чтобы повысить качество работы? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | "Во всех расположениях в регионе есть доступ в Интернет", <br>или централизована ли регрессия в Интернете по всему региону? | <input type="checkbox"> Региональный доступ к Интернету <br/> <input type="checkbox"> Централизованный доступ к Интернету | |

## <a name="endpoints"></a>Конечные точки

В таблице ниже фиксироваться сведения о клиентах и конечных точках, которые используются.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие операционные системы для настольных компьютеров вы сейчас используете? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac (укажите версию в столбце "Прикомменты").) <br/> <input type="checkbox"> Linux (укажите распределение в столбце Comments.) <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце "Комментарии".) | |
> | Какая версия Microsoft Office развертывается <br>на эти устройства? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office для Mac 2011 <br/> <input type="checkbox"> Office для Mac 2016 <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце "Комментарии".) | |
> | Используемая технология развертывания Office <br>в своей организации? | <input type="checkbox"> MSI <br/> <input type="checkbox"> "нажми и нажми ижми и вожми" | |
> | Какие мобильные устройства разрешены и поддерживаются <br>используются ли платформы? <br/>Выберите все, что применимо. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Мобильные устройства <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Другое (обратите внимание на подробности в столбце "Комментарии".) | |
> | В какой форме предоставляются мобильные устройства <br/>Выберите все, что применимо. | <input type="checkbox"> Корпоративные устройства <br/> <input type="checkbox"> Возьмите свое устройство | |
> | Какие устройства в настоящее время используют пользователи для доступа <br>службы голосовой и видеоконференции <br>(наушники, телефоны, видео)? | | |

## <a name="operations"></a>Операции

В таблице ниже фиксироваться аспекты работы вашей среды.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Что такое модель операций для вашего сервера Lync Server? <br>Развертывание Skype для бизнеса Server, Microsoft 365 или Office 365 <br>сегодня? | | |
> | Можете ли вы структурой текущего плана поддержки для <br>Lync Server, Skype для бизнеса Server, Microsoft 365 или Office 365? | | |
> | Если развертывание развертывается в нескольких странах или регионах, <br>каждая страна или регион имеют собственные ИТ-/телефонию <br>сотрудников для работы или централизованное управление этим вопросом | <input type="checkbox"> Региональные операции и поддержка <br/> <input type="checkbox"> Централизованные операции и поддержка | |
> | Вы думаете, что вы [думаете о том, что вы](quality-of-experience-review-guide.md)хотите использовать методологию качества вызова? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет | |
> | Назначены ли вам отдельные или группы <br>Роль Quality Champion для платформы совместной работы <br>используется? | <input type="checkbox"> Да <br/> <input type="checkbox"> Нет ||
> | Как следить за сервером Lync Server, Skype для <br>Развертывание Office 365, Microsoft Server или Office 365 | | |
> | Испытываете ли вы проблемы с качеством звонков? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как и когда вы предоставляете учебные курсы <br>справка по новым службам и возможностям? | | |

## <a name="adoption-and-readiness"></a>Внедрение и готовность

Укажите в следующей таблице сведения о принятии системы персоналом и готовности вашей организации к ее использованию.

>
> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каков ваш текущий активный использование <br>Skype для бизнеса? | **__** % всех активных пользователей в сравнении с включенными пользователями | |
> | Как ваша организация использует <br>Skype для бизнеса? | Личные беседы <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Мгновенные мгновенные мгновенны <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызовы <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Общий доступ<br> Собрания <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferencing<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Общий доступ<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Вызовы | |
> | Имеет ли ваша организация внедрение пользователей <br>и команда управления изменениями? | <input type="checkbox"> Да<br/> <input type="checkbox"> Нет | |
> | Как измерять успех технологий в данный момент? <br>Что делать, например Skype для бизнеса? | | |
> | Какой процент базы пользователей, как вы скажете, имеет <br>Принято в Skype для бизнеса? | | |
> | Каково мнение пользователей о Skype для бизнеса? | <input type="checkbox"> Хорошо <br/> <input type="checkbox"> Нейтральный <br/> <input type="checkbox"> Плохо | |
> | Что из следующего наилучшим образом описывает этот вариант. <br>стратегии, используемой для Skype для бизнеса <br>развертывание? | <input type="checkbox"> Широкий выбор: почтовая кампания с <br>&nbsp;&nbsp; &nbsp; ссылки на учебные курсы <br/> <input type="checkbox"> Expanded: Broad reach plus a variety <br>&nbsp;&nbsp; &nbsp; информационных кампаний (плакаты, <br>&nbsp;&nbsp; &nbsp; мероприятия, президенты и обучение; <br>&nbsp;&nbsp; &nbsp; (видео, руководства пользователя, личное лицо) <br/> <input type="checkbox"> Tailored: Expanded, plus targeted <br>&nbsp;&nbsp; &nbsp; обмен сообщениями и обучение по persona <br/> <input type="checkbox"> Другое <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце "Комментарии".) | |


