---
title: Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, какая информация автоматически передается пользователям по электронной почте при изменении их настроек конференц-связи с телефонным подключением в Microsoft Teams. '
ms.openlocfilehash: 67e4945095b9ed7e69632741e04b4ac384741feb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883421"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="c5833-103">Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5833-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="c5833-104">Сообщения электронной почты автоматически отправляются пользователям, которые [активированы для участия в аудиоконференциях](set-up-audio-conferencing-in-teams.md) с использованием Майкрософт в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="c5833-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="c5833-105">По умолчанию существует четыре типа сообщений электронной почты, которые будут отправляться вашим пользователям, активированным для участия в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="c5833-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c5833-106">Однако если вы хотите ограничить число отправляемых пользователям сообщений, вы можете отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="c5833-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="c5833-107">Аудиоконференции в Office 365 будут отправлять сообщения пользователям в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="c5833-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="c5833-108">**Им назначена лицензия аудиоконференций, или поставщик услуг аудиоконференций изменен на Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="c5833-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="c5833-109">Это сообщение содержит идентификатор конференции, телефонный номер конференц-связи по умолчанию для собраний, ПИН-код аудиоконференций для пользователя, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое применяется для обновления существующих собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5833-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c5833-110">В разделе [Назначение групп Майкрософт лицензий](assign-teams-licenses.md) или [Назначить Microsoft в качестве поставщика аудиоконференций](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="c5833-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5833-111">Если в вашей организации разрешены динамические идентификаторы конференции, все запланированные пользователем собрания будут иметь уникальные идентификаторы конференции.</span><span class="sxs-lookup"><span data-stu-id="c5833-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c5833-112">Вы можете настроить [динамические идентификаторы аудиоконференций в своей организации](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="c5833-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="c5833-113">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c5833-113">Here is an example of this email:</span></span>

     ![Проверка лицензии Skype для бизнеса](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="c5833-115">Для получения дополнительных сведений о лицензировании см. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c5833-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="c5833-116">**Изменяется идентификатор конференции и телефонный номер конференции по умолчанию для пользователя.**</span><span class="sxs-lookup"><span data-stu-id="c5833-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="c5833-117">Это сообщение содержит идентификатор конференции, телефонный номер конференц-связи по умолчанию, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое применяется для обновления существующих собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5833-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c5833-118">Однако это сообщение не содержит ПИН-код аудиоконференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5833-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="c5833-119">См. статью [Сброс идентификатора конференции для пользователя](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c5833-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="c5833-120">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c5833-120">Here is an example of this email:</span></span>

     ![Изменились сведения конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="c5833-122">**Выполнен сброс ПИН-кода аудиоконференций для пользователя.**</span><span class="sxs-lookup"><span data-stu-id="c5833-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="c5833-123">Это сообщение содержит ПИН-код аудиоконференций организатора, существующий идентификатор конференции и телефонный номер конференц-связи по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5833-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="c5833-124">См. статью [Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c5833-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="c5833-125">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c5833-125">Here is an example of this email:</span></span>
    
     ![Изменился ПИН-код конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="c5833-127">**Удалена лицензия пользователя, или поставщик услуг аудиоконференций изменен с Майкрософт на другого поставщика или на значение «Нет».**</span><span class="sxs-lookup"><span data-stu-id="c5833-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="c5833-128">Это происходит при удалении лицензии **Аудиоконференций** для пользователя или при изменении поставщика услуг аудиоконференций с Майкрософт на стороннего поставщика или на значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="c5833-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="c5833-129">Это сообщение содержит инструкции и сведения для пользователя по использованию средства обновления собраний Skype для бизнеса Online для удаление определенной информации об аудиоконференциях, например телефонного номера конференц-связи по умолчанию или идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="c5833-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>

    <span data-ttu-id="c5833-130">См. статью [Назначение и удаление лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c5833-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="c5833-131">Далее приведен пример этого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c5833-131">Here is an example of this email:</span></span>

     ![Отключена конференц-связь с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="c5833-133">Изменение отправляемых сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="c5833-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="c5833-134">Можно внести изменения в сообщение электронной почты, которое отправляется пользователям автоматически.</span><span class="sxs-lookup"><span data-stu-id="c5833-134">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="c5833-135">По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить отображаемое имя, с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5833-135">By default, the sender of the emails will be from Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="c5833-136">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c5833-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="c5833-137">Что делать, если отправлять сообщение не требуется?</span><span class="sxs-lookup"><span data-stu-id="c5833-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="c5833-138">Если отключить отправку сообщений пользователям, они не будут отправляться даже при назначении пользователю лицензии.</span><span class="sxs-lookup"><span data-stu-id="c5833-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="c5833-139">В этом случае идентификатор конференции, телефонный номер конференц-связи по умолчанию и, что более важно, ПИН-код аудиоконференций пользователю не отправляются.</span><span class="sxs-lookup"><span data-stu-id="c5833-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="c5833-140">В этом случае вам нужно сообщить все это пользователю, отправив отдельное сообщение или позвонив ему.</span><span class="sxs-lookup"><span data-stu-id="c5833-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="c5833-141">По умолчанию сообщения отправляются пользователям, но вы можете отключить сообщения по аудиоконференциям с помощью Microsoft Teams или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5833-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="c5833-142">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью центра администрирования группами Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="c5833-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c5833-143">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="c5833-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c5833-144">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="c5833-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c5833-145">В области **Настройки моста** включите или отключите настройку **Автоматически отправлять пользователям электронные письма при изменении их настроек телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="c5833-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="c5833-146">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c5833-146">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="c5833-147">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c5833-147">**Using Windows PowerShell**</span></span>

<span data-ttu-id="c5833-148">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c5833-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c5833-149">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c5833-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c5833-150">По умолчанию эти сообщения электронной почты отправляются из Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5833-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="c5833-p109">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="c5833-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c5833-154">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="c5833-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="c5833-155">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5833-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="c5833-156">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c5833-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c5833-157">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c5833-157">Related topics</span></span>

[<span data-ttu-id="c5833-158">Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="c5833-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="c5833-159">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="c5833-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
