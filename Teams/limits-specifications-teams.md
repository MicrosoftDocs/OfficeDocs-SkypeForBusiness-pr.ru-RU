---
title: Ограничения и спецификации для Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: В этой статье описаны ограничения, спецификации и другие требования, применяемые к Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee791259b938345876e9761344616fac7d1d9e45
ms.sourcegitcommit: 3056f95e9f654b78636949f43eacdde297e52c6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2023
ms.locfileid: "69990414"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Ограничения и спецификации для Microsoft Teams

В этой статье описаны некоторые ограничения, спецификации и другие требования, применяемые к Teams.

## <a name="teams-and-channels"></a>Команды и каналы

|Функция    | Максимальный предел |
|-----------|---------------|
|Количество команд, которые может создавать пользователь | Применяется ограничение в 250 объектов&sup1;         |
|Количество групп, в которые может входить пользователь|1 000&sup2;|
|Количество участников в команде | 25 000<sup>6</sup>     |
|Количество владельцев на команду | 100   |
|Количество команд для всей организации, разрешенное в клиенте | 5&sup2;     |
|Количество участников в [команде для всей организации](create-an-org-wide-team.md) | 10 000       |
|Количество команд, которые может создавать глобальный администратор        |  500 000   |
|Количество команд, которое может иметь организация, использующая Microsoft 365 или Office 365    | 500 000 & sup3;     |
|Количество каналов на команду    | 200 (включая удаленные каналы)<sup>4</sup>        |
|Количество закрытых каналов на команду    |30 (включая удаленные каналы)<sup>4</sup>        |
|Количество участников в закрытом канале    |250|
|Максимальный размер списка рассылки, группы безопасности или группы Microsoft 365, которые можно импортировать в команду    |3,500|
|Максимальное количество участников в группе Microsoft 365, которое можно преобразовать в команду    |10,000<sup>6</sup>     |
|Размер записи в беседе канала | Около 28 КБ на каждую запись<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> Это ограничение включает архивированные команды. 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 КБ — это приблизительное ограничение, так как сюда входит само сообщение (текст, ссылки на изображения и т. д.), @-упоминания, число соединителей и реакции.

<sup>6</sup> Это ограничение распространяется на участников общих каналов, не входящих в команду. Необходимо также отметить, что в командах с более чем 10 000 участниками упоминания команд или каналов блокируются.

> [!NOTE]
> Ограничения для общих каналов см. в разделе [Ограничения для общих каналов](/MicrosoftTeams/shared-channels#limits-for-shared-channels).

## <a name="messaging"></a>Обмен сообщениями

### <a name="chat"></a>Чат

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|Функция  | Максимальный предел  |
|---------|---------|
|Количество пользователей в закрытом чате<sup>1</sup>  | 250<sup>2</sup> |
|Количество людей, подключившихся к видео- или аудиоконференции из чата | 20 |
|Количество вложенных файлов<sup>3</sup>  |10     |
|Размер чата | Около 28 КБ на запись<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup>Если число вложений превышает это ограничение, появится сообщение об ошибке.

<sup>4</sup> 28 КБ — это приблизительное ограничение, так как оно включает само сообщение (текст, ссылки на изображения и т. д.), @упоминания и реакции.

### <a name="emailing-a-channel"></a>Отправка сообщения электронной почты в канал

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|Функция  | Максимальный предел  |
|---------|---------|
|Размер сообщения<sup>1<sup> | 24 КБ |
|Количество вложенных файлов<sup>2</sup>  |20     |
|Размер каждого вложенного файла | Меньше 10 МБ |
|Количество встроенных изображений<sup>2</sup> |50   |

> [!NOTE]
> Существует ограничение регулирования на количество сообщений электронной почты, которые вы можете отправить в канал. Ограничение составляет шесть сообщений электронной почты за 10 секунд для канала на пользователя и восемь сообщений электронной почты за 10 секунд для клиента на пользователя.
<sup>1</sup>Если сообщение превышает это ограничение, создается окно предварительного просмотра сообщения, и пользователю предлагается скачать и просмотреть исходное сообщение электронной почты по указанной ссылке.

<sup>2</sup>Если число вложений или изображений превышает это ограничение, появится сообщение об ошибке.

Дополнительные сведения см. в статье [Ограничения Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>Названия каналов

Названия каналов не могут содержать следующие символы и слова.

|Тип|Пример|
|---------|---------|
|Символы     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Символы из этих диапазонов    | 0–1F<br>80–9F        |
|Слова     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 — COM9, LPT1 — LPT9, desktop.ini,  &#95;vti&#95;|

Названия каналов также не могут начинаться с символа подчеркивания (_) или точки (.) либо заканчиваться точкой (.).

## <a name="meetings-and-calls"></a>Собрания и звонки

|Функция     | Максимальный предел |
|------------|---------------|
|Количество людей на встрече (могут общаться и звонить)  | 1000, включает GCC, GCCH и DoD, но пока не включает A1 (300).|
|Количество людей, подключившихся к видео- или аудиоконференции из чата | 20 |
|Максимальный размер файла PowerPoint | 2 ГБ|
|Teams хранит [записи собраний](cloud-recording.md), которые не отправляются в Microsoft Stream и доступны для скачивания | 20 дней |
| Максимальная длина записи собрания | 4 часа или 1,5 ГБ. После этого запись будет остановлена и автоматически перезапущена.

Дополнительные сведения см. в разделе [Собрания, вебинары и трансляции](/microsoftteams/quick-start-meetings-live-events).  
  
> [!NOTE]
> Комнаты отдыха можно создавать только для собраний, где число участников не превышает 300 человек. Кроме того, при создании комнат отдыха для собрания число участников собрания автоматически ограничивается до 300. Конечным пользователям рекомендуется не создавать комнаты отдыха для собраний, на которых планируется участие более 300 человек. Для получения дополнительных сведений о больших собраниях Teams отправьте конечным пользователям [рекомендации по большому собранию Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)

### <a name="meeting-expiration"></a>Окончание срока действия собрания

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|Тип собрания  |Срок действия собрания  |При каждом начале или обновлении собрания срок действия продлевается на указанный период  |
|---------|---------|---------|
|Незапланированные собрания     |Время начала + 8 часов         |Н/Д         |
|Обычное без времени окончания     |Время начала + 60 дней         | 60 дней        |
|Обычное со временем окончания     |Время окончания + 60 дней         |60 дней         |
|Повторяющееся без времени окончания     |Время начала + 60 дней         |60 дней         |
|Повторяющееся со временем окончания     |Время окончания последнего повторения + 60 дней         |60 дней         |

> [!NOTE]
> Для собраний Microsoft Teams установлено ограничение по времени — 30 часов.

## <a name="live-events"></a>Трансляции
  
Трансляции — это структурированные собрания, которые дают возможность организации планировать и проводить мероприятия с трансляцией для крупных аудиторий (до 20 000 пользователей) в Интернете. Взаимодействие с аудиторией во время трансляций подразумевает управление вопросами и ответами.

|Функция     | Максимальный предел |
|------------|---------------|
|Размер аудитории | До 20 000 участников <sup>1</sup> |
|Длительность мероприятия | 4 часа |
|Одновременные трансляции, выполняемые в microsoft 365 или Office 365 организации <sup>2</sup> | 15 |

<sup>1</sup> Обычные 10 000 увеличены до 20 000 до 30 июня 2023 года. Трансляции в Yammer и/или Microsoft Stream позволяют запланировать даже большее число участников. Подробнее см. в статье [Трансляции в Microsoft 365](/stream/live-event-m365). Обратите внимание, что для событий с количеством участников более 20 000 необходима [Программа поддержки трансляций](/stream/live-events-assistance).  
  
<sup>2</sup> Можно запланировать любое количество трансляций, но одновременно можно выполнять только 15. Сразу после присоединения организатора к трансляции она считается запущенной. Организатор, пытающийся присоединить шестнадцатую трансляцию, получит сообщение об ошибке.

Дополнительные сведения о трансляциях см. в разделе [Трансляции Teams](teams-live-events/plan-for-teams-live-events.md#teams-live-events). См. также [Планирование трансляции Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Повышение предельных значений для трансляций Microsoft 365**
>
> **Чтобы продолжать поддерживать потребности наших клиентов, мы продлим временное увеличение лимита для трансляций до 30 июня 2023 г., в том числе:**
>
>- Поддержка событий для до 20 000 участников
>- 50 одновременных трансляций в клиенте
>- Длительность события — 16 часов на трансляцию
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Присутствие в Outlook

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>Хранилище

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> У каждого [закрытого канала](./private-channels.md) есть собственный сайт SharePoint (предыдущее название "семейство веб-сайтов").

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|Компонент                 |Microsoft 365 бизнес базовый  |Microsoft 365 бизнес стандарт   |Office 365 для предприятий E1  |Office 365 корпоративный E3  |Office 365 корпоративный E5  |Office 365 корпоративный F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Хранилище                 |1 ТБ на организацию, а также 10 ГБ на каждую приобретенную лицензию  |1 ТБ на организацию, а также 10 ГБ на каждую приобретенную лицензию  |1 ТБ на организацию, а также 10 ГБ на каждую приобретенную лицензию   |1 ТБ на организацию, а также 10 ГБ на каждую приобретенную лицензию |1 ТБ на организацию, а также 10 ГБ на каждую приобретенную лицензию  |1 ТБ на организацию           |
|Хранилище для файлов Teams |До 25 ТБ на сайт или группу |До 25 ТБ на сайт или группу |До 25 ТБ на сайт или группу |До 25 ТБ на сайт или группу |До 25 ТБ на сайт или группу |До 25 ТБ на сайт или группу |
|Ограничение на передачу файлов (для отдельного файла)    |250 ГБ.    |250 ГБ.    |250 ГБ.    |250 ГБ.    |250 ГБ.    |250 ГБ.    |

Каналы создаются с помощью папок на сайте SharePoint Online (предыдущее название "семейство веб-сайтов"), созданном для команды, поэтому для вкладок файлов в каналах используются ограничения хранилища команды, к которой они относятся.

Дополнительные сведения см. в статье [Ограничения SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Команды классов

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Команда класса — это тип шаблона с дополнительными приложениями и ограничениями по количеству участников команды.

> [!NOTE]
> Для использования команд классов требуется [лицензия на Office 365 для образования](https://www.microsoft.com/education/products/office).

Ограничения для команд классов перечислены в следующей таблице:

|Компонент  |Максимальный предел  |
|---------|---------|
|Количество участников в команде    | См. раздел [Команды и каналы](#teams-and-channels) этой статьи        |
|Количество участников для использования заданий в команде класса    | 300        |
|Количество участников для использования записной книжки OneNote для занятий в команде класса     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>Теги

|Компонент  |Максимальный предел  |
|---------|---------|
|Количество тегов на команду    | 100        |
|Количество предлагаемых тегов по умолчанию на команду    | 25        |
|Число участников команды, назначенных тегу    |200         |
|Количество тегов, назначенных пользователю в одной команде    |25         |

## <a name="contacts"></a>Контакты

В Teams используются следующие контакты:

- Контакты в службе Active Directory организации
- Контакты, добавленные в папку пользователя Outlook по умолчанию

Пользователи Teams могут общаться с любыми пользователями из службы Active Directory организации и добавлять любых пользователей в качестве контактов в службу Active Directory организации и в свои списки контактов, используя параметры **Чат** > **Контакты** или **Звонки** > **Контакты**.

Пользователи Teams также могут добавить в качестве контакта человека, которого нет в службе Active Directory организации, выбрав **Звонки** > **Контакты**.

## <a name="browsers"></a>Браузеры

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Операционные системы

Сведения о требованиях к операционным системам см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).
