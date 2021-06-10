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
description: 'Узнайте, какие сведения автоматически отправляются пользователям по электронной почте при изменении параметров их параметров для Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120760"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="111ff-103">Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="111ff-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="111ff-104">Сообщения электронной почты автоматически отправляются пользователям, у которых включена аудиоконференция с использованием Майкрософт в качестве поставщика услуг аудиоконференций. [](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="111ff-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="111ff-105">По умолчанию пользователям, для которых включена аудиоконференция, отправляются четыре типа электронной почты.</span><span class="sxs-lookup"><span data-stu-id="111ff-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="111ff-106">Однако если вы хотите ограничить количество сообщений, отправленных пользователям, вы можете отключить их.</span><span class="sxs-lookup"><span data-stu-id="111ff-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="111ff-107">Аудиоконференция в Microsoft 365 или Office 365 отправляет электронную почту пользователям в:</span><span class="sxs-lookup"><span data-stu-id="111ff-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="111ff-108">**Им назначена лицензия на аудиоконференцию или при смене поставщика аудиоконференций на Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="111ff-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="111ff-109">Это сообщение электронной почты содержит код конференции, номер телефона конференции по умолчанию для собраний, ПИН-код аудиоконференции для пользователя, инструкции и ссылку для использования средства обновления собраний по сети Skype для бизнеса, которое используется для обновления существующих собраний для пользователя.</span><span class="sxs-lookup"><span data-stu-id="111ff-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="111ff-110">См. Microsoft Teams лицензии на [надстройки](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) или Назначение Майкрософт в качестве поставщика аудиоконференций. [](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)</span><span class="sxs-lookup"><span data-stu-id="111ff-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="111ff-111">Если в вашей организации включены динамические ИД конференции, у всех собраний пользователя, которые он запланет, будут уникальные.</span><span class="sxs-lookup"><span data-stu-id="111ff-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="111ff-112">Вы можете настроить [динамические ID](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)аудиоконференции в своей организации.</span><span class="sxs-lookup"><span data-stu-id="111ff-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="111ff-113">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="111ff-113">Here is an example of this email:</span></span>

     ![Skype для бизнеса Проверка лицензии](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="111ff-115">Дополнительные информацию о лицензировании см. в Microsoft Teams [лицензировании надстройки.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="111ff-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="111ff-116">**Изменяется ИД конференции или телефонный номер конференции по умолчанию пользователя.**</span><span class="sxs-lookup"><span data-stu-id="111ff-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="111ff-117">Это сообщение электронной почты содержит ИД конференции, номер телефона конференции по умолчанию, а также инструкции и ссылку для использования средства обновления собраний по сети Skype для бизнеса, которое используется для обновления существующих собраний для пользователя.</span><span class="sxs-lookup"><span data-stu-id="111ff-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="111ff-118">Но это сообщение электронной почты не содержит ПИН-код аудиоконференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="111ff-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="111ff-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="111ff-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="111ff-120">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="111ff-120">Here is an example of this email:</span></span>

     ![Сведения о телефонном подмене изменены.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="111ff-122">**Пин-код аудиоконференции пользователя сбрасывается.**</span><span class="sxs-lookup"><span data-stu-id="111ff-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="111ff-123">Это сообщение электронной почты содержит ПИН-код аудиоконференции организатора, существующий код конференции и телефонный номер конференции по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="111ff-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="111ff-124">См. [сброс ПИН-кода аудиоконференции.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="111ff-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="111ff-125">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="111ff-125">Here is an example of this email:</span></span>
    
     ![Изменен ПИН-код для телефонной телефонии.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="111ff-127">**Лицензия пользователя удаляется либо поставщик аудиоконферент изменяется с Майкрософт на другого поставщика или нет.**</span><span class="sxs-lookup"><span data-stu-id="111ff-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="111ff-128">Это происходит  при удалении лицензии пользователя на аудиоконференцию или при установке для поставщика услуг аудиоконференции параметра **Нет.**</span><span class="sxs-lookup"><span data-stu-id="111ff-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="111ff-129">См. [назначение и удаление лицензий Microsoft 365 для бизнеса.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="111ff-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="111ff-130">Вот пример такого сообщения:</span><span class="sxs-lookup"><span data-stu-id="111ff-130">Here is an example of this email:</span></span>

     ![Conferencing dial-in conferencing is turned off.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="111ff-132">Внесение изменений в отправленные им сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="111ff-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="111ff-133">Вы можете вносить изменения в сообщения электронной почты, которые автоматически отправляются пользователям.</span><span class="sxs-lookup"><span data-stu-id="111ff-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="111ff-134">По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить отображаемого имени, используя Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="111ff-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="111ff-135">Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="111ff-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="111ff-136">Что делать, если вы не хотите, чтобы им отправляли электронную почту?</span><span class="sxs-lookup"><span data-stu-id="111ff-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="111ff-137">Если отключить отправку сообщений пользователям, они не будут отправляться даже при назначении пользователю лицензии.</span><span class="sxs-lookup"><span data-stu-id="111ff-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="111ff-138">В этом случае код конференции, номер телефона для конференц-связи по умолчанию и, что важнее, ПИН-код аудиоконференции не будут отправлены пользователю.</span><span class="sxs-lookup"><span data-stu-id="111ff-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="111ff-139">В этом случае вы должны сообщить пользователю, отправив ему отдельное сообщение электронной почты или позвонив ему.</span><span class="sxs-lookup"><span data-stu-id="111ff-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="111ff-140">По умолчанию пользователям отправляются сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференций, вы можете использовать Microsoft Teams или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="111ff-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="111ff-141">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="111ff-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="111ff-142">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="111ff-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="111ff-143">В верхней части страницы **Мосты** конференций щелкните **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="111ff-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="111ff-144">В области **Параметры моста** включите или отключите параметр Автоматически отправлять сообщения электронной почты пользователям при изменении параметров телефонного **дозвона.**</span><span class="sxs-lookup"><span data-stu-id="111ff-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="111ff-145">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="111ff-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="111ff-146">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="111ff-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="111ff-147">Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="111ff-147">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="111ff-148">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="111ff-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="111ff-149">По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="111ff-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="111ff-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="111ff-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="111ff-151">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="111ff-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="111ff-152">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="111ff-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="111ff-153">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="111ff-153">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="111ff-154">[Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="111ff-154">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="111ff-155">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="111ff-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="111ff-156">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="111ff-156">Related topics</span></span>

[<span data-ttu-id="111ff-157">Включение и отключение отправки писем при смене настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="111ff-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="111ff-158">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="111ff-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)