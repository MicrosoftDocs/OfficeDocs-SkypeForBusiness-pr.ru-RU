---
title: Экспорт контента с помощью Microsoft Teams API экспорта
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: В этой статье вы узнаете, как экспортировать Teams с помощью Microsoft Teams API экспорта.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082869"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Экспорт контента с помощью Microsoft Teams API экспорта

Teams Экспорт API позволяет экспортировать 1:1, групповой чат, чаты собраний и сообщения каналов из Microsoft Teams. Если вашей организации требуется экспортировать Microsoft Teams, вы можете извлечь их с помощью Teams API экспорта. *Сообщение чата* представляет отдельное сообщение чата в [канале или](/graph/api/resources/channel?view=graph-rest-beta) [чате](/graph/api/resources/chat?view=graph-rest-beta). Сообщение чата может быть корневым сообщением чата или частью беседы ответа, определенной **свойством replyToId** в сообщении чата.

Вот несколько примеров использования этих API экспорта:

- **Пример 1.** Если вы включили Microsoft Teams организации и хотите экспортировать все сообщения Microsoft Teams к дате программным путем передачи диапазона дат для данного пользователя или группы.
- **Пример 2.** Если вы хотите программным путем экспортировать все сообщения пользователей или группы каждый день, за счет диапазона дат. API экспорта могут извлекать все сообщения, созданные или обновленные в течение заданного диапазона дат.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Какие API Teams экспорта?

- Массовый экспорт сообщения **Teams:** API экспорта Teams поддерживают до 200 RPS на одного клиента и 600 RPS для приложения, при этом вы должны иметь возможность массово экспортировать Teams сообщений.
- **Контекст приложения.** Чтобы позвонить в Microsoft Graph, ваше приложение должно получить маркер доступа из платформа удостоверений Майкрософт. Маркер доступа содержит сведения о вашем приложении и его разрешениях для ресурсов и API, доступных в Microsoft Graph. Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано в службе платформа удостоверений Майкрософт и иметь разрешение пользователя или администратора на доступ к нужным ресурсам Microsoft Graph.

    Если вы уже знакомы с интеграцией приложения с платформа удостоверений Майкрософт для получения [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) маркеров, см. раздел Дальнейшие действия для получения сведений и примеров для Microsoft Graph.
- **Гибридная среда:** Экспорт сообщений поддержки API, отправленных пользователями, которые были готовы к гибридной среде (локальной Exchange и Teams). Все сообщения, отправленные пользователями, настроенными для гибридной среды, будут доступны с помощью API экспорта.
- **Удаленные пользователями сообщения:** Сообщения, удаленные пользователями из клиента Teams, можно получить доступ с помощью API экспорта в течение 21 дня после удаления.
- **Вложения сообщений:** API экспорта включают ссылки на вложения, отправленные как часть сообщений. С помощью API экспорта можно получить файлы, вложенные в сообщения.
- **Свойства сообщения чата:** Полный список свойств, которые поддерживаются Teams API экспорта, [можно](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)найти здесь.

>[!NOTE]
>API экспорта не поддерживают *реакции*.

## <a name="how-to-access-teams-export-apis"></a>Доступ к API Teams экспорта

- **Пример 1** — это простой запрос для получения всех сообщений пользователя или группы без фильтров:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **Пример 2.** Пример запроса для извлечения всех сообщений пользователя или группы путем указания фильтров даты и первых 50 сообщений:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>API возвращает ответ со ссылкой на следующую страницу на случай нескольких результатов. Чтобы получить следующий набор результатов, просто позвоните get по URL-адресу @odata.nextlink. Если @odata.nextlink нет или NULL, будут извлечены все сообщения.

## <a name="prerequisites-to-access-teams-export-apis"></a>Необходимые условия для доступа к API Teams экспорта 

- Microsoft Teams API в Microsoft Graph доступ к конфиденциальным данным считается защищенным API. Для экспорта API требуются дополнительные проверки после разрешений и согласия, прежде чем вы сможете использовать их. Чтобы запросить доступ к этим защищенным API, заполните [форму запроса](https://aka.ms/teamsgraph/requestaccess).
- Разрешения приложений используются приложениями, которые работают без участия пользователя, выписаного из учетной записи. разрешения на использование приложений может получить только администратор. Необходимы следующие разрешения:

    - *Chat.Read.All*: позволяет получать доступ ко всем 1:1, групповым чатам и чатам собраний. 
    - *ChannelMessage.Read.All*: позволяет получать доступ ко всем сообщениям каналов.  
    - *User.Read.All*: обеспечивает доступ к списку пользователей клиента.

## <a name="license-requirements-for-teams-export-apis"></a>Лицензии для API Teams экспорта

Экспорт API поддерживает безопасность и соответствие требованиям (S+C) и общие сценарии использования с помощью параметра запроса модели. Сценарии S+C (модель A) включают в себя пропускную способность и требуют подписки на план E5 и сценариев общего использования (модель B) доступны для всех подписок и являются только потреблением. Дополнительные сведения о сборах за пропускную способность и потребление см. в записи Лицензии и требования к оплате [API microsoft Graph Teams.](/graph/teams-licenses)

### <a name="scmodel-a-scenarios"></a>Сценарии S+C/Model A

Только для приложений, которые выполняют функции безопасности и соответствия требованиям, пользователям необходимо иметь определенные лицензии E5, чтобы использовать эту функцию и получить пропускную способность. Пропускная способность рассчитана на одного пользователя и вычисляется в месяц и агрегируется на уровне клиента. За использование за неокупаемую мощность владельцам приложений выписыются счета за потребление API. Модель A позволяет получать доступ только к сообщениям от пользователей с назначенной лицензией E5.

### <a name="general-usagemodel-b-scenarios"></a>Общие сценарии использования и модели B

Доступно для всех сценариев, не связанных с S+C, не существует требований к лицензии или засеяемой емкости. Когда станут доступны метры потребления, с владельцев приложений будет взиматься плата за все ежемесячные звонки по API. 

### <a name="evaluation-mode-default"></a>Режим оценки (по умолчанию)

Объявление модели не позволяет получать доступ к API с ограниченным использованием для каждого запрашиваемого приложения в целях оценки. 

## <a name="json-representation"></a>Представление JSON

В следующем примере представлена JSON-представление ресурса:

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
>Дополнительные сведения о ресурсе chatMessage см. в статье о типе ресурсов [chatMessage.](/graph/api/resources/chatmessage)