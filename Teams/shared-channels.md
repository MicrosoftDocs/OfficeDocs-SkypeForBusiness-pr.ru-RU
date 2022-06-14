---
title: Общие каналы в Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Узнайте, как использовать общие каналы в Microsoft Teams и управлять ими.
ms.openlocfilehash: 72701d71712a553c9a02cf9ab41ce0ced0597c3a
ms.sourcegitcommit: c74c83fdb3fdbf1a5ebc9398bf0379d33f888d1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "65795641"
---
# <a name="shared-channels-in-microsoft-teams"></a>Общие каналы в Microsoft Teams

Общие каналы в Microsoft Teams образуют пространства для совместной работы, в которые можно приглашать пользователей, не входящих в состав команд. Доступ к общим каналам есть только у их владельцев и участников. Гостей (пользователей с гостевыми учетными записями Azure Active Directory в вашей организации) невозможно добавить в общий канал, но можно пригласить пользователей извне организации участвовать в общем канале, используя Azure AD B2B Direct Connect.

Общий канал целесообразно использовать, если нужно организовать совместную работу группы людей, входящих в состав разных команд. Например, сотрудники инженерного отдела, отдела продаж и службы поддержки, работающие над разными аспектами одного и того же проекта или продукта, могут использовать общий канал для совместной работы.

Только участники общих каналов могут видеть общие каналы, в которые они добавлены, и участвовать в них. Другие участники команды, к которой подключен общий канал, не увидят этот канал.

При создании общий канал связывается с родительской командой. Его невозможно переместить в другую команду. Кроме того, невозможно преобразовать общие каналы в стандартные каналы и наоборот.

[Сравните общие каналы с другими типами каналов](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="getting-started-with-shared-channels"></a>Начало работы с общими каналами

Общие каналы по умолчанию включены в Teams. [Создав политику каналов](/MicrosoftTeams/teams-policies), можно определить: могут ли пользователи создавать общие каналы; могут ли пользователи предоставлять доступ к каналам для пользователей вне организации; могут ли пользователи участвовать во внешних общих каналах.

Если вы планируете предоставлять доступ к каналам для пользователей вне организации, ознакомьтесь с важными факторами планирования в статье [Планирование внешней совместной работы](/microsoft-365/solutions/plan-external-collaboration).

Чтобы предоставить доступ к каналам для пользователей вне организации, также требуется настроить параметры доступа между клиентами в Azure AD. Такую настройку необходимо сделать во всех организациях, которым нужно предоставить доступ к каналам. Дополнительные сведения см. в статье [Совместная работа с внешними участниками в канале](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="shared-channel-creation"></a>Создание общего канала

Создать общий канал могут только владельцы команд. Участники команд и гости не могут создавать общие каналы. Возможностью создавать общие каналы можно управлять на уровне организации. Используйте [политики](teams-policies.md), чтобы выбрать, каким пользователям в организации разрешено создавать общие каналы.

Пользователь, создающий общий канал, становится его владельцем. Только владелец общего канала может напрямую добавлять пользователей в канал и удалять их. При необходимости можно добавить нескольких владельцев. Владелец общего канала может добавлять в свой канал любых пользователей из организации. Участники общего канала могут пользоваться безопасным местом для бесед. Новые участники общего канала могут видеть все беседы в этом общем канале, включая старые беседы.

Владельцы команды могут видеть названия всех общих каналов в своей команде, а также могут удалять любые общие каналы в своей команде. Владельцы команды не могут видеть файлы, беседы и список участников в общем канале, если они не являются участниками этого общего канала.

Участники команды могут видеть только те общие каналы, в которые они добавлены.

При клонировании команды не будут клонироваться общие каналы, связанные с этой командой.

## <a name="shared-channel-deletion"></a>Удаление общего канала

Удаленный общий канал можно восстановить в течение 30 дней после удаления. При восстановлении удаленного общего канала восстанавливается прежнее участие (общий доступ всех пользователей и команд).

Удаленные команды можно восстановить в течение 30 дней после удаления. При удалении команды также удаляются все общие каналы. При восстановлении удаленной команды восстанавливаются все общие каналы и все отношения общего доступа.

При архивации команды общий доступ пользователей сохраняется, но общий доступ всех команд, кроме родительской команды, удаляется. При восстановлении команды из архивного состояния все каналы восстанавливаются с общим доступом только для индивидуальных участников.

## <a name="adding-and-removing-owners-and-members"></a>Добавление и удаление владельцев и участников

Невозможно удалить владельца общего канала через клиент Teams, если этот владелец является последним владельцем одного или нескольких общих каналов.

Если последний владелец общего канала покидает организацию или удален из группы Microsoft 365, связанной с командой, то один из участников этого общего канала автоматически становится его владельцем. Во избежание подобной ситуации целесообразно добавить несколько владельцев.

## <a name="channel-owner-settings"></a>Параметры владельца канала

У каждого общего канала есть собственные параметры, которыми может управлять владелец канала, включая возможность добавлять и удалять участников, добавлять вкладки и использовать @упоминания для всего канала. Эти настройки не зависят от настроек родительской команды. При создании общий канал наследует параметры у родительской команды, после чего параметры канала можно изменять независимо от параметров родительской команды.

Владелец общего канала может щелкнуть **Управление каналом**, а затем использовать вкладки **Участники** и **Параметры**, чтобы добавлять и удалять участников и настраивать параметры.

## <a name="shared-channel-owner-and-member-actions"></a>Действия владельцев и участников общих каналов

В следующей таблице описываются действия, доступные для владельцев, участников и гостей в общих каналах.

|Действие  |Владелец команды|Участник команды|Гость команды|Владелец общего канала|Участник общего канала|Внешний участник общего канала|
|---------|---------|---------|---------|---------|---------|---------|
|Создание общего канала|Управляется администратором|Управляется администратором и владельцем команды|Нет|Н/Д|Нет|Нет|
|Удаление общего канала|Да|Нет|Нет|Да|Нет|Нет|
|Выход из общего канала|Н/Д|Н/Д|Н/Д|Да, если это не последний владелец|Да|Да|
|Изменение общего канала|Нет|Н/Д|Н/Д|Да|Нет|Нет|
|Восстановление удаленного общего канала|Да|Нет|Нет|Да|Нет|Нет|
|Добавить участников|Нет|Н/Д|Н/Д|Да|Нет|Нет|
|Изменение параметров|Нет|Н/Д|Н/Д|Да|Нет|Нет|
|Управление вкладками и приложениями|Нет|Н/Д|Н/Д|Да, для команды следует установить приложения|Управляется владельцем канала|Нет|

## <a name="shared-channel-sharepoint-sites"></a>Сайты общего канала SharePoint

У каждого общего канала есть [собственный сайт SharePoint](/SharePoint/teams-connected-sites). Для каждого общего канала используется отдельный сайт, чтобы доступ к файлам общего канала был только у участников этого канала. Эти сайты создаются с библиотекой документов по умолчанию, и их можно легко преобразовать в полнофункциональные сайты, используя [интерфейс управления сайтами](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Каждый сайт создается в том же географическом регионе, что и сайт родительской группы. Эти облегченные версии сайтов имеют собственный идентификатор шаблона "TEAMCHANNEL#0", что упрощает управление с помощью PowerShell и API Graph. 

> [!NOTE]
> Доступ к содержимому на сайте общего канала предоставляется только пользователям с разрешениями владельца или участника. Пользователи из родительской группы и администраторы не будут иметь доступа, если они не являются участниками канала.

Сайт общего канала синхронизирует классификацию данных с сайта родительской команды. Членство владельца и участников сайта в группах синхронизируется с членством в общем канале. Невозможно управлять разрешениями для сайта общего канала независимо с помощью SharePoint. 

Teams управляет жизненным циклом сайта общего канала. При удалении сайта вне Teams он автоматически восстанавливается в течение 4 часов, если общий канал по-прежнему активен. При окончательном удалении сайта для общего канала подготавливается новый сайт.

При восстановлении канала или команды с общим каналом также восстанавливаются и сайты. Если сайт общего канала восстанавливается после истечения 30-дневного окна обратимого удаления для общего канала, то сайт работает в качестве автономного.

## <a name="shared-channel-messages"></a>Сообщения в общем канале

Сообщения общего канала хранятся в выделенном системном почтовом ящике, который связан с общим каналом, а не в почтовом ящике группы.

Дополнительные сведения об обнаружении электронных данных для сообщений общего канала см. в статье [Обнаружение электронных данных в содержимом Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Доступ к файлам в общих каналах

Используя [стандартный общий доступ к файлам SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c), можно предоставлять доступ к файлам, папкам и записным книжкам OneNote в общем канале для пользователей, находящихся вне канала.

Если пользователю предоставлен доступ к файлу, папке или записной книжке в общем канале с помощью SharePoint, то при удалении этого пользователя из команды или из общего канала доступ этого пользователя файлу, папке или записной книжке сохранится.

Если добавить существующую записную книжку в общий канал в виде вкладки, то доступ к общему каналу не изменится, а у записной книжки сохранятся существующие разрешения.

## <a name="resources-for-your-users"></a>Ресурсы для пользователей

Следующие статьи могут быть полезны пользователям в организации при использовании общих каналов.

[Создание общего канала в Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Совместное использование канала с другими пользователями в Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Совместное использование канала с командой](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Зачем использовать общий канал в сравнении с другими типами каналов в Teams?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Гости и общие каналы в Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Владелец общего канала и роли участника в Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>Ограничения для общих каналов

В приведенной ниже таблице указано максимальное количество каналов и участников.

|Максимальное количество|Значение|Notes|
|:---------|:----|:----|
|Участники в команде|25 000|Включает всех пользователей в команде и непосредственных участников в общих каналах.|
|Общие каналы в каждой команде|200|Размещение в команде, общий доступ для команды. (Включает удаленные каналы в течение 30-дневного окна восстановления.)|
|Команды, которым может быть предоставлен доступ к каналу|50|Кроме родительской команды|
|Участники в общем канале|5000 непосредственных участников, в том числе до 50 команд. (В отношении этого ограничения каждая команда, которой предоставлен доступ к каналу, считается одним участником.)|Обновления в реальном времени доступны только для 25 000 пользователей одновременно. В списке каналов отображается только 25 000 пользователей.|

Также применяются следующие ограничения:

- Общие каналы поддерживают вкладки, кроме вкладок Stream, "Планировщик" и Forms.

- Бизнес-приложения, боты, соединители и расширения сообщений не поддерживаются.

- При создании команды из существующей команды общие каналы не копируются из существующей команды в новую.

- Уведомления общих каналов не включаются в сообщения электронной почте о пропущенных действиях.

## <a name="supported-apps-in-shared-channels"></a>Поддерживаемые приложения в общих каналах

Сведения о том, как подготовить приложение для общих каналов, см. в статье [Как открыть приложение для совместной работы в Microsoft Teams Связи](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1).

Следующие приложения поддерживаются для использования в общих каналах. 

- Действие
- Adobe Acrobat Sign
- Asana
- Календарь
- Календарь Pro
- Звонки
- Чат
- Code by Vivani
- Conceptboard
- Excel
- FileBrowser
- Файлы
- Flipgrid
- Freehand by InVision
- HeyTaco
- Jira Cloud
- Kahoot!
- Списки
- Lucidchart
- Lumio
- MeisterTask
- Mindmeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- PDF
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Saved
- Scrum-Poker
- Поиск
- SharePoint
- SharePoint Pages
- Slido
- Smartsheet
- SurveyMonkey
- Tasks in a Box
- Teams
- Teams Manager
- Teamviewer
- Командная работа
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Интернет
- Wooclap
- Word
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>См. также

[Обзор B2B Direct Connect](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Настройка параметров доступа между клиентами для B2B Direct Connect](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Обзор команд и каналов в Teams](teams-channels-overview.md)

[Частные каналы в Microsoft Teams](/microsoftteams/private-channels)