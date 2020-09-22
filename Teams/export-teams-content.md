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
ms.openlocfilehash: 7849892870f54f43f0fda16564ad472426d46cd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171459"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="cc7b6-103">Экспорт контента с помощью API экспорта Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc7b6-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="cc7b6-104">API экспорта в Teams позволяют экспортировать сообщения из Microsoft Teams в 1:1 и группового чата.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="cc7b6-105">Если в вашей организации необходимо экспортировать сообщения Microsoft Teams, вы сможете извлечь их с помощью API экспорта для групп.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-105">If your organization needs to export Microsoft Teams messages, you can be able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="cc7b6-106">*Сообщение чата* обозначает отдельное сообщение чата в [канале](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) или [чате](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="cc7b6-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="cc7b6-107">Сообщение чата может представлять собой корневое сообщение чата или часть ответа, определяемое свойством **replyToId** в сообщении чата.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="cc7b6-108">Вот несколько примеров того, как можно использовать следующие API экспорта:</span><span class="sxs-lookup"><span data-stu-id="cc7b6-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="cc7b6-109">**Пример 1**: Если вы включили Microsoft Teams в своей организации и хотите по-своему экспортировать все сообщения Microsoft Teams на дату, передавая диапазон данных для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the data range for a given user.</span></span>
- <span data-ttu-id="cc7b6-110">**Пример 2**: Если вы хотите программным образом экспортировать все пользовательские сообщения, указав диапазон данных.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-110">**Example 2**: If you want to programmatically export all user messages daily by providing a data range.</span></span> <span data-ttu-id="cc7b6-111">API экспорта могут получать все сообщения, созданные или обновленные в указанном диапазоне дат.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="cc7b6-112">Что поддерживает API экспорта для групп?</span><span class="sxs-lookup"><span data-stu-id="cc7b6-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="cc7b6-113">**Массовый экспорт сообщений teams:** API экспорта в Teams поддерживают до 200 RPS на приложение на одного клиента и 600 RPS для приложения, с этими ограничениями вы сможете массово экспортировать сообщения Teams.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="cc7b6-114">**Контекст приложения**: чтобы вызвать Microsoft Graph, ваше приложение должно получить маркер доступа от платформы удостоверений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="cc7b6-115">Маркер доступа содержит сведения о приложении и разрешения, предоставленные им для ресурсов и API, доступных через Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="cc7b6-116">Чтобы получить маркер доступа, ваше приложение должно быть зарегистрировано на платформе удостоверений Майкрософт и авторизовано пользователем или администратором для доступа к ресурсам Microsoft Graph, которые ему необходимы.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="cc7b6-117">Если вы уже знакомы с интеграцией приложения с платформой удостоверений Microsoft для получения маркеров, ознакомьтесь с разделом [дальнейшие действия](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) , чтобы получить сведения и примеры, специфичные для Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="cc7b6-118">**Гибридная среда:** API экспорта поддерживают сообщения, отправляемые пользователями, которые настроены в гибридной среде (локальное Exchange и Teams).</span><span class="sxs-lookup"><span data-stu-id="cc7b6-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="cc7b6-119">Все сообщения, отправляемые пользователями, которые настроены для гибридной среды, будут доступны с помощью API экспорта.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="cc7b6-120">**Сообщение удалено пользователем:** Доступ к сообщениям, которые удаляются пользователем из клиента Teams, можно получить, используя API экспорта в течение 30 дней с момента удаления.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="cc7b6-121">**Вложения в сообщения:** API экспорта включают ссылки на вложения, которые отправляются как часть сообщений.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="cc7b6-122">Использование API экспорта. Вы можете получать файлы, вложенные в сообщения.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="cc7b6-123">**Свойства сообщения чата:** Ниже приведен полный список свойств, которые поддерживаются в [этой](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)группе для экспорта API.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="cc7b6-124">Доступ к экспортным API-интерфейсам Teams</span><span class="sxs-lookup"><span data-stu-id="cc7b6-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="cc7b6-125">**Например, 1** — простой запрос для извлечения всех сообщений пользователя без фильтров.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET [https://graph.microsoft.com/beta/users/{id}/chats/allMessages](https://graph.microsoft.com/beta/users/%7bid%7d/chats/allMessages)
    ```

- <span data-ttu-id="cc7b6-126">**Пример 2** — это образец запроса, который позволяет получить все сообщения пользователя, указав фильтры по дате и времени (первые 50 сообщения).</span><span class="sxs-lookup"><span data-stu-id="cc7b6-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="cc7b6-127">API возвращает ответ со следующей ссылкой на страницу в случае с несколькими результатами.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="cc7b6-128">Чтобы получить следующий набор результатов, просто вызовите GET на URL-адресе из @odata. nextlink.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="cc7b6-129">Если @odata. NEXTLINK отсутствует или null, все сообщения извлекаются.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="cc7b6-130">Необходимые условия для доступа к API экспорта в Teams</span><span class="sxs-lookup"><span data-stu-id="cc7b6-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="cc7b6-131">API экспорта в Teams в настоящее время доступны для предварительного просмотра в соответствии с условиями использования API Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-131">Teams Export APIs are currently in preview, subject to the Microsoft APIs Terms of Use.</span></span>  <span data-ttu-id="cc7b6-132">Он будет доступен только для пользователей и клиентов, у которых есть необходимые лицензии.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-132">It will only be available to users and tenants that have the required licenses.</span></span> <span data-ttu-id="cc7b6-133">Попытки доступа к API без соответствующих лицензий приведут к ошибке 403.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-133">Attempts to access APIs without the proper licenses will result in a 403 error.</span></span>
- <span data-ttu-id="cc7b6-134">API Microsoft Teams в Microsoft Graph, исдоступность конфиденциальных данных, рассматриваются как защищенные API.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="cc7b6-135">Для экспорта API-интерфейсов требуется дополнительная проверка, помимо разрешений и согласия, прежде чем можно будет использовать их.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="cc7b6-136">Чтобы запросить доступ к этим защищенным API, заполните [форму запроса](https://aka.ms/teamsgraph/requestaccess).</span><span class="sxs-lookup"><span data-stu-id="cc7b6-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="cc7b6-137">Разрешения на доступ к приложениям используются приложениями, которые выполняются без вошедшего пользователя. разрешения на доступ к приложению могут только пропослать администратору.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="cc7b6-138">Необходимы следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="cc7b6-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="cc7b6-139">*Чат. Read. ALL*: позволяет получить доступ ко всем сообщениям 1:1 и группового чата.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="cc7b6-140">*User. Read. ALL*: позволяет получить доступ к списку пользователей для клиента.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="cc7b6-141">Представление JSON</span><span class="sxs-lookup"><span data-stu-id="cc7b6-141">JSON representation</span></span>

<span data-ttu-id="cc7b6-142">Ниже приведен пример представления ресурса в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="cc7b6-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="cc7b6-143">Пространство имен: Microsoft. Graph</span><span class="sxs-lookup"><span data-stu-id="cc7b6-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="cc7b6-144">Более подробную информацию о ресурсе chatMessage можно найти в статье [тип ресурсов chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .</span><span class="sxs-lookup"><span data-stu-id="cc7b6-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
