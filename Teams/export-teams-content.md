---
title: Экспорт контента с помощью API экспорта Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: В этой статье вы узнаете, как экспортировать содержимое Teams с помощью API экспорта Microsoft Teams.
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
ms.openlocfilehash: 2932488128ccf6f0bff12f3aad39181ed56c1cd0
ms.sourcegitcommit: 26dc4ca6aacf4634b1dbe1bfbd97aa17f8cb7dd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235817"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Экспорт контента с помощью API экспорта Microsoft Teams

API экспорта в Teams позволяют экспортировать сообщения из Microsoft Teams в 1:1 и группового чата. Если в вашей организации необходимо экспортировать сообщения Microsoft Teams, вы сможете извлечь их с помощью API экспорта для групп. *Сообщение чата* обозначает отдельное сообщение чата в [канале](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) или [чате](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). Сообщение чата может представлять собой корневое сообщение чата или часть ответа, определяемое свойством **replyToId** в сообщении чата.

Вот несколько примеров того, как можно использовать следующие API экспорта:

- **Пример 1**: Если вы включили Microsoft Teams в вашей организации и хотите по-своему экспортировать все сообщения Microsoft Teams на дату, передав диапазон дат для определенного пользователя.
- **Пример 2**: Если вы хотите программным образом экспортировать все пользовательские сообщения, указав диапазон дат. API экспорта могут получать все сообщения, созданные или обновленные в указанном диапазоне дат.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Что поддерживает API экспорта для групп?

- **Массовый экспорт сообщений teams:** API экспорта в Teams поддерживают до 200 RPS на приложение на одного клиента и 600 RPS для приложения, с этими ограничениями вы сможете массово экспортировать сообщения Teams.
- **Контекст приложения**: чтобы вызвать Microsoft Graph, ваше приложение должно получить маркер доступа от платформы удостоверений Майкрософт. Маркер доступа содержит сведения о приложении и разрешения, предоставленные им для ресурсов и API, доступных через Microsoft Graph. Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано на платформе удостоверений Майкрософт и авторизовано пользователем или администратором для доступа к ресурсам Microsoft Graph, которые ему необходимы.

    Если вы уже знакомы с интеграцией приложения с платформой удостоверений Microsoft для получения маркеров, ознакомьтесь с разделом [дальнейшие действия](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) , чтобы получить сведения и примеры, специфичные для Microsoft Graph.
- **Гибридная среда:** API экспорта поддерживают сообщения, отправляемые пользователями, которые настроены в гибридной среде (локальное Exchange и Teams). Все сообщения, отправляемые пользователями, которые настроены для гибридной среды, будут доступны с помощью API экспорта.
- **Сообщение удалено пользователем:** Доступ к сообщениям, которые удаляются пользователем из клиента Teams, можно получить, используя API экспорта в течение 30 дней с момента удаления.
- **Вложения в сообщения:** API экспорта включают ссылки на вложения, которые отправляются как часть сообщений. Использование API экспорта. Вы можете получать файлы, вложенные в сообщения.
- **Свойства сообщения чата:** Ниже приведен полный список свойств, которые поддерживаются в [этой](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)группе для экспорта API.

## <a name="how-to-access-teams-export-apis"></a>Доступ к экспортным API-интерфейсам Teams

- **Например, 1** — простой запрос для извлечения всех сообщений пользователя без фильтров.

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- **Пример 2** — это образец запроса, который позволяет получить все сообщения пользователя, указав фильтры по дате и времени (первые 50 сообщения).

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>API возвращает ответ со следующей ссылкой на страницу в случае с несколькими результатами. Чтобы получить следующий набор результатов, просто вызовите GET на URL-адресе из @odata. nextlink. Если @odata. NEXTLINK отсутствует или null, все сообщения извлекаются.

## <a name="prerequisites-to-access-teams-export-apis"></a>Необходимые условия для доступа к API экспорта в Teams 

- API экспорта в Teams в настоящее время находятся в предварительной версии. Он будет доступен только для пользователей и клиентов, у которых есть [необходимые лицензии](https://aka.ms/teams-changenotification-licenses) для API-интерфейсов. В будущем корпорация Майкрософт может потребовать от вас или ваших клиентов платить дополнительные тарифы на основе объема данных, доступ к которому осуществляется через API-интерфейс.
- API Microsoft Teams в Microsoft Graph, исдоступность конфиденциальных данных, рассматриваются как защищенные API. Для экспорта API-интерфейсов требуется дополнительная проверка, помимо разрешений и согласия, прежде чем можно будет использовать их. Чтобы запросить доступ к этим защищенным API, заполните [форму запроса](https://aka.ms/teamsgraph/requestaccess).
- Разрешения на доступ к приложениям используются приложениями, которые выполняются без вошедшего пользователя. разрешения на доступ к приложению могут только пропослать администратору. Необходимы следующие разрешения:

    - *Чат. Read. ALL*: позволяет получить доступ ко всем сообщениям 1:1 и группового чата. 
    - *User. Read. ALL*: позволяет получить доступ к списку пользователей для клиента. 

## <a name="json-representation"></a>Представление JSON

Ниже приведен пример представления ресурса в формате JSON.

Пространство имен: Microsoft. Graph

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
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Более подробную информацию о ресурсе chatMessage можно найти в статье [тип ресурсов chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
