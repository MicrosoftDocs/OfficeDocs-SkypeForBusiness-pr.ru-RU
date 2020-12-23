---
title: Разрешения и рекомендации для приложений Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Администратор может узнать, какие данные и разрешения запрашиваются приложениями Microsoft Teams у их организации.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739387"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="8f956-103">Разрешения и рекомендации для приложений Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f956-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="8f956-104">Приложения Microsoft Teams позволяют агрегировать одну или несколько возможностей в _пакет приложения_, который можно установить, обновить и удалить.</span><span class="sxs-lookup"><span data-stu-id="8f956-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="8f956-105">К этим возможностям относятся:</span><span class="sxs-lookup"><span data-stu-id="8f956-105">The capabilities include:</span></span>

- <span data-ttu-id="8f956-106">боты;</span><span class="sxs-lookup"><span data-stu-id="8f956-106">Bots</span></span>
- <span data-ttu-id="8f956-107">расширения для обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="8f956-107">Messaging extensions</span></span>
- <span data-ttu-id="8f956-108">Вкладки</span><span class="sxs-lookup"><span data-stu-id="8f956-108">Tabs</span></span>
- <span data-ttu-id="8f956-109">Соединители</span><span class="sxs-lookup"><span data-stu-id="8f956-109">Connectors</span></span>

<span data-ttu-id="8f956-110">Получение согласия пользователей на приложения и управление этими приложениями ИТ-отделом осуществляется в рамках политики.</span><span class="sxs-lookup"><span data-stu-id="8f956-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="8f956-111">Однако в большинстве части разрешения и профиль рисков приложения определяются разрешениями и профилями рисков, которые содержит приложение.</span><span class="sxs-lookup"><span data-stu-id="8f956-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="8f956-112">Таким образом, основное внимание в этой статье уделяется разрешениям и рекомендациями для уровня возможностей.</span><span class="sxs-lookup"><span data-stu-id="8f956-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="8f956-113">Разрешения, указанные ниже прописными буквами, например RECEIVE_MESSAGE и REPLYTO_MESSAGE, не указаны в [документации для разработчиков Microsoft Teams](https://aka.ms/teamsdevdocs) или [разрешениях для Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="8f956-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="8f956-114">Это просто описательные условные обозначения, используемые в рамках данной статьи.</span><span class="sxs-lookup"><span data-stu-id="8f956-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="8f956-115">Название</span><span class="sxs-lookup"><span data-stu-id="8f956-115">Title</span></span>   | <span data-ttu-id="8f956-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8f956-116">Description</span></span>    |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8f956-118">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="8f956-118">Decision point</span></span>|<ul><li><span data-ttu-id="8f956-119">Используйте таблицы ниже в качестве руководства, чтобы понять, какие разрешения запрашивают приложения.</span><span class="sxs-lookup"><span data-stu-id="8f956-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Значок, изображающий следующее действие](media/audio_conferencing_image9.png)<br/><span data-ttu-id="8f956-121">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="8f956-121">Next step</span></span>|<ul><li><span data-ttu-id="8f956-122">Изумите приложение или службу, чтобы решить, хотите ли вы разрешить доступ к ним в организации.</span><span class="sxs-lookup"><span data-stu-id="8f956-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="8f956-123">Например, боты отправляют и получают сообщения от пользователей и (за исключением корпоративных) настраиваемые боты находятся за пределами границы соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8f956-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="8f956-124">Таким образом, все приложения, которые включают бота, требуются эти разрешения и имеет как минимум этот профиль риска.</span><span class="sxs-lookup"><span data-stu-id="8f956-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="8f956-125">Глобальные разрешения и соображения по приложениям</span><span class="sxs-lookup"><span data-stu-id="8f956-125">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="8f956-126">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-126">Required permissions</span></span>

<span data-ttu-id="8f956-127">Нет</span><span class="sxs-lookup"><span data-stu-id="8f956-127">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="8f956-128">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-128">Optional permissions</span></span>

<span data-ttu-id="8f956-129">Нет</span><span class="sxs-lookup"><span data-stu-id="8f956-129">None</span></span>

### <a name="considerations"></a><span data-ttu-id="8f956-130">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8f956-130">Considerations</span></span>

- <span data-ttu-id="8f956-131">Приложение должно сообщать, какие данные он использует и для чего они используются в условиях использования и связей политики конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="8f956-131">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="8f956-132">[Разрешение для конкретного](resource-specific-consent.md) ресурса предоставляет набор разрешений, которые могут запрашиваться приложениями, который отображается на экране установки приложения.</span><span class="sxs-lookup"><span data-stu-id="8f956-132">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="8f956-133">Дополнительные данные о разрешениях для конкретного ресурса см. в справке по разрешениям [Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="8f956-133">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="8f956-134">Кроме того, приложениям могут потребоваться разрешения, кроме разрешений на доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="8f956-134">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="8f956-135">После установки приложения приложение может запрашивать разрешения Graph через запрос на согласие.</span><span class="sxs-lookup"><span data-stu-id="8f956-135">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="8f956-136">Дополнительные узнать см. в этом видеоролике о разрешениях приложений [Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="8f956-136">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="8f956-137">Вы можете настроить разрешения API и получить согласие на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="8f956-137">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="8f956-138">Дополнительные узнать см. в структуре согласия [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="8f956-138">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="8f956-139">Боты и расширения для обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="8f956-139">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="8f956-140">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-140">Required permissions</span></span>

- <span data-ttu-id="8f956-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="8f956-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="8f956-142">Бот может получать сообщения от пользователей и отвечать на них. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8f956-142">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="8f956-143">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="8f956-143">POST_MESSAGE_USER.</span></span> <span data-ttu-id="8f956-144">После того как пользователь отправил сообщение боту, он может в любое  время отправлять ему прямые сообщения (также называемые упреждающие сообщения).</span><span class="sxs-lookup"><span data-stu-id="8f956-144">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="8f956-145">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="8f956-145">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="8f956-146">Боты, добавленные в команды, могут получить список имен и ИД каналов в команде.</span><span class="sxs-lookup"><span data-stu-id="8f956-146">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="8f956-147">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-147">Optional permissions</span></span>

- <span data-ttu-id="8f956-148">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="8f956-148">IDENTITY.</span></span> <span data-ttu-id="8f956-149">Когда приложение используется в канале, боты приложения могут получать доступ к основным сведениям об удостоверениях участников группы (имя, фамилия, имя-имя пользователя [UPN], адрес электронной почты); при его использования в личном или групповом чате бот может получить доступ к той же информации для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f956-149">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="8f956-150">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="8f956-150">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="8f956-151">Позволяет ботам приложения в любое время отправлять прямые (упреждающие) сообщения членам группы, даже если пользователь никогда не общался с ботом.</span><span class="sxs-lookup"><span data-stu-id="8f956-151">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="8f956-152">Следующие разрешения не являются явными, но подразумеваются под RECEIVE_MESSAGE и REPLYTO_MESSAGE, а также области, в которых можно использовать боты, объявленные в манифесте:</span><span class="sxs-lookup"><span data-stu-id="8f956-152">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="8f956-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="8f956-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="8f956-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="8f956-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="8f956-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="8f956-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="8f956-156">SEND_FILES, RECEIVE_FILES. <sup>2.</sup> Управляет тем, может ли бот отправлять и получать файлы в личном чате (пока не поддерживается для групповых чатов или каналов).</span><span class="sxs-lookup"><span data-stu-id="8f956-156">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="8f956-157">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8f956-157">Considerations</span></span>

- <span data-ttu-id="8f956-158">Боты имеют доступ только к командам, в которые они были добавлены, или к пользователям, которые их установили.</span><span class="sxs-lookup"><span data-stu-id="8f956-158">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="8f956-159">Боты получают только сообщения, в которых они явно упоминаются пользователями.</span><span class="sxs-lookup"><span data-stu-id="8f956-159">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="8f956-160">Эти данные покинет корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="8f956-160">This data leaves the corporate network.</span></span>

- <span data-ttu-id="8f956-161">Боты могут отвечать только на беседы, в которых они упомянуты.</span><span class="sxs-lookup"><span data-stu-id="8f956-161">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="8f956-162">После того как пользователь побеседует с ботом, он сможет отправлять прямые сообщения в любое время.</span><span class="sxs-lookup"><span data-stu-id="8f956-162">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="8f956-163">Обычно сообщения ботов могут содержать ссылки на фишинговые или вредоносные сайты, но они могут быть заблокированы пользователем, администратором клиента или глобально корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f956-163">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="8f956-164">Бот может получать (и может хранить) очень основные сведения об удостоверениях участников группы, в которые добавлено приложение, а также отдельных пользователей в личных или групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="8f956-164">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="8f956-165">Чтобы получить дополнительные сведения об этих пользователях, бот должен потребовать от них войти в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8f956-165">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="8f956-166">Боты могут извлекать (и хранить) список каналов в группе; эти данные покинет корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="8f956-166">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="8f956-167">При отправлении файла боту он покидает корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="8f956-167">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="8f956-168">Для отправки и получения файлов требуется утверждение пользователями для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="8f956-168">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="8f956-169">По умолчанию боты не могут действовать от имени пользователя, но могут попросить их войти в учетную записи. Как только пользователь будет в сети, у бота появится маркер доступа, с помощью которого он может делать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="8f956-169">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="8f956-170">То, что еще нужно, зависит от бота и места, в котором он работает: бот — это зарегистрированное приложение Azure AD, в котором он может иметь собственный https://apps.dev.microsoft.com/ набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="8f956-170">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="8f956-171">Боты информируют о добавлении пользователей в команду или их удалении из нее.</span><span class="sxs-lookup"><span data-stu-id="8f956-171">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="8f956-172">Боты не видят IP-адреса пользователей или другие сведения о ссылке.</span><span class="sxs-lookup"><span data-stu-id="8f956-172">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="8f956-173">Все сведения поступает от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f956-173">All information comes from Microsoft.</span></span> <span data-ttu-id="8f956-174">(Есть одно исключение: если бот реализует собственный интерфейс для выполнения входов, в пользовательском интерфейсе для выполнения входов будут отсылаться IP-адреса пользователей и сведения о ссылке.)</span><span class="sxs-lookup"><span data-stu-id="8f956-174">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="8f956-175">Расширения для сообщений, с другой стороны, видят IP-адреса пользователей и сведения о ссылке.</span><span class="sxs-lookup"><span data-stu-id="8f956-175">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="8f956-176">Рекомендации по приложению (и процесс проверки в AppSource) требуют дискреционного действия при публикации личных сообщений чата пользователям (с POST_MESSAGE_TEAM разрешения) в допустимых целях.</span><span class="sxs-lookup"><span data-stu-id="8f956-176">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="8f956-177">В случае нарушения пользователи могут заблокировать бота, администраторы клиента могут заблокировать приложение, а Корпорация Майкрософт может заблокировать боты централизованно, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="8f956-177">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="8f956-178"><sup>1</sup> Некоторые боты отправляют только сообщения (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="8f956-178"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="8f956-179">Они называются ботами только для уведомлений, но в термине не говорится о разрешенных или не разрешенных действиях ботов. Это означает, что он не хочет показать беседу.</span><span class="sxs-lookup"><span data-stu-id="8f956-179">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="8f956-180">Teams использует это поле для отключения функций пользовательского интерфейса, которые обычно включены; в отличие от ботов, которые делают беседу, возможность бота не ограничена тем, что им разрешено делать.</span><span class="sxs-lookup"><span data-stu-id="8f956-180">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="8f956-181"><sup>2.</sup> Определяется свойством boolean supportsFiles объекта-бота manifest.jsв файле приложения.</span><span class="sxs-lookup"><span data-stu-id="8f956-181"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="8f956-182">Если у бота есть собственный вход, второй (другой) интерфейс согласия при первом входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f956-182">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="8f956-183">В настоящее время разрешения Azure AD, связанные с любыми возможностями приложения Teams (бота, вкладки, соединитела или расширения для обмена сообщениями), полностью отделены от указанных здесь разрешений Teams.</span><span class="sxs-lookup"><span data-stu-id="8f956-183">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="8f956-184">Вкладки</span><span class="sxs-lookup"><span data-stu-id="8f956-184">Tabs</span></span>

<span data-ttu-id="8f956-185">Вкладка — это веб-сайт, работающий в Teams.</span><span class="sxs-lookup"><span data-stu-id="8f956-185">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="8f956-186">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-186">Required permissions</span></span>

<span data-ttu-id="8f956-187">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="8f956-187">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="8f956-188">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-188">Optional permissions</span></span>

<span data-ttu-id="8f956-189">Нет (сейчас)</span><span class="sxs-lookup"><span data-stu-id="8f956-189">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="8f956-190">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8f956-190">Considerations</span></span>

- <span data-ttu-id="8f956-191">Профиль риска для вкладки практически идентичен тому же веб-сайту, который работает на вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="8f956-191">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="8f956-192">Вкладка также возвращает контекст, в котором она работает, включая имя для регистрации и имя пользователя текущего пользователя, ИД объекта Azure AD для текущего пользователя, ИД группы Microsoft 365, в которой она находится (если это группа), ИД клиента и текущий язык пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f956-192">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="8f956-193">Но чтобы эти ID-карты соедились с данными пользователя, на вкладке нужно будет сделать так, чтобы он войди в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8f956-193">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="8f956-194">Соединители</span><span class="sxs-lookup"><span data-stu-id="8f956-194">Connectors</span></span>

<span data-ttu-id="8f956-195">Соединител публикует сообщения в канале при событиях внешней системы.</span><span class="sxs-lookup"><span data-stu-id="8f956-195">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="8f956-196">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-196">Required permissions</span></span>

<span data-ttu-id="8f956-197">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="8f956-197">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="8f956-198">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-198">Optional permissions</span></span>

<span data-ttu-id="8f956-199">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="8f956-199">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="8f956-200">Некоторые соединитетели поддерживают сообщения с действиями, позволяющие пользователям отправлять целевые ответы на них, например, добавляя ответы на проблемы GitHub или добавляя дату на карточку Trello.</span><span class="sxs-lookup"><span data-stu-id="8f956-200">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="8f956-201">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8f956-201">Considerations</span></span>

- <span data-ttu-id="8f956-202">Система, которая публикует сообщения соединителя, не знает, для кого она публикуется или кто получает сообщения: никакие сведения о получателе не будут раскрыты.</span><span class="sxs-lookup"><span data-stu-id="8f956-202">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="8f956-203">(Корпорация Майкрософт — фактический получатель, а не клиент; Корпорация Майкрософт делает фактическую запись для канала.)</span><span class="sxs-lookup"><span data-stu-id="8f956-203">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="8f956-204">При публикации сообщений соединитела в канале никакие данные не покинет корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="8f956-204">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="8f956-205">Соединители, которые поддерживают сообщения с действиями (REPLYTO_CONNECTOR_MESSAGE разрешения), также не могут видеть IP-адрес и сведения о ссылке. эти сведения отправляются в корпорацию Майкрософт, а затем направляются в конечные точки HTTP, которые ранее были зарегистрированы в Корпорации Майкрософт на портале Connectors.</span><span class="sxs-lookup"><span data-stu-id="8f956-205">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="8f956-206">При каждой настройке соединителя для канала создается уникальный URL-адрес для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8f956-206">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="8f956-207">Если этот экземпляр соединителя будет удален, URL-адрес больше не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="8f956-207">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="8f956-208">Сообщения соединителения не могут содержать вложенные файлы.</span><span class="sxs-lookup"><span data-stu-id="8f956-208">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="8f956-209">URL-адрес экземпляра соединителя следует рассматривать как секретный или конфиденциальный: любой, у кого есть этот URL-адрес, может опубликовать его, например адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8f956-209">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="8f956-210">Поэтому существует риск спама или ссылок на фишинговые и вредоносные сайты.</span><span class="sxs-lookup"><span data-stu-id="8f956-210">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="8f956-211">Если это произойдет, владельцы команд смогут удалить экземпляр соединитела.</span><span class="sxs-lookup"><span data-stu-id="8f956-211">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="8f956-212">Если служба, которая отправляет сообщения соединителя, была скомпрометирована и начнет отправлять ссылки на спам, фишинг или вредоносные программы, администратор клиента может запретить создавать новые экземпляры соединителя и корпорация Майкрософт может заблокировать их централизованно.</span><span class="sxs-lookup"><span data-stu-id="8f956-212">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="8f956-213">В настоящее время невозможно узнать, какие соединители поддерживают сообщения с действиями (разрешение REPLYTO_CONNECTOR_MESSAGE почты).</span><span class="sxs-lookup"><span data-stu-id="8f956-213">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="8f956-214">Исходяющие веб-ooks</span><span class="sxs-lookup"><span data-stu-id="8f956-214">Outgoing webhooks</span></span>

<span data-ttu-id="8f956-215">*Исходяющие веб-сайты* создаются на лету владельцами или членами команды.</span><span class="sxs-lookup"><span data-stu-id="8f956-215">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="8f956-216">Они не являются возможностями приложений Teams; эти сведения включаются в сведения о полноте.</span><span class="sxs-lookup"><span data-stu-id="8f956-216">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="8f956-217">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-217">Required permissions</span></span>

<span data-ttu-id="8f956-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="8f956-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="8f956-219">Может получать сообщения от пользователей и отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="8f956-219">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="8f956-220">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="8f956-220">Optional permissions</span></span>

<span data-ttu-id="8f956-221">Нет</span><span class="sxs-lookup"><span data-stu-id="8f956-221">None</span></span>

### <a name="considerations"></a><span data-ttu-id="8f956-222">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8f956-222">Considerations</span></span>

- <span data-ttu-id="8f956-223">Исходяющие веб-сайты похожи на боты, но имеют меньше прав.</span><span class="sxs-lookup"><span data-stu-id="8f956-223">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="8f956-224">Их следует упоминать явным образом, как боты.</span><span class="sxs-lookup"><span data-stu-id="8f956-224">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="8f956-225">При регистрации исходяющего веб-приложения создается секрет, который позволяет исходяющему веб-сайту проверять, является ли отправитель Microsoft Teams, а не вредоносным злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="8f956-225">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="8f956-226">Эта секретная должна оставаться секретной; Любой, у кого есть доступ к этой службе, может получить себя за Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f956-226">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="8f956-227">Если секрет скомпрометирован, исходяходящий веб-сайт можно удалить и повторно создать, и будет создан новый секрет.</span><span class="sxs-lookup"><span data-stu-id="8f956-227">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="8f956-228">Хотя можно создать исходяходящий веб-сайт, который не проверяет секрет, мы рекомендуем вам это сделать.</span><span class="sxs-lookup"><span data-stu-id="8f956-228">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="8f956-229">Кроме получения сообщений и ответов на них, исходящие веб-службы не могут заранее отправлять сообщения, не могут отправлять и получать файлы, они не могут ничего делать, кроме получения сообщений и ответа на них.</span><span class="sxs-lookup"><span data-stu-id="8f956-229">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
