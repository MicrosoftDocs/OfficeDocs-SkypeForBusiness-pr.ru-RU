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
ms.openlocfilehash: f2e7ccaac78cd7e96581dc1d9371fc9eef096265
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717980"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="96d1b-103">Экспорт контента с помощью Microsoft Teams API экспорта</span><span class="sxs-lookup"><span data-stu-id="96d1b-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="96d1b-104">Teams Экспорт API позволяет экспортировать 1:1, групповой чат, чаты собраний и сообщения каналов из Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96d1b-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="96d1b-105">Если вашей организации требуется экспортировать Microsoft Teams, вы можете извлечь их с помощью Teams API экспорта.</span><span class="sxs-lookup"><span data-stu-id="96d1b-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="96d1b-106">*Сообщение чата* представляет отдельное сообщение чата в [канале или](/graph/api/resources/channel?view=graph-rest-beta) [чате](/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="96d1b-106">*Chat Message* represents an individual chat message within a [channel](/graph/api/resources/channel?view=graph-rest-beta) or [chat](/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="96d1b-107">Сообщение чата может быть корневым сообщением чата или частью беседы ответа, определенной **свойством replyToId** в сообщении чата.</span><span class="sxs-lookup"><span data-stu-id="96d1b-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="96d1b-108">Вот несколько примеров использования этих API экспорта:</span><span class="sxs-lookup"><span data-stu-id="96d1b-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="96d1b-109">**Пример 1.** Если вы включили Microsoft Teams в своей организации и хотите экспортировать все Microsoft Teams сообщения на дату программным путем передачи диапазона дат для данного пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="96d1b-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="96d1b-110">**Пример 2.** Если вы хотите программным путем экспортировать все сообщения пользователей или группы каждый день, за счет диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="96d1b-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="96d1b-111">API экспорта могут извлекать все сообщения, созданные или обновленные в течение заданного диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="96d1b-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="96d1b-112">Какие API Teams экспорта?</span><span class="sxs-lookup"><span data-stu-id="96d1b-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="96d1b-113">Массовый экспорт сообщения **Teams:** Teams API экспорта поддерживают до 200 RPS для каждого приложения на одного клиента и 600 RPS для приложения, при таких ограничениях вы сможете массово экспортировать Teams сообщений.</span><span class="sxs-lookup"><span data-stu-id="96d1b-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="96d1b-114">**Контекст приложения.** Чтобы позвонить в Microsoft Graph, ваше приложение должно получить маркер доступа из платформа удостоверений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="96d1b-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="96d1b-115">Маркер доступа содержит сведения о вашем приложении и его разрешениях для ресурсов и API, доступных в Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="96d1b-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="96d1b-116">Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано в службе платформа удостоверений Майкрософт и иметь разрешение пользователя или администратора на доступ к нужным Graph Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="96d1b-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="96d1b-117">Если вы уже знакомы с интеграцией приложения с платформа удостоверений Майкрософт для получения [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) маркеров, см. раздел Дальнейшие действия для получения сведений и примеров для Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="96d1b-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="96d1b-118">**Гибридная среда:** Экспорт сообщений поддержки API, отправленных пользователями, которые поддерживаются в гибридной среде (локальной Exchange и Teams).</span><span class="sxs-lookup"><span data-stu-id="96d1b-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="96d1b-119">Все сообщения, отправленные пользователями, настроенными для гибридной среды, будут доступны с помощью API экспорта.</span><span class="sxs-lookup"><span data-stu-id="96d1b-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="96d1b-120">**Удаленные пользователями сообщения:** Сообщения, удаленные пользователями из клиента Teams, можно получать с помощью API экспорта в течение 21 дня с времени удаления.</span><span class="sxs-lookup"><span data-stu-id="96d1b-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="96d1b-121">**Вложения сообщений:** API экспорта включают ссылки на вложения, отправленные как часть сообщений.</span><span class="sxs-lookup"><span data-stu-id="96d1b-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="96d1b-122">С помощью API экспорта можно получить файлы, вложенные в сообщения.</span><span class="sxs-lookup"><span data-stu-id="96d1b-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="96d1b-123">**Свойства сообщения чата:** Полный список свойств, которые поддерживаются Teams API экспорта, можно найти [здесь.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)</span><span class="sxs-lookup"><span data-stu-id="96d1b-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="96d1b-124">Доступ к API Teams экспорта</span><span class="sxs-lookup"><span data-stu-id="96d1b-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="96d1b-125">**Пример 1** — это простой запрос для получения всех сообщений пользователя или группы без фильтров:</span><span class="sxs-lookup"><span data-stu-id="96d1b-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="96d1b-126">**Пример 2.** Пример запроса для извлечения всех сообщений пользователя или группы с помощью фильтров даты и первых 50 сообщений:</span><span class="sxs-lookup"><span data-stu-id="96d1b-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="96d1b-127">API возвращает ответ со ссылкой на следующую страницу на случай нескольких результатов.</span><span class="sxs-lookup"><span data-stu-id="96d1b-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="96d1b-128">Чтобы получить следующий набор результатов, просто позвоните get по URL-адресу @odata.nextlink.</span><span class="sxs-lookup"><span data-stu-id="96d1b-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="96d1b-129">Если @odata.nextlink нет или NULL, будут извлечены все сообщения.</span><span class="sxs-lookup"><span data-stu-id="96d1b-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="96d1b-130">Необходимые условия для доступа к API Teams экспорта</span><span class="sxs-lookup"><span data-stu-id="96d1b-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="96d1b-131">Teams API экспорта в настоящее время находятся в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="96d1b-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="96d1b-132">Она будет доступна только пользователям и клиентам с требуемой лицензией [на](/graph/teams-licenses) API.</span><span class="sxs-lookup"><span data-stu-id="96d1b-132">It will only be available to users and tenants that have the [required licenses](/graph/teams-licenses) for APIs.</span></span> <span data-ttu-id="96d1b-133">В будущем корпорация Майкрософт может потребовать от вас или ваших клиентов оплаты дополнительных сборов в зависимости от объема данных, полученных через API.</span><span class="sxs-lookup"><span data-stu-id="96d1b-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="96d1b-134">Microsoft Teams API в Microsoft Graph доступ к конфиденциальным данным считается защищенным API.</span><span class="sxs-lookup"><span data-stu-id="96d1b-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="96d1b-135">Для экспорта API требуются дополнительные проверки после разрешений и согласия, прежде чем вы сможете использовать их.</span><span class="sxs-lookup"><span data-stu-id="96d1b-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="96d1b-136">Чтобы запросить доступ к этим защищенным API, заполните [форму запроса](https://aka.ms/teamsgraph/requestaccess).</span><span class="sxs-lookup"><span data-stu-id="96d1b-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="96d1b-137">Разрешения приложений используются приложениями, которые работают без участия пользователя, выписаного из учетной записи. разрешения на использование приложений может получить только администратор.</span><span class="sxs-lookup"><span data-stu-id="96d1b-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="96d1b-138">Необходимы следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="96d1b-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="96d1b-139">*Chat.Read.All*: позволяет получать доступ ко всем чатам 1:1, групповым чатам и чатам собраний.</span><span class="sxs-lookup"><span data-stu-id="96d1b-139">*Chat.Read.All*: enables access to all 1:1, Group chat, and meeting chat messages</span></span> 
    - <span data-ttu-id="96d1b-140">*ChannelMessage.Read.All*: позволяет получать доступ ко всем сообщениям каналов.</span><span class="sxs-lookup"><span data-stu-id="96d1b-140">*ChannelMessage.Read.All*: enables access to all channel messages</span></span>  
    - <span data-ttu-id="96d1b-141">*User.Read.All*: обеспечивает доступ к списку пользователей клиента.</span><span class="sxs-lookup"><span data-stu-id="96d1b-141">*User.Read.All*: enables access to the list of users for a tenant</span></span>

## <a name="json-representation"></a><span data-ttu-id="96d1b-142">Представление JSON</span><span class="sxs-lookup"><span data-stu-id="96d1b-142">JSON representation</span></span>

<span data-ttu-id="96d1b-143">В следующем примере представлена JSON-представление ресурса:</span><span class="sxs-lookup"><span data-stu-id="96d1b-143">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="96d1b-144">Пространство имен: microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="96d1b-144">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="96d1b-145">Дополнительные сведения о ресурсе chatMessage см. в статье о типе ресурсов [chatMessage.](/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="96d1b-145">For more details on chatMessage resource, see the [chatMessage resource type](/graph/api/resources/chatmessage) article.</span></span>