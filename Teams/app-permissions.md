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
description: Администратор может узнать, какие данные и разрешения запрашиваются приложениями Microsoft Teams в организации.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1e6628467d4300130c39a3bade87919fb064a14f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874709"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="5e386-103">Разрешения и рекомендации для приложений Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e386-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="5e386-104">Приложения Microsoft Teams — это способ агрегировать  одну или несколько возможностей в пакет приложения, который можно устанавливать, обновлять и устанавливать.</span><span class="sxs-lookup"><span data-stu-id="5e386-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="5e386-105">К ним относятся следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5e386-105">The capabilities include:</span></span>

- <span data-ttu-id="5e386-106">Боты</span><span class="sxs-lookup"><span data-stu-id="5e386-106">Bots</span></span>
- <span data-ttu-id="5e386-107">Расширения для сообщений</span><span class="sxs-lookup"><span data-stu-id="5e386-107">Messaging extensions</span></span>
- <span data-ttu-id="5e386-108">Вкладки</span><span class="sxs-lookup"><span data-stu-id="5e386-108">Tabs</span></span>
- <span data-ttu-id="5e386-109">Соединители</span><span class="sxs-lookup"><span data-stu-id="5e386-109">Connectors</span></span>

<span data-ttu-id="5e386-110">Пользователи могут получить согласие на доступ к приложениям и управлять им с точки зрения политики.</span><span class="sxs-lookup"><span data-stu-id="5e386-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="5e386-111">Однако в большинстве приложений разрешения и профиль рисков определяются разрешениями и профилями рисков, которые содержит приложение.</span><span class="sxs-lookup"><span data-stu-id="5e386-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="5e386-112">Поэтому в этой статье рассматриваются разрешения и аспекты на уровне возможностей.</span><span class="sxs-lookup"><span data-stu-id="5e386-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="5e386-113">Разрешения, перечисленные ниже в виде букв, например разрешения RECEIVE_MESSAGE и REPLYTO_MESSAGE, не отображаются ни в документации разработчика [Microsoft Teams,](https://aka.ms/teamsdevdocs) ни в разрешениях [для Microsoft Graph.](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)</span><span class="sxs-lookup"><span data-stu-id="5e386-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="5e386-114">Они просто вкратце описательны для целей данной статьи.</span><span class="sxs-lookup"><span data-stu-id="5e386-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="5e386-115">Название</span><span class="sxs-lookup"><span data-stu-id="5e386-115">Title</span></span>   | <span data-ttu-id="5e386-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5e386-116">Description</span></span>    |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5e386-118">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="5e386-118">Decision point</span></span>|<ul><li><span data-ttu-id="5e386-119">Используйте таблицы ниже в качестве руководства, чтобы понять, какие разрешения запрашивают приложения, которые вы изучаете.</span><span class="sxs-lookup"><span data-stu-id="5e386-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Значок, изображающий следующее действие](media/audio_conferencing_image9.png)<br/><span data-ttu-id="5e386-121">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="5e386-121">Next step</span></span>|<ul><li><span data-ttu-id="5e386-122">Изумите приложение или службу, чтобы решить, хотите ли вы разрешить доступ к ним в организации.</span><span class="sxs-lookup"><span data-stu-id="5e386-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="5e386-123">Например, боты отправляют и получают сообщения от пользователей и (за исключением корпоративных) ботов, которые находятся за пределами границы соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5e386-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="5e386-124">Таким образом, все приложения, которые включают бота, требуются эти разрешения и имеет как минимум этот профиль риска.</span><span class="sxs-lookup"><span data-stu-id="5e386-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="5e386-125">См. также [запрос разрешений устройств для вкладки Microsoft Teams.](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)</span><span class="sxs-lookup"><span data-stu-id="5e386-125">See also [Request device permissions for your Microsoft Teams tab](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="5e386-126">Глобальные разрешения и соображения по приложениям</span><span class="sxs-lookup"><span data-stu-id="5e386-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="5e386-127">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-127">Required permissions</span></span>

<span data-ttu-id="5e386-128">Нет</span><span class="sxs-lookup"><span data-stu-id="5e386-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="5e386-129">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-129">Optional permissions</span></span>

<span data-ttu-id="5e386-130">Нет</span><span class="sxs-lookup"><span data-stu-id="5e386-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="5e386-131">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e386-131">Considerations</span></span>

- <span data-ttu-id="5e386-132">Приложение должно сообщать, какие данные используются и для чего они используются в условиях использования и связей политики конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="5e386-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="5e386-133">[Разрешение для конкретного](resource-specific-consent.md) ресурса предоставляет набор разрешений, которые могут запрашиваться приложениями, который отображается на экране установки приложения.</span><span class="sxs-lookup"><span data-stu-id="5e386-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="5e386-134">Дополнительные данные о разрешениях для конкретного ресурса см. в справке [о разрешениях Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="5e386-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="5e386-135">Кроме того, приложениям могут потребоваться разрешения, кроме разрешений на доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="5e386-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="5e386-136">После установки приложения приложение может запрашивать разрешения Graph через запрос на согласие.</span><span class="sxs-lookup"><span data-stu-id="5e386-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="5e386-137">Дополнительные узнать см. в этом видеоролике о разрешениях приложений [Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="5e386-137">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="5e386-138">Вы можете настроить разрешения API и получить согласие на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="5e386-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="5e386-139">Дополнительные информации [см. в рамках программы "Платформа согласия Azure Active Directory".](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="5e386-139">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="5e386-140">Боты и расширения для обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="5e386-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="5e386-141">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-141">Required permissions</span></span>

- <span data-ttu-id="5e386-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="5e386-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="5e386-143">Бот может получать сообщения от пользователей и отвечать на них. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5e386-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="5e386-144">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="5e386-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="5e386-145">После того как пользователь отправит сообщение боту, он может в любое  время отправлять ему прямые сообщения (также называемые упреждающие сообщения).</span><span class="sxs-lookup"><span data-stu-id="5e386-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="5e386-146">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="5e386-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="5e386-147">Боты, добавленные в команды, могут получить список имен и ИД каналов в команде.</span><span class="sxs-lookup"><span data-stu-id="5e386-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="5e386-148">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-148">Optional permissions</span></span>

- <span data-ttu-id="5e386-149">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="5e386-149">IDENTITY.</span></span> <span data-ttu-id="5e386-150">Когда приложение используется в канале, боты приложения могут получать доступ к основным сведениям об удостоверениях участников группы (имя, фамилия, имя-имя пользователя [UPN], адрес электронной почты); при его использования в личном или групповом чате бот может получить доступ к той же информации для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e386-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="5e386-151">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="5e386-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="5e386-152">Позволяет ботам приложения в любое время отправлять прямые (упреждающие) сообщения членам группы, даже если пользователь никогда не общался с ботом.</span><span class="sxs-lookup"><span data-stu-id="5e386-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="5e386-153">Следующие разрешения не являются явными, но подразумеваются под RECEIVE_MESSAGE и REPLYTO_MESSAGE, а также области, в которых можно использовать боты, объявленные в манифесте:</span><span class="sxs-lookup"><span data-stu-id="5e386-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="5e386-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="5e386-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="5e386-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="5e386-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="5e386-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="5e386-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="5e386-157">SEND_FILES, RECEIVE_FILES. <sup>2.</sup> Управляет тем, может ли бот отправлять и получать файлы в личном чате (пока не поддерживается для группового чата или каналов).</span><span class="sxs-lookup"><span data-stu-id="5e386-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="5e386-158">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e386-158">Considerations</span></span>

- <span data-ttu-id="5e386-159">У ботов есть доступ только к командам, в которые они были добавлены, или к пользователям, которые их установили.</span><span class="sxs-lookup"><span data-stu-id="5e386-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="5e386-160">Боты получают только сообщения, в которых их явно упомянули пользователи.</span><span class="sxs-lookup"><span data-stu-id="5e386-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="5e386-161">Эти данные покинет корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="5e386-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="5e386-162">Боты могут отвечать только на беседы, в которых они упомянуты.</span><span class="sxs-lookup"><span data-stu-id="5e386-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="5e386-163">После того как пользователь побеседует с ботом, он сможет отправлять прямые сообщения в любое время.</span><span class="sxs-lookup"><span data-stu-id="5e386-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="5e386-164">Обычно сообщения ботов могут содержать ссылки на фишинговые или вредоносные сайты, но они могут быть заблокированы пользователем, администратором клиента или глобально корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e386-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="5e386-165">Бот может получать (и может хранить) очень основные сведения об удостоверениях участников группы, в которые добавлено приложение, а также отдельных пользователей в личных или групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="5e386-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="5e386-166">Чтобы получить дополнительные сведения об этих пользователях, бот должен потребовать от них войти в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5e386-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="5e386-167">Боты могут извлекать (и хранить) список каналов в группе; эти данные покинет корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="5e386-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="5e386-168">При отправлении файла боту он покидает корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="5e386-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="5e386-169">Для отправки и получения файлов требуется утверждение пользователями для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="5e386-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="5e386-170">По умолчанию боты не могут действовать от имени пользователя, но могут попросить их войти в учетную записи. Как только пользователь будет в сети, у бота появится маркер доступа, с помощью которого он может делать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="5e386-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="5e386-171">То, что еще зависит от бота и где он вошел: бот — это зарегистрированное приложение Azure AD, которое может иметь собственный https://apps.dev.microsoft.com/ набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="5e386-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="5e386-172">Боты информируют о добавлении пользователей в команду или их удалении из нее.</span><span class="sxs-lookup"><span data-stu-id="5e386-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="5e386-173">Боты не видят IP-адреса пользователей или другие сведения для ссылки.</span><span class="sxs-lookup"><span data-stu-id="5e386-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="5e386-174">Все сведения поступает от Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e386-174">All information comes from Microsoft.</span></span> <span data-ttu-id="5e386-175">(Есть одно исключение: если бот реализует собственный интерфейс для выполнения входов, в пользовательском интерфейсе для выполнения входов будут отсылаться IP-адреса пользователей и сведения о ссылке.)</span><span class="sxs-lookup"><span data-stu-id="5e386-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="5e386-176">Расширения для сообщений, с другой стороны, видят IP-адреса пользователей и сведения о ссылке.</span><span class="sxs-lookup"><span data-stu-id="5e386-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="5e386-177">Рекомендации по приложению (и процесс проверки в AppSource) требуют дискреционного действия при публикации личных сообщений чата пользователям (с POST_MESSAGE_TEAM разрешения) в допустимых целях.</span><span class="sxs-lookup"><span data-stu-id="5e386-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="5e386-178">В случае нарушения пользователи могут заблокировать бота, администраторы клиента могут заблокировать приложение, а корпорация Майкрософт может при необходимости заблокировать боты централизованно.</span><span class="sxs-lookup"><span data-stu-id="5e386-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="5e386-179"><sup>1</sup> Некоторые боты отправляют только сообщения (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="5e386-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="5e386-180">Они называются ботами только для уведомлений, но это понятие не относится к разрешенным или не разрешенным ботам. Это означает, что он не хочет показать беседу.</span><span class="sxs-lookup"><span data-stu-id="5e386-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="5e386-181">Teams использует это поле для отключения функций пользовательского интерфейса, которые обычно включены; возможность бота не ограничена возможностью по сравнению с ботами, которые делают сеанс беседы.</span><span class="sxs-lookup"><span data-stu-id="5e386-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="5e386-182"><sup>2.</sup> Определяется свойством boolean supportsFiles объекта-бота manifest.jsв файле приложения.</span><span class="sxs-lookup"><span data-stu-id="5e386-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="5e386-183">Если у бота есть собственный вход, при первом входе пользователя вы сможете получить второй (другой) опыт получения согласия.</span><span class="sxs-lookup"><span data-stu-id="5e386-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="5e386-184">В настоящее время разрешения Azure AD, связанные с любыми возможностями приложения Teams (бота, вкладки, соединитела или расширения для обмена сообщениями), полностью отделены от указанных здесь разрешений Teams.</span><span class="sxs-lookup"><span data-stu-id="5e386-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="5e386-185">Вкладки</span><span class="sxs-lookup"><span data-stu-id="5e386-185">Tabs</span></span>

<span data-ttu-id="5e386-186">Вкладка — это веб-сайт, работающий в Teams.</span><span class="sxs-lookup"><span data-stu-id="5e386-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="5e386-187">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-187">Required permissions</span></span>

<span data-ttu-id="5e386-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="5e386-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="5e386-189">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-189">Optional permissions</span></span>

<span data-ttu-id="5e386-190">Нет (сейчас)</span><span class="sxs-lookup"><span data-stu-id="5e386-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="5e386-191">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e386-191">Considerations</span></span>

- <span data-ttu-id="5e386-192">Профиль риска для вкладки практически идентичен тому же веб-сайту, который работает на вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="5e386-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="5e386-193">Вкладка также возвращает контекст, в котором она работает, включая имя для регистрации и имя пользователя текущего пользователя, ИД объекта Azure AD для текущего пользователя, ИД группы Microsoft 365, в которой она находится (если это группа), ИД клиента и текущий язык пользователя.</span><span class="sxs-lookup"><span data-stu-id="5e386-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="5e386-194">Но чтобы эти ID-карты соедились с данными пользователя, на вкладке необходимо будет войти в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e386-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="5e386-195">Соединители</span><span class="sxs-lookup"><span data-stu-id="5e386-195">Connectors</span></span>

<span data-ttu-id="5e386-196">Соединител публикует сообщения в канале при событиях внешней системы.</span><span class="sxs-lookup"><span data-stu-id="5e386-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="5e386-197">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-197">Required permissions</span></span>

<span data-ttu-id="5e386-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="5e386-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="5e386-199">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-199">Optional permissions</span></span>

<span data-ttu-id="5e386-200">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="5e386-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="5e386-201">Некоторые соединитетели поддерживают сообщения с действиями, позволяющие пользователям отправлять целевые ответы на них, например, добавляя ответы на проблемы GitHub или добавляя дату на карточку Trello.</span><span class="sxs-lookup"><span data-stu-id="5e386-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="5e386-202">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e386-202">Considerations</span></span>

- <span data-ttu-id="5e386-203">Система, которая публикует сообщения соединителя, не знает, кому она публикуется или кто получает сообщения: никакие сведения о получателе не раскрываются.</span><span class="sxs-lookup"><span data-stu-id="5e386-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="5e386-204">(Корпорация Майкрософт — фактический получатель, а не клиент; Корпорация Майкрософт делает фактическую запись для канала.)</span><span class="sxs-lookup"><span data-stu-id="5e386-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="5e386-205">При публикации сообщений соединитела в канале никакие данные не покинет корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="5e386-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="5e386-206">Соединители, которые поддерживают сообщения с действиями (REPLYTO_CONNECTOR_MESSAGE разрешения), также не могут видеть IP-адрес и сведения о ссылке. эти сведения отправляются в корпорацию Майкрософт, а затем направляются в конечные точки HTTP, которые ранее были зарегистрированы в Корпорации Майкрософт на портале Соединители.</span><span class="sxs-lookup"><span data-stu-id="5e386-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="5e386-207">При каждой настройке соединителя для канала создается уникальный URL-адрес для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5e386-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="5e386-208">Если этот экземпляр соединителя будет удален, URL-адрес больше не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="5e386-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="5e386-209">Сообщения соединителения не могут содержать вложенные файлы.</span><span class="sxs-lookup"><span data-stu-id="5e386-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="5e386-210">URL-адрес экземпляра соединителя следует рассматривать как секретный или конфиденциальный: любой, у кого есть этот URL-адрес, может опубликовать его, например адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5e386-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="5e386-211">Поэтому существует риск спама или ссылок на фишинговые и вредоносные сайты.</span><span class="sxs-lookup"><span data-stu-id="5e386-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="5e386-212">Если это произойдет, владельцы команд смогут удалить экземпляр соединитела.</span><span class="sxs-lookup"><span data-stu-id="5e386-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="5e386-213">Если служба, которая отправляет сообщения соединителя, была скомпрометирована и начнет отправлять ссылки на спам, фишинг или вредоносные программы, администратор клиента может запретить создавать новые экземпляры соединителя и корпорация Майкрософт может заблокировать их централизованно.</span><span class="sxs-lookup"><span data-stu-id="5e386-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="5e386-214">В настоящее время невозможно узнать, какие соединители поддерживают сообщения с действиями (разрешение REPLYTO_CONNECTOR_MESSAGE почты).</span><span class="sxs-lookup"><span data-stu-id="5e386-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="5e386-215">Исходяющие веб-ooks</span><span class="sxs-lookup"><span data-stu-id="5e386-215">Outgoing webhooks</span></span>

<span data-ttu-id="5e386-216">*Исходяющие веб-сайты* создаются на лету владельцами или членами команды.</span><span class="sxs-lookup"><span data-stu-id="5e386-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="5e386-217">Они не являются возможностями приложений Teams; эти сведения включаются в сведения о полноте.</span><span class="sxs-lookup"><span data-stu-id="5e386-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="5e386-218">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-218">Required permissions</span></span>

<span data-ttu-id="5e386-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="5e386-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="5e386-220">Может получать сообщения от пользователей и отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="5e386-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="5e386-221">Необязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="5e386-221">Optional permissions</span></span>

<span data-ttu-id="5e386-222">Нет</span><span class="sxs-lookup"><span data-stu-id="5e386-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="5e386-223">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e386-223">Considerations</span></span>

- <span data-ttu-id="5e386-224">Исходяющие веб-сайты похожи на боты, но имеют меньше прав.</span><span class="sxs-lookup"><span data-stu-id="5e386-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="5e386-225">Их следует упоминать явным образом, как боты.</span><span class="sxs-lookup"><span data-stu-id="5e386-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="5e386-226">При регистрации исходяющего веб-приложения создается секрет, который позволяет исходяющему веб-сайту проверять, является ли отправитель Microsoft Teams, а не вредоносным злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="5e386-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="5e386-227">Эта секретная должна оставаться секретной; Любой, у кого есть доступ к этой службе, может получить себя за Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5e386-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="5e386-228">Если секрет скомпрометирован, исходяходящий веб-сайт можно удалить и повторно создать, и будет создан новый секрет.</span><span class="sxs-lookup"><span data-stu-id="5e386-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="5e386-229">Хотя можно создать исходяходящий веб-сайт, который не проверяет секрет, рекомендуется использовать его.</span><span class="sxs-lookup"><span data-stu-id="5e386-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="5e386-230">Кроме получения сообщений и ответа на них, исходящие веб-службы могут не только получать сообщения, но и отвечать на них: они не могут заранее отправлять сообщения, не могут отправлять и получать файлы, они не могут ничего делать, кроме получения сообщений и ответа на них.</span><span class="sxs-lookup"><span data-stu-id="5e386-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
