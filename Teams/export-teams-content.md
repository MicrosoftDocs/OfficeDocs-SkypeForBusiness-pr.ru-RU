---
title: Экспорт содержимого с помощью Microsoft Teams API экспорта
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: В этой статье вы узнаете, как экспортировать содержимое Teams с помощью Microsoft Teams API экспорта.
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
ms.openlocfilehash: 2f59b275d3caaaa94fc55cf7bc2418ebe0aee4ba
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674221"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Экспорт содержимого с помощью Microsoft Teams API экспорта

Teams API экспорта позволяют экспортировать сообщения 1:1, групповой чат, чаты собраний и сообщения каналов из Microsoft Teams. Если вашей организации необходимо экспортировать Microsoft Teams сообщения, их можно извлечь с помощью Teams API экспорта. *Сообщение чата* представляет отдельное сообщение чата в [канале или](/graph/api/resources/channel) [чате](/graph/api/resources/chat). Сообщение чата может быть корневым сообщением чата или частью потока ответа, определенного **свойством replyToId** в сообщении чата.

Ниже приведены некоторые примеры использования этих API экспорта.

- **Пример 1**. Если вы включили Microsoft Teams в организации и хотите экспортировать все сообщения Microsoft Teams до даты программными средствами, передав диапазон дат для данного пользователя или команды.
- **Пример 2**. Если вы хотите ежедневно экспортировать все сообщения пользователя или группы программными средствами, указав диапазон дат. API экспорта могут получать все сообщения, созданные или обновленные в течение указанного диапазона дат.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Что поддерживается интерфейсами API Teams экспорта?

- Массовый экспорт сообщений **Teams:** Teams API экспорта поддерживают до 200 RPS на приложение на клиент и 600 RPS для приложения. С этими ограничениями вы сможете выполнять массовый экспорт Teams сообщений.
- **Контекст приложения**. Чтобы вызвать Microsoft Graph, ваше приложение должно получить маркер доступа из платформа удостоверений Майкрософт. Маркер доступа содержит сведения о приложении и разрешениях, которые он имеет для ресурсов и API, доступных через Microsoft Graph. Чтобы получить маркер доступа, приложение должно быть зарегистрировано в платформа удостоверений Майкрософт и авторизоваться пользователем или администратором для доступа к нужным Graph Microsoft.

    Если вы уже знакомы с интеграцией приложения с платформа удостоверений Майкрософт для получения маркеров, ознакомьтесь с разделом "Дальнейшие действия[](/graph/auth/auth-concepts#next-steps)" для получения сведений и примеров, относящиеся к Microsoft Graph.
- **Гибридная среда:** API экспорта поддерживают сообщения, отправленные пользователями, подготовленными в гибридной среде (локальные Exchange и Teams). Все сообщения, отправляемые пользователями, настроенными для гибридной среды, будут доступны с помощью API экспорта.
- **Удаленные пользователем сообщения:** Сообщения, удаленные пользователями из клиента Teams, можно получить с помощью API экспорта до 21 дня с даты удаления.
- **Вложения сообщений:** Интерфейсы API экспорта включают ссылки на вложения, отправляемые как часть сообщений. С помощью API экспорта можно получить файлы, вложенные в сообщения.
- **Свойства сообщения чата:** Полный список свойств, поддерживаемых Teams API экспорта, см. [здесь](/graph/api/resources/chatmessage#properties).

> [!NOTE]
> API экспорта не поддерживают *реакции*.

## <a name="how-to-access-teams-export-apis"></a>Как получить доступ к Teams API экспорта

- **Пример 1** — это простой запрос для получения всех сообщений пользователя или команды без фильтров:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **Пример 2** — это пример запроса для получения всех сообщений пользователя или команды путем указания фильтров даты и времени, а также 50 основных сообщений:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> API возвращает ответ со ссылкой на следующую страницу в случае нескольких результатов. Чтобы получить следующий набор результатов, просто вызовите GET по URL-адресу из @odata.nextlink. Если @odata.nextlink отсутствует или имеет значение NULL, извлекаются все сообщения.

## <a name="prerequisites-to-access-teams-export-apis"></a>Предварительные требования для доступа Teams API экспорта

- Microsoft Teams API в Microsoft Graph, которые имеют доступ к конфиденциальным данным, считаются защищенными API. Для использования API экспорта требуется дополнительная проверка, помимо разрешений и согласия. Чтобы запросить доступ к этим защищенным API, заполните [форму запроса](https://aka.ms/teamsgraph/requestaccess).
- Разрешения приложения используются приложениями, которые выполняются без входа пользователя; разрешения приложения могут предоставляться только администратором. Требуются следующие разрешения:
  - *Chat.Read.All*: обеспечивает доступ ко всем 1:1, групповым чатам и чатам собраний
  - *ChannelMessage.Read.All*: обеспечивает доступ ко всем сообщениям канала.
  - *User.Read.All*: обеспечивает доступ к списку пользователей для клиента.

## <a name="license-requirements-for-teams-export-apis"></a>Требования к лицензиям для Teams API экспорта

API экспорта поддерживает безопасность и соответствие требованиям (S+C) и общие сценарии использования с помощью параметра запроса модели. Сценарии S+C (модель A) включают в себя заполненную емкость и требуют подписки E5 и сценариев общего использования (модель Б) доступны для всех подписок и используются только. Дополнительные сведения о начальной емкости и расходных платежах см. в разделе о требованиях к лицензированию и оплате для [API Graph Teams Майкрософт](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Сценарии S+C/Model A

Пользователи должны иметь определенные лицензии E5, чтобы использовать эту функцию и получать заполненную емкость только для приложений, выполняющего функции безопасности и (или) соответствия требованиям. Заполненная емкость рассчитана на пользователя и вычисляется в месяц и агрегирована на уровне клиента. За использование за пределами начальной емкости владельцам приложений выставляется счет за использование API. Модель A может получать доступ к сообщениям только от пользователей с назначенной лицензией E5.

### <a name="general-usagemodel-b-scenarios"></a>Общие сценарии использования и модели B

Доступно для всех сценариев, не связанных с S+C, нет требований к лицензии или заполненной емкости. Когда единицы измерения потребления станут доступны, владельцы приложений будут оплачивать все ежемесячные вызовы API.

### <a name="evaluation-mode-default"></a>Режим оценки (по умолчанию)

Объявление модели не обеспечивает доступ к API с ограниченным использованием для каждого запрашиваемого приложения в целях оценки.

## <a name="json-representation"></a>Представление JSON

Ниже приведен пример представления ресурса в формате JSON:

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

> [!NOTE]
> Дополнительные сведения о ресурсе chatMessage см. в статье о типе ресурса [chatMessage](/graph/api/resources/chatmessage) .
