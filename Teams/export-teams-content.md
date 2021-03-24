---
title: Экспорт контента с помощью API экспорта Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: В этой статье вы узнаете, как экспортировать контент Teams с помощью API экспорта Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 013cd992619264f875841b1b6bb13aca3943d14e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092454"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Экспорт контента с помощью API экспорта Microsoft Teams

API экспорта Teams позволяют экспортировать 1:1, групповой чат, чаты собраний и сообщения каналов из Microsoft Teams. Если вашей организации требуется экспортировать сообщения Microsoft Teams, вы можете извлечь их с помощью API экспорта Teams. *Сообщение чата* представляет отдельное сообщение чата в [канале или](/graph/api/resources/channel?view=graph-rest-beta) [чате.](/graph/api/resources/chat?view=graph-rest-beta) Сообщение чата может быть корневым сообщением чата или частью цепочки ответа, определенной **свойством replyToId** в сообщении чата.

Вот несколько примеров использования этих API экспорта:

- **Пример 1.** Если вы включили Microsoft Teams в организации и хотите экспортировать все сообщения Microsoft Teams на дату программным путем передачи диапазона дат для данного пользователя или группы.
- **Пример 2.** Если вы хотите ежедневно экспортировать все сообщения пользователей или группы программным путем, за счет диапазона дат. API экспорта могут извлекать все сообщения, созданные или обновленные в течение заданного диапазона дат.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Какие API экспорта Teams поддерживаются?

- **Массовый экспорт сообщений Teams:** С помощью API-приложений Teams можно экспортировать до 200 RPS на одного клиента и до 600 RPS для приложения, при этом вы сможете массово экспортировать сообщения Teams.
- **Контекст приложения.** Чтобы позвонить в Microsoft Graph, приложение должно получить маркер доступа на платформе удостоверений Майкрософт. Маркер доступа содержит сведения о вашем приложении и его разрешениях для ресурсов и API, которые доступны в Microsoft Graph. Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано в платформе удостоверений Майкрософт и авторизованно пользователем или администратором для доступа к нужным ресурсам Microsoft Graph.

    Если вы уже знакомы с интеграцией приложения с платформой удостоверений [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) Майкрософт для получения маркеров, ознакомьтесь с информацией и образцами для Microsoft Graph в разделе "Дальнейшие действия".
- **Гибридная среда:** Экспорт API поддерживают сообщения, отправленные пользователями, которые работают в гибридной среде (локальной среде Exchange и Teams). Все сообщения, отправленные пользователями, настроенными для гибридной среды, будут доступны с помощью API экспорта.
- **Удаленные пользователями сообщения** Сообщения, удаленные пользователями из клиента Teams, можно получить с помощью API экспорта в течение 21 дня после удаления.
- **Вложения сообщений:** API экспорта включают ссылки на вложения, отправленные как часть сообщений. С помощью API экспорта можно восстановить файлы, вложенные в сообщения.
- **Свойства сообщения чата:** Полный список свойств, поддерживаемых API экспорта Teams, можно найти [здесь.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Доступ к API экспорта Teams

- **Пример 1** — это простой запрос для извлечения всех сообщений пользователя или группы без фильтров:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- **Пример 2** — это пример запроса для извлечения всех сообщений пользователя или группы с помощью фильтров по дате и первых 50 сообщений:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>API возвращает ответ со ссылкой на следующую страницу на случай нескольких результатов. Чтобы получить следующий набор результатов, просто позвоните get по URL-адресу @odata.nextlink. Если @odata.nextlink нет или NULL, то будут восстановлены все сообщения.

## <a name="prerequisites-to-access-teams-export-apis"></a>Необходимые условия для доступа к API экспорта Teams 

- API экспорта Teams в настоящее время находятся в предварительной версии. Оно будет доступно только пользователям и клиентам с [требуемой лицензией](/graph/teams-licenses) на API. В будущем корпорация Майкрософт может потребовать от вас или ваших клиентов оплаты дополнительной оплаты в зависимости от объема данных, полученных через API.
- API Microsoft Teams в Microsoft Graph, которые имеют доступ к конфиденциальным данным, считаются защищенными API. Чтобы можно было использовать API экспорта, вам потребуется дополнительная проверка, помимо разрешений и согласия. Чтобы запросить доступ к этим защищенным API, заполните [форму запроса.](https://aka.ms/teamsgraph/requestaccess)
- Разрешения приложений используются приложениями, которые работают без участия пользователя, в который не был в сети пользователь. разрешения на использование приложений может получить только администратор. Необходимы следующие разрешения:

    - *Chat.Read.All*: позволяет получать доступ ко всем 1:1 и групповым чатам 
    - *User.Read.All:* доступ к списку пользователей для клиента 

## <a name="json-representation"></a>Представление JSON

В следующем примере по jSON представлен ресурс:

Пространство имен: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Дополнительные сведения о ресурсе ChatMessage см. в статье о типе [ресурсов chatMessage.](/graph/api/resources/chatmessage)