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
description: 'Сведения о том, какие данные автоматически отправляются пользователям по электронной почте при изменении настроек для этой цели в Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120760"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="9a743-103">Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a743-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="9a743-104">Сообщения электронной почты будут автоматически [](set-up-audio-conferencing-in-teams.md) отправляться пользователям, у которых в качестве поставщика услуг аудиоконференции включена аудиоконференция с Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a743-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="9a743-105">По умолчанию существует четыре типа сообщений электронной почты, которые отправляются пользователям, для которых включена аудиоконференция.</span><span class="sxs-lookup"><span data-stu-id="9a743-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9a743-106">Но если вы хотите ограничить количество сообщений, отключите их.</span><span class="sxs-lookup"><span data-stu-id="9a743-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="9a743-107">Аудиоконференция в Microsoft 365 или Office 365 будет отправлять электронную почту пользователей по электронной почте в том случае, если:</span><span class="sxs-lookup"><span data-stu-id="9a743-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="9a743-108">**Им назначена лицензия на аудиоконференцию или при смене поставщика услуг аудиоконференции на Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="9a743-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="9a743-109">Это сообщение электронной почты содержит код конференции, номер телефона конференции по умолчанию для собраний, ПИН-код аудиоконференции для пользователя, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое используется для обновления существующих собраний для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a743-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="9a743-110">См. ["Назначение лицензий на надстройки Microsoft Teams"](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) или "Назначение Майкрософт в качестве поставщика аудиоконференций". [](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)</span><span class="sxs-lookup"><span data-stu-id="9a743-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a743-111">Если в вашей организации включены динамические ИД конференц-залов, всем собраниям пользователя, которые он запланил, будут уникальные.</span><span class="sxs-lookup"><span data-stu-id="9a743-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="9a743-112">Вы можете настроить динамические ИД аудиоконференций [в своей организации.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)</span><span class="sxs-lookup"><span data-stu-id="9a743-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="9a743-113">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="9a743-113">Here is an example of this email:</span></span>

     ![Проверка лицензии Skype для бизнеса](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="9a743-115">Дополнительные информацию о лицензировании см. в лицензировании надстройки [Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="9a743-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="9a743-116">**Изменяется ИД конференции или телефонный номер конференции по умолчанию пользователя.**</span><span class="sxs-lookup"><span data-stu-id="9a743-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="9a743-117">Это сообщение электронной почты содержит номер конференции, номер телефона конференции по умолчанию, инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое используется для обновления существующих собраний для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a743-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="9a743-118">Но это сообщение электронной почты не содержит ПИН-код аудиоконференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a743-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="9a743-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9a743-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="9a743-120">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="9a743-120">Here is an example of this email:</span></span>

     ![Изменены сведения о телефонной телефонной телефонии.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="9a743-122">**ПИН-код аудиоконференции пользователя сбрасывается.**</span><span class="sxs-lookup"><span data-stu-id="9a743-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="9a743-123">Это сообщение электронной почты содержит ПИН-код аудиоконференции организатора, существующий код конференции и номер телефона конференции по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a743-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="9a743-124">См. ["Сброс ПИН-кода аудиоконференции".](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9a743-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="9a743-125">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="9a743-125">Here is an example of this email:</span></span>
    
     ![Изменен ПИН-код для телефонной телефонной телефонии.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="9a743-127">**Лицензия пользователя удаляется или если поставщик услуг аудиоконференций изменяется с Microsoft на другого поставщика или "Нет".**</span><span class="sxs-lookup"><span data-stu-id="9a743-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="9a743-128">Это происходит  при удалении лицензии на аудиоконференцию для пользователя или при установке для поставщика услуг аудиоконференции параметра **"Нет".**</span><span class="sxs-lookup"><span data-stu-id="9a743-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="9a743-129">См. ["Назначение и удаление лицензий для Microsoft 365 для бизнеса".](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="9a743-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="9a743-130">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="9a743-130">Here is an example of this email:</span></span>

     ![Conferencing с dial-in отключается.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="9a743-132">Внесение изменений в сообщения электронной почты, от которых они отправляются</span><span class="sxs-lookup"><span data-stu-id="9a743-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="9a743-133">Вы можете внести изменения в электронные письма, которые автоматически отправляются пользователям.</span><span class="sxs-lookup"><span data-stu-id="9a743-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="9a743-134">По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить отображаемого имени, используя Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a743-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="9a743-135">Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="9a743-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="9a743-136">Что делать, если вы не хотите, чтобы им отправляли электронную почту?</span><span class="sxs-lookup"><span data-stu-id="9a743-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="9a743-137">Если отключить отправку электронных писем пользователям, сообщения не будут отправляться, даже если пользователю назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="9a743-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="9a743-138">В этом случае код конференции, номер телефона для конференц-связи по умолчанию и, что важнее, ПИН-код аудиоконференции не отправляются пользователю.</span><span class="sxs-lookup"><span data-stu-id="9a743-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="9a743-139">В этом случае вы должны сообщить пользователю, отправив ему отдельный адрес электронной почты или позвонив ему.</span><span class="sxs-lookup"><span data-stu-id="9a743-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="9a743-140">По умолчанию пользователям отправляются сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференции, вы можете использовать Microsoft Teams или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a743-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="9a743-141">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="9a743-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9a743-142">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="9a743-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9a743-143">В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста".**</span><span class="sxs-lookup"><span data-stu-id="9a743-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9a743-144">В области **параметров моста** включите или отключите автоматическое отправку электронных писем пользователям в случае изменения **настроек телефонного дозвона.**</span><span class="sxs-lookup"><span data-stu-id="9a743-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="9a743-145">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a743-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="9a743-146">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9a743-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9a743-147">Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="9a743-147">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9a743-148">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9a743-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9a743-149">По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени, используя Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a743-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="9a743-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9a743-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9a743-151">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="9a743-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9a743-152">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9a743-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9a743-153">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="9a743-153">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="9a743-154">[Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9a743-154">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="9a743-155">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9a743-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9a743-156">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9a743-156">Related topics</span></span>

[<span data-ttu-id="9a743-157">Включение и отключение отправки писем при смене настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="9a743-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="9a743-158">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="9a743-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)