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
ms.openlocfilehash: 896e60e8de6e01208a07c40e757a79a12192383a
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611823"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="d8019-103">Экспорт контента с помощью API экспорта Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8019-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="d8019-104">API экспорта Teams позволяют экспортировать 1:1 и групповые сообщения чата из Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8019-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="d8019-105">Если вашей организации требуется экспортировать сообщения Microsoft Teams, вы можете извлечь их с помощью API экспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="d8019-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="d8019-106">*Сообщение чата* представляет отдельное сообщение чата в [канале или](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) [чате.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="d8019-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="d8019-107">Сообщение чата может быть корневым сообщением чата или частью цепочки ответа, определенной **свойством replyToId** в сообщении чата.</span><span class="sxs-lookup"><span data-stu-id="d8019-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="d8019-108">Вот несколько примеров использования этих API экспорта:</span><span class="sxs-lookup"><span data-stu-id="d8019-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="d8019-109">**Пример 1.** Если вы включили Microsoft Teams в организации и хотите экспортировать все сообщения Microsoft Teams на дату программным путем передачи диапазона дат для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8019-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user.</span></span>
- <span data-ttu-id="d8019-110">**Пример 2.** Если вы хотите ежедневно экспортировать все сообщения пользователей программным путем с диапазоном дат.</span><span class="sxs-lookup"><span data-stu-id="d8019-110">**Example 2**: If you want to programmatically export all user messages daily by providing a date range.</span></span> <span data-ttu-id="d8019-111">API экспорта могут извлекать все сообщения, созданные или обновленные в течение заданного диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="d8019-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="d8019-112">Какие API экспорта Teams поддерживаются?</span><span class="sxs-lookup"><span data-stu-id="d8019-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="d8019-113">**Массовый экспорт сообщений Teams:** С помощью API-приложений Teams можно экспортировать до 200 RPS на одного клиента и до 600 RPS для приложения, при этом вы сможете массово экспортировать сообщения Teams.</span><span class="sxs-lookup"><span data-stu-id="d8019-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="d8019-114">**Контекст приложения.** Чтобы позвонить в Microsoft Graph, приложение должно получить маркер доступа на платформе удостоверений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d8019-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="d8019-115">Маркер доступа содержит сведения о вашем приложении и его разрешениях для ресурсов и API, доступных в Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d8019-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="d8019-116">Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано в платформе удостоверений Майкрософт и авторизованно пользователем или администратором для доступа к нужным ресурсам Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d8019-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="d8019-117">Если вы уже знакомы с интеграцией приложения с платформой удостоверений [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) Майкрософт для получения маркеров, ознакомьтесь с информацией и примерами для Microsoft Graph в разделе "Дальнейшие действия".</span><span class="sxs-lookup"><span data-stu-id="d8019-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="d8019-118">**Гибридная среда:** Экспорт API-поддержку сообщений, отправленных пользователями, которые работают в гибридной среде (локальной среде Exchange и Teams).</span><span class="sxs-lookup"><span data-stu-id="d8019-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="d8019-119">Все сообщения, отправленные пользователями, настроенными для гибридной среды, будут доступны с помощью API экспорта.</span><span class="sxs-lookup"><span data-stu-id="d8019-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="d8019-120">**Удаленные пользователями сообщения** Сообщения, удаленные пользователем из клиента Teams, можно получить с помощью API экспорта в течение 30 дней со времени удаления.</span><span class="sxs-lookup"><span data-stu-id="d8019-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="d8019-121">**Вложения сообщений:** API экспорта включают ссылки на вложения, отправленные как часть сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8019-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="d8019-122">С помощью API экспорта можно восстановить файлы, вложенные в сообщения.</span><span class="sxs-lookup"><span data-stu-id="d8019-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="d8019-123">**Свойства сообщения чата:** Полный список свойств, поддерживаемых API экспорта Teams, можно найти [здесь.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)</span><span class="sxs-lookup"><span data-stu-id="d8019-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="d8019-124">Доступ к API экспорта Teams</span><span class="sxs-lookup"><span data-stu-id="d8019-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="d8019-125">**Пример 1** — это простой запрос для извлечения всех сообщений пользователя без фильтров.</span><span class="sxs-lookup"><span data-stu-id="d8019-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- <span data-ttu-id="d8019-126">**Пример 2** — это пример запроса для извлечения всех сообщений пользователя с помощью фильтров по времени даты и первых 50 сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8019-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="d8019-127">API возвращает ответ со ссылкой на следующую страницу на случай нескольких результатов.</span><span class="sxs-lookup"><span data-stu-id="d8019-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="d8019-128">Чтобы получить следующий набор результатов, просто позвоните get по URL-адресу @odata.nextlink.</span><span class="sxs-lookup"><span data-stu-id="d8019-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="d8019-129">Если @odata.nextlink нет или NULL, будут восстановлены все сообщения.</span><span class="sxs-lookup"><span data-stu-id="d8019-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="d8019-130">Необходимые условия для доступа к API экспорта Teams</span><span class="sxs-lookup"><span data-stu-id="d8019-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="d8019-131">API экспорта Teams в настоящее время находятся в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="d8019-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="d8019-132">Оно будет доступно только пользователям и клиентам с [требуемой лицензией](https://aka.ms/teams-changenotification-licenses) на API.</span><span class="sxs-lookup"><span data-stu-id="d8019-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="d8019-133">В будущем корпорация Майкрософт может потребовать от вас или ваших клиентов оплаты дополнительных сборов в зависимости от объема данных, полученных через API.</span><span class="sxs-lookup"><span data-stu-id="d8019-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="d8019-134">API Microsoft Teams в Microsoft Graph, которые имеют доступ к конфиденциальным данным, считаются защищенными API.</span><span class="sxs-lookup"><span data-stu-id="d8019-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="d8019-135">Для экспорта API требуется дополнительная проверка, помимо разрешений и согласия, перед использованием.</span><span class="sxs-lookup"><span data-stu-id="d8019-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="d8019-136">Чтобы запросить доступ к этим защищенным API, заполните [форму запроса.](https://aka.ms/teamsgraph/requestaccess)</span><span class="sxs-lookup"><span data-stu-id="d8019-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="d8019-137">Разрешения приложений используются приложениями, которые работают без участия пользователя, в который не был в сети пользователь. разрешения на использование приложений может получить только администратор.</span><span class="sxs-lookup"><span data-stu-id="d8019-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="d8019-138">Необходимы следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="d8019-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="d8019-139">*Chat.Read.All*: позволяет получать доступ ко всем 1:1 и групповым чатам</span><span class="sxs-lookup"><span data-stu-id="d8019-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="d8019-140">*User.Read.All:* доступ к списку пользователей для клиента</span><span class="sxs-lookup"><span data-stu-id="d8019-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="d8019-141">Представление JSON</span><span class="sxs-lookup"><span data-stu-id="d8019-141">JSON representation</span></span>

<span data-ttu-id="d8019-142">Следующий пример — представление ресурса Скайп Скайп по JSON:</span><span class="sxs-lookup"><span data-stu-id="d8019-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="d8019-143">Пространство имен: microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="d8019-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="d8019-144">Дополнительные сведения о ресурсе ChatMessage см. в статье о типе [ресурсов chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="d8019-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
