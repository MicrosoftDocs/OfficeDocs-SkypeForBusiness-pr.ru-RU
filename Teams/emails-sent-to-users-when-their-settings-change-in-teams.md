---
title: Электронные письма, отправляемые пользователям при изменении параметров
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Сведения о том, какая информация автоматически передается пользователям по электронной почте при изменении их настроек конференц-связи с телефонным подключением в Microsoft Teams. '
ms.openlocfilehash: 1cef5f0ea8865820f6f6f83e29fe5f66799b70ae
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788693"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="b302f-103">Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b302f-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="b302f-104">Сообщения электронной почты автоматически отправляются пользователям, которые [активированы для участия в аудиоконференциях](set-up-audio-conferencing-in-teams.md) с использованием Майкрософт в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b302f-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="b302f-105">По умолчанию существует четыре типа сообщений электронной почты, которые будут отправляться вашим пользователям, активированным для участия в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="b302f-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b302f-106">Однако если вы хотите ограничить число отправляемых пользователям сообщений, вы можете отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="b302f-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="b302f-107">Аудиоконференция в Microsoft 365 или Office 365 будет отправлять электронную почту пользователей по электронной почте в том случае, если:</span><span class="sxs-lookup"><span data-stu-id="b302f-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="b302f-108">**Им назначена лицензия аудиоконференций, или поставщик услуг аудиоконференций изменен на Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="b302f-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="b302f-109">Это сообщение содержит идентификатор конференции, телефонный номер конференц-связи по умолчанию для собраний, ПИН-код аудиоконференций для пользователя, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое применяется для обновления существующих собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="b302f-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="b302f-110">См. ["Назначение лицензий на надстройки Microsoft Teams"](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) или "Назначение Майкрософт в качестве поставщика аудиоконференций". [](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)</span><span class="sxs-lookup"><span data-stu-id="b302f-110">See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b302f-111">Если в вашей организации разрешены динамические идентификаторы конференции, все запланированные пользователем собрания будут иметь уникальные идентификаторы конференции.</span><span class="sxs-lookup"><span data-stu-id="b302f-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="b302f-112">Вы можете настроить [динамические идентификаторы аудиоконференций в своей организации](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="b302f-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="b302f-113">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="b302f-113">Here is an example of this email:</span></span>

     ![Проверка лицензии Skype для бизнеса](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="b302f-115">Дополнительные информацию о лицензировании см. в лицензировании надстройки [Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="b302f-115">To find out more about licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

- <span data-ttu-id="b302f-116">**Изменяется идентификатор конференции и телефонный номер конференции по умолчанию для пользователя.**</span><span class="sxs-lookup"><span data-stu-id="b302f-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="b302f-117">Это сообщение содержит идентификатор конференции, телефонный номер конференц-связи по умолчанию, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое применяется для обновления существующих собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="b302f-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="b302f-118">Однако это сообщение не содержит ПИН-код аудиоконференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="b302f-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="b302f-119">См. статью [Сброс идентификатора конференции для пользователя](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b302f-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="b302f-120">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="b302f-120">Here is an example of this email:</span></span>

     ![Изменились сведения конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="b302f-122">**Выполнен сброс ПИН-кода аудиоконференций для пользователя.**</span><span class="sxs-lookup"><span data-stu-id="b302f-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="b302f-123">Это сообщение содержит ПИН-код аудиоконференций организатора, существующий идентификатор конференции и телефонный номер конференц-связи по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b302f-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="b302f-124">См. статью [Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b302f-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="b302f-125">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="b302f-125">Here is an example of this email:</span></span>
    
     ![Изменился ПИН-код конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="b302f-127">**Удалена лицензия пользователя, или поставщик услуг аудиоконференций изменен с Майкрософт на другого поставщика или на значение «Нет».**</span><span class="sxs-lookup"><span data-stu-id="b302f-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="b302f-128">Это происходит  при удалении лицензии на аудиоконференцию для пользователя или при установке для поставщика услуг аудиоконференции параметра **"Нет".**</span><span class="sxs-lookup"><span data-stu-id="b302f-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="b302f-129">См. ["Назначение и удаление лицензий для Microsoft 365 для бизнеса".](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="b302f-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="b302f-130">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="b302f-130">Here is an example of this email:</span></span>

     ![Conferencing с dial-in отключается.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="b302f-132">Внесение изменений в сообщения электронной почты, от которых они отправляются</span><span class="sxs-lookup"><span data-stu-id="b302f-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="b302f-133">Вы можете внести изменения в электронные письма, которые автоматически отправляются пользователям.</span><span class="sxs-lookup"><span data-stu-id="b302f-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="b302f-134">По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить отображаемого имени, используя Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b302f-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="b302f-135">Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="b302f-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="b302f-136">Что делать, если вы не хотите, чтобы им отправляли электронную почту?</span><span class="sxs-lookup"><span data-stu-id="b302f-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="b302f-137">Если отключить отправку электронных писем пользователям, сообщения не будут отправляться, даже если пользователю назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="b302f-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="b302f-138">В этом случае код конференции, номер телефона для конференц-связи по умолчанию и, что важнее, ПИН-код аудиоконференции не отправляются пользователю.</span><span class="sxs-lookup"><span data-stu-id="b302f-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="b302f-139">В этом случае вы должны сообщить пользователю, отправив ему отдельное сообщение электронной почты или позвонив ему.</span><span class="sxs-lookup"><span data-stu-id="b302f-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="b302f-140">По умолчанию пользователям отправляются сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференции, вы можете использовать Microsoft Teams или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b302f-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="b302f-141">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b302f-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b302f-142">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="b302f-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="b302f-143">В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста".**</span><span class="sxs-lookup"><span data-stu-id="b302f-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="b302f-144">В области **параметров моста** включите или отключите автоматическое отправку электронных писем пользователям в случае изменения **настроек телефонного дозвона.**</span><span class="sxs-lookup"><span data-stu-id="b302f-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="b302f-145">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b302f-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="b302f-146">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b302f-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="b302f-147">Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="b302f-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b302f-148">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b302f-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b302f-149">По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени, используя Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b302f-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="b302f-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="b302f-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b302f-151">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="b302f-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b302f-152">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="b302f-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b302f-153">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="b302f-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="b302f-154">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b302f-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="b302f-155">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b302f-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b302f-156">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b302f-156">Related topics</span></span>

[<span data-ttu-id="b302f-157">Включение и отключение отправки писем при смене настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="b302f-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="b302f-158">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="b302f-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
