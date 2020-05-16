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
description: Администратор может узнать, какие данные и разрешения приложения Microsoft Teams запрашиваются из своей организации.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f19cbbba6df7c43c69af35893466344e8df1d17d
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256484"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="df587-103">Разрешения и рекомендации для приложений Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df587-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="df587-104">Приложения Microsoft Teams позволяют агрегировать одну или несколько возможностей в _пакет приложения_, который можно установить, обновить и удалить.</span><span class="sxs-lookup"><span data-stu-id="df587-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="df587-105">К этим возможностям относятся:</span><span class="sxs-lookup"><span data-stu-id="df587-105">The capabilities include:</span></span>

- <span data-ttu-id="df587-106">боты;</span><span class="sxs-lookup"><span data-stu-id="df587-106">Bots</span></span>
- <span data-ttu-id="df587-107">расширения для обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="df587-107">Messaging extensions</span></span>
- <span data-ttu-id="df587-108">Вкладки</span><span class="sxs-lookup"><span data-stu-id="df587-108">Tabs</span></span>
- <span data-ttu-id="df587-109">Соединители</span><span class="sxs-lookup"><span data-stu-id="df587-109">Connectors</span></span>

<span data-ttu-id="df587-110">Получение согласия пользователей на приложения и управление этими приложениями ИТ-отделом осуществляется в рамках политики.</span><span class="sxs-lookup"><span data-stu-id="df587-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="df587-111">Тем не менее, в большинстве случаев разрешения и профиль риска для приложения определяются профилями разрешений и риска для возможностей, содержащихся в приложении.</span><span class="sxs-lookup"><span data-stu-id="df587-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="df587-112">Таким образом, основное внимание в этой статье уделяется разрешениям и рекомендациями для уровня возможностей.</span><span class="sxs-lookup"><span data-stu-id="df587-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="df587-113">Разрешения, указанные ниже прописными буквами, например RECEIVE_MESSAGE и REPLYTO_MESSAGE, не указаны в [документации для разработчиков Microsoft Teams](https://aka.ms/teamsdevdocs) или [разрешениях для Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="df587-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="df587-114">Это просто описательные условные обозначения, используемые в рамках данной статьи.</span><span class="sxs-lookup"><span data-stu-id="df587-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="df587-116">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="df587-116">Decision point</span></span>|<ul><li><span data-ttu-id="df587-117">Воспользуйтесь приведенными ниже таблицами, чтобы узнать, какие разрешения запрашиваются для приложений, которые вы изучаете.</span><span class="sxs-lookup"><span data-stu-id="df587-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Значок, изображающий следующее действие](media/audio_conferencing_image9.png)<br/><span data-ttu-id="df587-119">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="df587-119">Next step</span></span>|<ul><li><span data-ttu-id="df587-120">Изучите свое приложение или службу, чтобы решить, нужно ли разрешить доступ к ней в Организации.</span><span class="sxs-lookup"><span data-stu-id="df587-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="df587-121">Например, ботов отправлять и получать сообщения от пользователей и (за исключением настраиваемой корпоративной ботов) они находятся за пределами границы соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="df587-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="df587-122">Таким образом, любое приложение, включающее Bot, должно иметь такие разрешения и имеет этот профиль риска как минимум.</span><span class="sxs-lookup"><span data-stu-id="df587-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="df587-123">Глобальные разрешения и рекомендации для приложений</span><span class="sxs-lookup"><span data-stu-id="df587-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="df587-124">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-124">Required permissions</span></span>

<span data-ttu-id="df587-125">Нет</span><span class="sxs-lookup"><span data-stu-id="df587-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="df587-126">Дополнительные разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-126">Optional permissions</span></span>

<span data-ttu-id="df587-127">Нет</span><span class="sxs-lookup"><span data-stu-id="df587-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="df587-128">Особенности</span><span class="sxs-lookup"><span data-stu-id="df587-128">Considerations</span></span>

- <span data-ttu-id="df587-129">Приложение должно раскрывать используемые данные и данные, для которых они используются, в соответствии с условиями использования и ссылками на правила конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="df587-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="df587-130">[Согласие](resource-specific-consent.md) на доступ к ресурсам предоставляет набор разрешений, которые могут запрашивать приложения, которые отображаются на экране установки приложения.</span><span class="sxs-lookup"><span data-stu-id="df587-130">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="df587-131">Дополнительные сведения о разрешениях на разрешение для конкретных ресурсов можно найти в статье [разрешения на доступ к графике](https://docs.microsoft.com/graph/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="df587-131">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference).</span></span>

- <span data-ttu-id="df587-132">Приложениям также могут потребоваться разрешения, отличные от разрешений согласия для определенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="df587-132">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="df587-133">После установки приложения приложение может запросить разрешения графа с помощью запроса согласия.</span><span class="sxs-lookup"><span data-stu-id="df587-133">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="df587-134">Дополнительные сведения можно найти в разделе [Общие сведения о специальных возможностях приложения Azure AD](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span><span class="sxs-lookup"><span data-stu-id="df587-134">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="df587-135">Вы можете настроить разрешения и согласие на доступ к API на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="df587-135">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="df587-136">Дополнительные сведения можно найти в разделе [инфраструктура согласия Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span><span class="sxs-lookup"><span data-stu-id="df587-136">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="df587-137">Расширения ботов и обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="df587-137">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="df587-138">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-138">Required permissions</span></span>

- <span data-ttu-id="df587-139">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="df587-139">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="df587-140">Bot может получать сообщения от пользователей и отвечать на них. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="df587-140">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="df587-141">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="df587-141">POST_MESSAGE_USER.</span></span> <span data-ttu-id="df587-142">После того как пользователь отправил сообщение на Bot, Bot может отправлять пользователям прямые сообщения (также называемые *активными сообщениями* в любое время).</span><span class="sxs-lookup"><span data-stu-id="df587-142">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="df587-143">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="df587-143">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="df587-144">Ботов, добавленные в Teams, могут получить список имен и идентификаторов каналов в команде.</span><span class="sxs-lookup"><span data-stu-id="df587-144">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="df587-145">Дополнительные разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-145">Optional permissions</span></span>

- <span data-ttu-id="df587-146">Идентифицирующи.</span><span class="sxs-lookup"><span data-stu-id="df587-146">IDENTITY.</span></span> <span data-ttu-id="df587-147">Когда она используется в канале, ботов приложения может получать доступ к основным сведениям о членах группы (имя, фамилию, имя участника-пользователя [UPN], адрес электронной почты); когда он используется в личном или группом чате, Bot может получить доступ к одной и той же информации для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="df587-147">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="df587-148">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="df587-148">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="df587-149">Позволяет ботов приложения отправлять прямые (упреждающее) сообщения любому участнику группы в любое время, даже если пользователь никогда не говорил на Bot.</span><span class="sxs-lookup"><span data-stu-id="df587-149">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="df587-150">Следующие разрешения не являются явными, но подразумеваемые RECEIVE_MESSAGE и REPLYTO_MESSAGE и областями, в которых можно использовать ботов, объявленные в манифесте:</span><span class="sxs-lookup"><span data-stu-id="df587-150">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="df587-151">RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="df587-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="df587-152">RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="df587-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="df587-153">RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="df587-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="df587-154">SEND_FILES RECEIVE_FILES. <sup>2</sup> . определяет, может ли Bot отправлять и получать файлы в личном чате (но не поддерживается для группового чата или каналов).</span><span class="sxs-lookup"><span data-stu-id="df587-154">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="df587-155">Особенности</span><span class="sxs-lookup"><span data-stu-id="df587-155">Considerations</span></span>

- <span data-ttu-id="df587-156">Ботов имеет доступ только к тем группам, в которых они были добавлены, или на пользователей, которые установили их.</span><span class="sxs-lookup"><span data-stu-id="df587-156">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="df587-157">Ботов получать только те сообщения, в которых они явно упоминаются пользователями.</span><span class="sxs-lookup"><span data-stu-id="df587-157">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="df587-158">Эти данные оставляют корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="df587-158">This data leaves the corporate network.</span></span>

- <span data-ttu-id="df587-159">Ботов может отвечать только на беседы, в которых они упоминаются.</span><span class="sxs-lookup"><span data-stu-id="df587-159">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="df587-160">После того как пользователь применяет объект Bot, если он хранит идентификатор пользователя, он может в любое время отправить ему прямые сообщения.</span><span class="sxs-lookup"><span data-stu-id="df587-160">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="df587-161">Теоретически возможно, что сообщения от начала содержат ссылки на фишинговые и вредоносные сайты, но ботов может быть заблокирована пользователем, администратором клиента или глобально корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="df587-161">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="df587-162">Bot может извлекать (и может хранить) очень простые данные идентификации для участников группы, к которым было добавлено приложение, или для отдельных пользователей в личных или групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="df587-162">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="df587-163">Чтобы получить дополнительные сведения об этих пользователях, для роботов необходимо войти в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="df587-163">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="df587-164">Ботов может извлекать (и может сохранять) список каналов в команде; Эти данные оставляют корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="df587-164">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="df587-165">При отправке файла на Bot файл выходит из корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="df587-165">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="df587-166">Для отправки и получения файлов требуется утверждение пользователей для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="df587-166">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="df587-167">По умолчанию ботов не имеет возможности действовать от имени пользователя, но ботов может попросить пользователей выполнить вход. После того как пользователь войдет в систему, у Bot будет маркер доступа, с помощью которого можно делать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="df587-167">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="df587-168">Что эти дополнительные возможности зависят от роботов и от того, где пользователь входит в систему: Bot — это приложение Azure AD, которое зарегистрировано https://apps.dev.microsoft.com/ и может иметь собственный набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="df587-168">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="df587-169">Ботов уведомляются каждый раз, когда пользователи добавляются в группу или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="df587-169">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="df587-170">В ботов не отображаются IP-адреса пользователей и другие сведения об источнике.</span><span class="sxs-lookup"><span data-stu-id="df587-170">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="df587-171">Все данные поступают от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="df587-171">All information comes from Microsoft.</span></span> <span data-ttu-id="df587-172">(Существует одно исключение: Если в Bot реализован собственный вход, Пользовательский интерфейс входа будет просматривать IP-адреса пользователей и сведения о его источнике.)</span><span class="sxs-lookup"><span data-stu-id="df587-172">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="df587-173">Расширения для обмена сообщениями, с другой стороны, видят IP-адреса пользователей и сведения о источнике ссылки.</span><span class="sxs-lookup"><span data-stu-id="df587-173">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="df587-174">Руководство по приложениям (и наш процесс проверки AppSource) требует от пользователей публиковать личные сообщения в чате (с помощью разрешения POST_MESSAGE_TEAM) для выполнения допустимых задач.</span><span class="sxs-lookup"><span data-stu-id="df587-174">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="df587-175">В случае нарушения, пользователи могут блокировать Bot, Администраторы клиентов могут блокировать приложение, и при необходимости Майкрософт может блокировать ботов централизованно.</span><span class="sxs-lookup"><span data-stu-id="df587-175">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="df587-176"><sup>1</sup> в некоторых ботов только отправка сообщений (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="df587-176"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="df587-177">Они называются "только для уведомлений" ботов, но этот термин не указывает на то, что может сделать Bot, или не может делать это, это означает, что робот не хочет показать беседу.</span><span class="sxs-lookup"><span data-stu-id="df587-177">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="df587-178">Teams использует это поле для отключения функций в пользовательском интерфейсе, которые обычно включены. Программа "bot" не ограничена тем, что может быть просвоено по сравнению с ботов, предоставляющей возможности общения.</span><span class="sxs-lookup"><span data-stu-id="df587-178">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="df587-179"><sup>2</sup> , управляемый логическим свойством supportsFiles в объекте Bot в файле manifest. JSON для приложения.</span><span class="sxs-lookup"><span data-stu-id="df587-179"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="df587-180">Если у робота есть собственный вход, существует вторая — другая — режим согласия при первом входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="df587-180">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="df587-181">В настоящее время разрешения Azure AD, связанные с какими-либо возможностями в приложении Teams (Bot, вкладка, соединитель или расширение для обмена сообщениями), полностью отделены от разрешений Teams, перечисленных здесь.</span><span class="sxs-lookup"><span data-stu-id="df587-181">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="df587-182">Вкладки</span><span class="sxs-lookup"><span data-stu-id="df587-182">Tabs</span></span>

<span data-ttu-id="df587-183">Вкладка — это веб-сайт, работающий внутри Teams.</span><span class="sxs-lookup"><span data-stu-id="df587-183">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="df587-184">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-184">Required permissions</span></span>

<span data-ttu-id="df587-185">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="df587-185">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="df587-186">Дополнительные разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-186">Optional permissions</span></span>

<span data-ttu-id="df587-187">Нет (сейчас)</span><span class="sxs-lookup"><span data-stu-id="df587-187">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="df587-188">Особенности</span><span class="sxs-lookup"><span data-stu-id="df587-188">Considerations</span></span>

- <span data-ttu-id="df587-189">Профиль риска для вкладки почти идентичен тому же веб-сайту, на котором работает вкладка браузера.</span><span class="sxs-lookup"><span data-stu-id="df587-189">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="df587-190">Вкладка также получает контекст, в котором она выполняется, включая имя для входа и UPN текущего пользователя, идентификатор объекта Azure AD для текущего пользователя, идентификатор группы Office 365, в которой она находится (если это группа), идентификатор клиента и текущий языковой стандарт пользователя.</span><span class="sxs-lookup"><span data-stu-id="df587-190">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Office 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="df587-191">Тем не менее, чтобы сопоставить эти идентификаторы со сведениями о пользователе, вкладка должна настроить вход пользователя в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df587-191">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="df587-192">Плат</span><span class="sxs-lookup"><span data-stu-id="df587-192">Connectors</span></span>

<span data-ttu-id="df587-193">Соединитель отправляет сообщения в канал, когда возникают события во внешней системе.</span><span class="sxs-lookup"><span data-stu-id="df587-193">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="df587-194">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-194">Required permissions</span></span>

<span data-ttu-id="df587-195">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="df587-195">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="df587-196">Дополнительные разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-196">Optional permissions</span></span>

<span data-ttu-id="df587-197">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="df587-197">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="df587-198">Некоторые соединители поддерживают транзактные сообщения, которые позволяют пользователям отправлять целевые ответы на соединительные сообщения, например, добавив ответ на вопрос GitHub или добавив дату в карточку Trello.</span><span class="sxs-lookup"><span data-stu-id="df587-198">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="df587-199">Особенности</span><span class="sxs-lookup"><span data-stu-id="df587-199">Considerations</span></span>

- <span data-ttu-id="df587-200">Система, на которой размещаются посылаемые сообщения, не знает, кто отправляет сообщение или кто получает сообщения: никакие сведения о получателе не будут закрыты.</span><span class="sxs-lookup"><span data-stu-id="df587-200">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="df587-201">(Microsoft — это реальный получатель, а не клиент; Корпорация Майкрософт производит фактическое сообщение в канале.)</span><span class="sxs-lookup"><span data-stu-id="df587-201">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="df587-202">Данные не отправляются в корпоративную сеть при размещении в канале сообщений в виде соединителя.</span><span class="sxs-lookup"><span data-stu-id="df587-202">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="df587-203">Соединители, поддерживающие транзактные сообщения (REPLYTO_CONNECTOR_MESSAGE разрешение), также не видят сведения об IP-адресе и источнике ссылки. Эти данные отправляются в корпорацию Майкрософт, а затем пересылаются в конечные точки HTTP, которые ранее были зарегистрированы в Microsoft на портале соединителей.</span><span class="sxs-lookup"><span data-stu-id="df587-203">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="df587-204">Каждый раз, когда для канала настроена соединительная линия, создается уникальный URL-адрес для этого экземпляра соединителя.</span><span class="sxs-lookup"><span data-stu-id="df587-204">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="df587-205">Если этот экземпляр соединителя удален, этот URL-адрес больше нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="df587-205">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="df587-206">В сообщениях подключателя не может быть вложенных файлов.</span><span class="sxs-lookup"><span data-stu-id="df587-206">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="df587-207">URL-адрес экземпляра соединителя должен рассматриваться как секретный или конфиденциальный: любой пользователь, у которого есть этот URL-адрес, может публиковать его, например адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="df587-207">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="df587-208">Таким образом, существует риск нежелательной почты или ссылок на фишинговые и вредоносные сайты.</span><span class="sxs-lookup"><span data-stu-id="df587-208">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="df587-209">Если это произошло, владельцы групп могут удалить экземпляр соединителя.</span><span class="sxs-lookup"><span data-stu-id="df587-209">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="df587-210">Если служба, передающая сообщения соединителя, была скомпрометирована и начата отправка нежелательной почты/фишинга/вредоносных программ, администратор клиента может предотвратить создание новых экземпляров соединителя, и корпорация Майкрософт сможет централизованно заблокировать их.</span><span class="sxs-lookup"><span data-stu-id="df587-210">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="df587-211">В настоящее время невозможно узнать, какие соединители поддерживают транзактные сообщения (REPLYTO_CONNECTOR_MESSAGE разрешение).</span><span class="sxs-lookup"><span data-stu-id="df587-211">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="df587-212">Исходящие веб-перехватчики</span><span class="sxs-lookup"><span data-stu-id="df587-212">Outgoing webhooks</span></span>

<span data-ttu-id="df587-213">*Исходящие веб-перехватчики* создаются на лету владельцами группы или участниками группы.</span><span class="sxs-lookup"><span data-stu-id="df587-213">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="df587-214">Они не являются возможностями приложений Teams; Эта информация включена для полноты.</span><span class="sxs-lookup"><span data-stu-id="df587-214">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="df587-215">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-215">Required permissions</span></span>

<span data-ttu-id="df587-216">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="df587-216">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="df587-217">Может получать сообщения от пользователей и отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="df587-217">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="df587-218">Дополнительные разрешения</span><span class="sxs-lookup"><span data-stu-id="df587-218">Optional permissions</span></span>

<span data-ttu-id="df587-219">Нет</span><span class="sxs-lookup"><span data-stu-id="df587-219">None</span></span>

### <a name="considerations"></a><span data-ttu-id="df587-220">Особенности</span><span class="sxs-lookup"><span data-stu-id="df587-220">Considerations</span></span>

- <span data-ttu-id="df587-221">Исходящие веб-перехватчики похожи на ботов, но имеют меньшие полномочия.</span><span class="sxs-lookup"><span data-stu-id="df587-221">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="df587-222">Они должны быть явно упомянуты, как ботов.</span><span class="sxs-lookup"><span data-stu-id="df587-222">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="df587-223">При регистрации исходящего веб-перехватчика генерируется секретный код, который позволяет исходящему веб-перехватчику проверить, что отправитель является Microsoft Teams, а не злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="df587-223">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="df587-224">Этот секрет должен оставаться секретным; любой пользователь, у которого есть доступ к нему, может олицетворять Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="df587-224">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="df587-225">Если секретный код скомпрометирован, исходящий веб-перехватчик можно удалить и создать заново, и будет создан новый секрет.</span><span class="sxs-lookup"><span data-stu-id="df587-225">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="df587-226">Несмотря на то, что вы можете создать исходящий веб-перехватчик, который не должен проверять секретный код, рекомендуется использовать его.</span><span class="sxs-lookup"><span data-stu-id="df587-226">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="df587-227">Исходящие веб-перехватчики, кроме приема сообщений и ответов на них, не могут быть неактивными, они не могут отправлять и получать файлы, но не могут выполнять какие-либо действия в ботов, кроме приема сообщений и ответов на них.</span><span class="sxs-lookup"><span data-stu-id="df587-227">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
