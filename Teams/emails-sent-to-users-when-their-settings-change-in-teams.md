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
ms.openlocfilehash: 4c4668e671b65a7927434a5ad7c9028d673d47b3
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042866"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="ed325-103">Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed325-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="ed325-104">Сообщения электронной почты автоматически отправляются пользователям, которые [активированы для участия в аудиоконференциях](set-up-audio-conferencing-in-teams.md) с использованием Майкрософт в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="ed325-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="ed325-105">По умолчанию существует четыре типа сообщений электронной почты, которые будут отправляться вашим пользователям, активированным для участия в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="ed325-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="ed325-106">Однако если вы хотите ограничить число отправляемых пользователям сообщений, вы можете отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="ed325-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="ed325-107">Аудиоконференции в Office 365 будут отправлять сообщения пользователям в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="ed325-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="ed325-108">**Им назначена лицензия аудиоконференций, или поставщик услуг аудиоконференций изменен на Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="ed325-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="ed325-109">Это сообщение содержит идентификатор конференции, телефонный номер конференц-связи по умолчанию для собраний, ПИН-код аудиоконференций для пользователя, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое применяется для обновления существующих собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed325-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="ed325-110">В разделе [Назначение лицензий на надстройки Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) или [назначение Microsoft в качестве поставщика видеоконференций](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="ed325-110">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed325-111">Если в вашей организации разрешены динамические идентификаторы конференции, все запланированные пользователем собрания будут иметь уникальные идентификаторы конференции.</span><span class="sxs-lookup"><span data-stu-id="ed325-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="ed325-112">Вы можете настроить [динамические идентификаторы аудиоконференций в своей организации](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="ed325-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="ed325-113">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="ed325-113">Here is an example of this email:</span></span>

     ![Проверка лицензии Skype для бизнеса](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="ed325-115">Дополнительные сведения о лицензировании можно найти в разделе [Лицензирование надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ed325-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="ed325-116">**Изменяется идентификатор конференции и телефонный номер конференции по умолчанию для пользователя.**</span><span class="sxs-lookup"><span data-stu-id="ed325-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="ed325-117">Это сообщение содержит идентификатор конференции, телефонный номер конференц-связи по умолчанию, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое применяется для обновления существующих собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed325-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="ed325-118">Однако это сообщение не содержит ПИН-код аудиоконференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed325-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="ed325-119">См. статью [Сброс идентификатора конференции для пользователя](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ed325-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="ed325-120">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="ed325-120">Here is an example of this email:</span></span>

     ![Изменились сведения конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="ed325-122">**Выполнен сброс ПИН-кода аудиоконференций для пользователя.**</span><span class="sxs-lookup"><span data-stu-id="ed325-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="ed325-123">Это сообщение содержит ПИН-код аудиоконференций организатора, существующий идентификатор конференции и телефонный номер конференц-связи по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed325-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="ed325-124">См. статью [Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ed325-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="ed325-125">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="ed325-125">Here is an example of this email:</span></span>
    
     ![Изменился ПИН-код конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="ed325-127">**Удалена лицензия пользователя, или поставщик услуг аудиоконференций изменен с Майкрософт на другого поставщика или на значение «Нет».**</span><span class="sxs-lookup"><span data-stu-id="ed325-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="ed325-128">Это происходит, когда лицензия на **голосовую конференцию** удаляется от пользователя или при установке поставщика видеоконференций в **положение None (нет**).</span><span class="sxs-lookup"><span data-stu-id="ed325-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="ed325-129">Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="ed325-129">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="ed325-130">Вот пример этого сообщения:</span><span class="sxs-lookup"><span data-stu-id="ed325-130">Here is an example of this email:</span></span>

     ![Конференц-связь с телефонным подключением отключена.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="ed325-132">Внесение изменений в сообщения электронной почты, отправленные им</span><span class="sxs-lookup"><span data-stu-id="ed325-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="ed325-133">Вы можете вносить изменения в сообщение электронной почты, которое автоматически отправляется пользователям.</span><span class="sxs-lookup"><span data-stu-id="ed325-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="ed325-134">По умолчанию отправитель сообщений электронной почты будет находиться в Office 365, но вы можете изменить отображаемое имя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed325-134">By default, the sender of the emails will be from Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="ed325-135">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="ed325-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="ed325-136">Что делать, если вы не хотите отправлять электронную почту?</span><span class="sxs-lookup"><span data-stu-id="ed325-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="ed325-137">Когда вы отключаете отправку сообщений электронной почты пользователям, электронная почта не отправляется, даже если пользователю назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="ed325-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="ed325-138">В этом случае идентификатор конференции, номер телефона конференц-связи по умолчанию и, что важнее, ПИН-код для Конференции с голосовой связью не будет отправлен пользователю.</span><span class="sxs-lookup"><span data-stu-id="ed325-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="ed325-139">В этом случае необходимо сообщить пользователю, отправив ему отдельное сообщение электронной почты или позвонив по нему.</span><span class="sxs-lookup"><span data-stu-id="ed325-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="ed325-140">По умолчанию сообщения будут отправляться пользователям, но если вы не хотите, чтобы они могли получать электронную почту для голосовой конференции, вы можете использовать Microsoft Teams или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed325-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="ed325-141">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ed325-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ed325-142">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="ed325-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ed325-143">В верхней части страницы **мосты** выберите пункт **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="ed325-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ed325-144">В области **Параметры моста** включите или отключите **автоматическую отправку сообщений пользователям при изменении параметров телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="ed325-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="ed325-145">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ed325-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="ed325-146">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ed325-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="ed325-147">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="ed325-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ed325-148">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ed325-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ed325-149">По умолчанию отправитель сообщений электронной почты будет находиться в Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed325-149">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="ed325-p108">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="ed325-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ed325-153">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="ed325-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="ed325-154">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed325-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="ed325-155">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ed325-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ed325-156">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ed325-156">Related topics</span></span>

[<span data-ttu-id="ed325-157">Включение и отключение отправки писем при смене настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="ed325-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="ed325-158">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="ed325-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
