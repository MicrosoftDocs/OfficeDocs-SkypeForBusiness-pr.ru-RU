---
title: Интеграция Teams и Outlook с электронной почтой
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Узнайте о том, как интеграция Teams и Outlook с электронной почтой, в том числе функции, с которых пользователи могут обмениваться информацией между электронной почтой в Outlook, а также общаться в чате или беседах каналов в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e469017eb9d03cbba55017ca609f49da9ebfe07a
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819365"
---
# <a name="teams-and-outlook-email-integration"></a><span data-ttu-id="ba8eb-103">Интеграция Teams и Outlook с электронной почтой</span><span class="sxs-lookup"><span data-stu-id="ba8eb-103">Teams and Outlook email integration</span></span>

<span data-ttu-id="ba8eb-104">Microsoft Teams включает функции, которые по возможности могут обмениваться информацией между электронной почтой в Outlook, а также чатом или беседами каналов в Teams и всегда быть в верхней части пропущенных бесед.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-104">Microsoft Teams includes features that make it easy for users in your organization to share information between email in Outlook and chat or channel conversations in Teams and to stay on top of missed conversations.</span></span> <span data-ttu-id="ba8eb-105">В этой статье представлены общие сведения об этих средствах и средствах администрирования, которые применяются.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-105">This article gives you an overview of these features and the admin controls that apply.</span></span>

## <a name="share-to-outlook"></a><span data-ttu-id="ba8eb-106">Поделиться в Outlook</span><span class="sxs-lookup"><span data-stu-id="ba8eb-106">Share to Outlook</span></span>

<span data-ttu-id="ba8eb-107">**Поделиться в Outlook позволяет** пользователям отправлять копию беседы Teams по электронной почте в Outlook, не покидая Teams.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-107">**Share to Outlook** lets users share a copy of a Teams conversation to an email in Outlook, without having to leave Teams.</span></span> <span data-ttu-id="ba8eb-108">Эта функция удобна, если пользователям нужно делиться беседами или обновлениями состояния с пользователями за пределами их группы или даже вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-108">This feature is handy if users need to share conversations or status updates with users outside their immediate team or even your organization.</span></span> <span data-ttu-id="ba8eb-109">Перейдите в верхнюю часть беседы в Teams, выберите **̇ ̇ ̇ "Дополнительные** параметры", а затем выберите "Поделиться **в Outlook".**</span><span class="sxs-lookup"><span data-stu-id="ba8eb-109">Go to the top of the conversation in Teams, select **˙˙˙ More options**, and then select **Share to Outlook**.</span></span>  <span data-ttu-id="ba8eb-110">Дополнительные узнать см. в share [to Outlook (Поделиться в Outlook из Teams).](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)</span><span class="sxs-lookup"><span data-stu-id="ba8eb-110">To learn more, see [Share to Outlook from Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).</span></span>

![Снимок экрана: функция "Поделиться в Outlook" в Teams](media/share-to-outlook.png)

<span data-ttu-id="ba8eb-112">Для использования этой функции необходимо, чтобы для пользователя был включен Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-112">To use this feature, Outlook on the web must be turned on for the user.</span></span> <span data-ttu-id="ba8eb-113">Если Outlook в Интернете отключен, параметр "Поделиться в **Outlook"** не отображается в Teams для пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-113">If Outlook on the web is turned off, the **Share to Outlook** option isn't displayed in Teams for the user.</span></span> <span data-ttu-id="ba8eb-114">По шагам, позволяющим включить и отключить [Outlook](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)в Интернете, см. в этом видео.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-114">For steps on how to turn on and turn off Outlook on the web, see [Enable or disable Outlook on the web for a mailbox](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).</span></span>

## <a name="actionable-activity-emails"></a><span data-ttu-id="ba8eb-115">Сообщения электронной почты с действиями</span><span class="sxs-lookup"><span data-stu-id="ba8eb-115">Actionable activity emails</span></span>

<span data-ttu-id="ba8eb-116">Пользователи автоматически получают сообщения о пропущенных действиях, которые помогают им наверстать упущенную беседу в Teams.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-116">Users automatically get actionable missed activity emails which help them to catch up on missed conversations in Teams.</span></span> <span data-ttu-id="ba8eb-117">В сообщениях о пропущенных действиях будут демонстрироваться последние ответы из беседы, включая  сообщения, отправленные после пропущенного сообщения, и пользователи могут нажать кнопку "Ответить", чтобы ответить непосредственно из Outlook.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-117">The missed activity emails show the latest replies from a conversation, including messages that were sent after the missed message, and users can click **Reply** to respond directly from within Outlook.</span></span> <span data-ttu-id="ba8eb-118">Дополнительные узнать см. в [ответ на пропущенные сообщения электронной](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)почты о действиях из Outlook.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-118">To learn more, see [Reply to missed activity emails from Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).</span></span> 

> [!NOTE]
> <span data-ttu-id="ba8eb-119">Эта функция не поддерживается в Outlook для Mac и некоторых более старых версиях Outlook для Windows.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-119">This feature isn't supported in Outlook for Mac or some older versions of Outlook for Windows.</span></span> <span data-ttu-id="ba8eb-120">Дополнительные сведения см. в сообщениях с действиями [в Outlook и группах Office 365.](https://docs.microsoft.com/outlook/actionable-messages/)</span><span class="sxs-lookup"><span data-stu-id="ba8eb-120">For more information, see [Actionable messages in Outlook and Office 365 Groups](https://docs.microsoft.com/outlook/actionable-messages/).</span></span>

![Снимок экрана: сообщение о пропущенных действиях](media/missed-activity-email.png)

![Снимок экрана: ответ на пропущенные сообщения об активности](media/missed-activity-email-reply.png)

<span data-ttu-id="ba8eb-123">Для отключения сообщений электронной почты, которые можно отправлять с помощью параметра **SmtpActionableMessagesEnabled,** можно использовать для этого вместе с параметром [Set-OrganizationConfig.](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="ba8eb-123">You can use the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet together with the **SmtpActionableMessagesEnabled** parameter to turn off actionable emails.</span></span> <span data-ttu-id="ba8eb-124">По умолчанию параметр **SmtpActionableMessagesEnabled** имеет **значение TRUE.**</span><span class="sxs-lookup"><span data-stu-id="ba8eb-124">By default, the **SmtpActionableMessagesEnabled** parameter is set to **true**.</span></span> <span data-ttu-id="ba8eb-125">Если для параметра задан **ложный,** можно отключить сообщения электронной почты с действиями в Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-125">Setting the parameter to **false** turns off actionable email messages across Office 365.</span></span> <span data-ttu-id="ba8eb-126">Для пользователей Teams это  означает, что команда "Ответить" для ответа прямо в Outlook недоступна в пропущенных сообщениях о действиях.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-126">For Teams users, this means that the **Reply** option to respond directly in Outlook isn't available in missed activity emails.</span></span> <span data-ttu-id="ba8eb-127">Вместо них в пропущенных сообщениях о действиях есть команда **"Ответить** в Teams".</span><span class="sxs-lookup"><span data-stu-id="ba8eb-127">Instead, the missed activity emails include a **Reply in Teams** option for users to reply in Teams.</span></span>
