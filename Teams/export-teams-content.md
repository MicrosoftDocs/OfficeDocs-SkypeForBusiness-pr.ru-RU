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
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944604"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Экспорт контента с помощью API экспорта Microsoft Teams

API экспорта Teams позволяют экспортировать 1:1, групповой чат и сообщения каналов из Microsoft Teams. Если вашей организации требуется экспортировать сообщения Microsoft Teams, вы можете извлечь их с помощью API экспорта Teams. *Сообщение чата* представляет отдельное сообщение чата в [канале или](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) [чате.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) Сообщение чата может быть корневым сообщением чата или частью цепочки ответа, определенной **свойством replyToId** в сообщении чата.

Вот несколько примеров использования этих API экспорта:

- **Пример 1.** Если вы включили Microsoft Teams в организации и хотите экспортировать все сообщения Microsoft Teams на дату программным путем передачи диапазона дат для данного пользователя или группы.
- **Пример 2.** Если вы хотите ежедневно экспортировать все сообщения пользователей или группы программным путем, за счет диапазона дат. API экспорта могут извлекать все сообщения, созданные или обновленные в течение заданного диапазона дат.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Какие API экспорта Teams поддерживаются?

- **Массовый экспорт сообщений Teams:** С помощью API-приложений Teams можно экспортировать до 200 RPS на одного клиента и до 600 RPS для приложения, при этом вы сможете массово экспортировать сообщения Teams.
- **Контекст приложения.** Чтобы позвонить в Microsoft Graph, приложение должно получить маркер доступа на платформе удостоверений Майкрософт. Маркер доступа содержит сведения о вашем приложении и его разрешениях для ресурсов и API, доступных в Microsoft Graph. Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано в платформе удостоверений Майкрософт и авторизованно пользователем или администратором для доступа к нужным ресурсам Microsoft Graph.

    Если вы уже знакомы с интеграцией приложения с платформой удостоверений [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) Майкрософт для получения маркеров, ознакомьтесь с информацией и образцами для Microsoft Graph в разделе "Дальнейшие действия".
- **Гибридная среда:** Экспорт API поддерживают сообщения, отправленные пользователями, которые работают в гибридной среде (локальной среде Exchange и Teams). Все сообщения, отправленные пользователями, настроенными для гибридной среды, будут доступны с помощью API экспорта.
- **Удаленные пользователями сообщения** Сообщения, удаленные пользователем из клиента Teams, можно получить с помощью API экспорта в течение 30 дней со времени удаления.
- **Вложения сообщений:** API экспорта включают ссылки на вложения, отправленные как часть сообщений. С помощью API экспорта можно восстановить файлы, вложенные в сообщения.
- **Свойства сообщения чата:** Полный список свойств, поддерживаемых API экспорта Teams, можно найти [здесь.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Доступ к API экспорта Teams

- **Пример 1** — это простой запрос для извлечения всех сообщений пользователя или группы без фильтров:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- **Пример 2** — это пример запроса для извлечения всех сообщений пользователя или группы с помощью фильтров по дате и первых 50 сообщений:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

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
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Дополнительные сведения о ресурсе ChatMessage см. в статье о типе [ресурсов chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)
