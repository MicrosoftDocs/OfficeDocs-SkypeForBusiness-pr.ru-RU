---
title: Управление настройками аудиоконференций для организации в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о шагах в Microsoft Teams для назначения лицензии конференц-связи с телефонным подключением и идентификатора конференции пользователю и многих других настройках такой конференц-связи. '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884707"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="fb825-103">Управление настройками аудиоконференций для организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb825-103">If you want to manage these settings in Teams, see Manage the Audio Conferencing settings for my organization in Microsoft Teams.</span></span>

<span data-ttu-id="fb825-104">Вам будет проще просматривать все настройки аудиоконференций для Microsoft Teams в одном месте.</span><span class="sxs-lookup"><span data-stu-id="fb825-104">It might be easier for you to see all of the dial-in conferencing settings in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="fb825-105">Назначение лицензии для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb825-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="fb825-106">Вы не можете назначать лицензии с помощью Teams.</span><span class="sxs-lookup"><span data-stu-id="fb825-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="fb825-107">Для этого нужно использовать Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb825-107">You also can use the Office 365 admin center.</span></span> <span data-ttu-id="fb825-108">См. статью [Назначение лицензий Skype для бизнеса и Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="fb825-108">[](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)Assign Skype for Business and Microsoft Teams licenses</span></span> 
  
 <span data-ttu-id="fb825-109">**Назначение лицензии для пользователя**</span><span class="sxs-lookup"><span data-stu-id="fb825-109">\*\*\*\* To assign a license for a user</span></span>
  
1. <span data-ttu-id="fb825-110">Войдите в Office 365 с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="fb825-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="fb825-111">В левой области навигации **Центра администрирования Office 365** перейдите в раздел **Пользователи** > **Активные пользователи** и выберите одного или нескольких пользователей в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb825-111">In the left navigation of the Office 365 admin center, go to Users  Active users > and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb825-112">Если число пользователей, которым вы назначаете лицензии, не превышает 20, вы можете использовать раскрывающийся список **Выбор представления**, а затем выбрать один из вариантов или создать собственное представление.</span><span class="sxs-lookup"><span data-stu-id="fb825-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click Edit, Next twice then select the license and click Submit. You can also assign licenses to multiple users by using Windows Powershell. For for instructions and sample PowerShell scripts, see Assign Skype for Business licenses.</span></span> <span data-ttu-id="fb825-113">Затем выберите пункт **Правка**, дважды нажмите кнопку **Далее**, выберите лицензию и нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="fb825-114">На панели действий в разделе **Лицензии на продукты** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="fb825-115">На странице **Лицензии на продукты** включите **Аудиоконференции** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="fb825-116">Дополнительные сведения см. в статье [Дополнительные лицензии для Skype для бизнеса и Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="fb825-116">For more information, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)</span></span>
    
> [!NOTE]
> <span data-ttu-id="fb825-117">После назначения лицензии Майкрософт может сначала не отображаться в списке как поставщик услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb825-117">After you assign the license, Microsoft might not appear initially in the drop-down as a dial-in conferencing provider.</span></span> <span data-ttu-id="fb825-118">В таком случае выйдите из Центра администрирования Office 365 или нажмите клавиши CTRL+F5 для обновления окна браузера.</span><span class="sxs-lookup"><span data-stu-id="fb825-118">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="fb825-119">Включение или отключение отправки сообщений пользователям аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb825-119">Enable or disable emails from being sent to dial-in users</span></span>

<span data-ttu-id="fb825-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="fb825-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="fb825-121">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fb825-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fb825-122">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="fb825-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="fb825-123">В области **Настройки моста** включите или отключите настройку **Автоматически отправлять пользователям электронные письма при изменении их настроек телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="fb825-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="fb825-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-124">Click **Save**.</span></span>

    
<span data-ttu-id="fb825-125">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fb825-125">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="fb825-126">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="fb825-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="fb825-127">Изменение контактных данных отправителя в сообщениях, отправляемых пользователям</span><span class="sxs-lookup"><span data-stu-id="fb825-127">Change the senders contact information of email messages sent to users</span></span>

<span data-ttu-id="fb825-128">В сообщение, которое отправляется пользователям автоматически, можно внести изменения, включив в него фактический адрес электронной почты и отобразив имя отправителя в составе контактной информации.</span><span class="sxs-lookup"><span data-stu-id="fb825-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="fb825-129">По умолчанию эти сообщения электронной почты отправляются из Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb825-129">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the Set-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="fb825-130">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="fb825-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="fb825-131">Сброс идентификатора конференции для собрания</span><span class="sxs-lookup"><span data-stu-id="fb825-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="fb825-132">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb825-132">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="fb825-133">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-133">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="fb825-134">В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="fb825-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="fb825-135">В окне **Сбросить идентификатор конференции?** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="fb825-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="fb825-136">При этом будет автоматически создан идентификатор конференции и, если функция отправки сообщений включена, пользователям будут отправлены сообщения с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="fb825-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="fb825-137">Эта функция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fb825-137">It's enabled by default.</span></span>

<span data-ttu-id="fb825-138">См. статью [Сброс идентификатора конференции для пользователя](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="fb825-139">Сброс ПИН-кода для организатора собрания</span><span class="sxs-lookup"><span data-stu-id="fb825-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="fb825-140">Каждому из запланированных пользователем собраний назначается уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="fb825-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="fb825-141">Хотя идентификатор конференции создается и назначается пользователю автоматически, в некоторых случаях пользователю может потребоваться использовать в качестве идентификатора конкретный номер, кроме того, пользователи могут забыть или потерять этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="fb825-141">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> 

1. <span data-ttu-id="fb825-142">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb825-142">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="fb825-143">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-143">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="fb825-144">В области **Аудиоконференции** щелкните на элементе **Сбросить ПИН-код** и нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="fb825-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="fb825-145">Пользователи получат сообщение электронной почты при их активации для аудиоконференций или при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="fb825-145">Users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="fb825-146">Однако если автоматическая отправка сообщений электронной почты отключена, пользователь не получит сообщение при сбросе ПИН-кода и эти данные придется пересылать пользователю вручную.</span><span class="sxs-lookup"><span data-stu-id="fb825-146">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="fb825-147">ПИН-код отображается только после его сброса.</span><span class="sxs-lookup"><span data-stu-id="fb825-147">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="fb825-148">После отображения сразу после сброса ПИН-код больше не отображается в свойствах пользователя; вместо него отображается срока \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="fb825-148">Once it's displayed just after being reset, the PIN won't be shown anymore on the user properties and instead \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="fb825-149">См. статью [Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-149">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="fb825-150">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb825-150">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="fb825-151">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb825-151">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="fb825-152">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-152">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="fb825-153">В области **Аудиоконференции** щелкните на элементе **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="fb825-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="fb825-154">Если вы сделаете это, ПИН-код конференц-связи не отправится пользователю.</span><span class="sxs-lookup"><span data-stu-id="fb825-154">When you do this, the dial-in conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="fb825-155">См. статью [Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="fb825-156">Настройка телефонных номеров, включаемых в приглашения</span><span class="sxs-lookup"><span data-stu-id="fb825-156">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="fb825-157">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb825-157">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="fb825-158">Щелкните **Изменить** рядом с элементом **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="fb825-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="fb825-159">В области **Аудиоконференции** можно задать **Платный номер** и, если это разрешено, **Бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="fb825-159">In the Action pane, you can set the Toll number and, if allowed, the Toll-free number.</span></span>

4. <span data-ttu-id="fb825-160">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-160">Click **Save**.</span></span>
    
<span data-ttu-id="fb825-161">См. статью [Настройка телефонных номеров, включаемых в приглашения](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-161">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="fb825-162">Выбор параметров моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb825-162">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="fb825-163">**Настройка взаимодействия при присоединении вызывающих абонентов к собранию**</span><span class="sxs-lookup"><span data-stu-id="fb825-163">\*\*\*\* Set the meeting experience when callers join a meeting</span></span>


1. <span data-ttu-id="fb825-164">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fb825-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fb825-165">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="fb825-165">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="fb825-166">В области **Настройки моста** включите или отключите **уведомления о входе на собрание и выходе из него**.</span><span class="sxs-lookup"><span data-stu-id="fb825-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="fb825-167">Эта настройка включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fb825-167">CDR is enabled by default.</span></span> <span data-ttu-id="fb825-168">Если ее отключить, пользователи, уже присоединившиеся к собранию, по умолчанию не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.</span><span class="sxs-lookup"><span data-stu-id="fb825-168">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="fb825-169">В области **Тип объявлений о входе или выходе** выберите **Тональные сигналы** или **Имена или номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="fb825-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="fb825-170">Если вы выбрали **Имена или номера телефонов**, можно также включить или отключить функцию **Попросите абонентов записывать свои имена перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="fb825-170">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="fb825-171">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-171">Click **Save**.</span></span>

    
<span data-ttu-id="fb825-172">См. статью [Изменение настроек для моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-172">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>
  
 <span data-ttu-id="fb825-173">**Установка длины ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="fb825-173">\*\*\*\* Set the PIN length for meetings</span></span>

1. <span data-ttu-id="fb825-174">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fb825-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fb825-175">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="fb825-175">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="fb825-176">В области **Настройки моста** выберите требуемое число цифр для ПИН-кода в списке **Длина ПИН-кода**, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="fb825-177">ПИН-код должен содержать от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="fb825-177">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="fb825-178">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="fb825-178">The default is 5.</span></span>

    
<span data-ttu-id="fb825-179">См. статью [Изменение настроек для моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-179">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>
  
 <span data-ttu-id="fb825-180">**Включение или отключение отправки сообщения пользователям аудиоконференций**</span><span class="sxs-lookup"><span data-stu-id="fb825-180">\*\*\*\* Enable or disable email from being sent to dial-in users</span></span>


1. <span data-ttu-id="fb825-181">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fb825-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fb825-182">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="fb825-182">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="fb825-183">В области **Настройки моста** включите или отключите настройку **Автоматически отправлять пользователям электронные письма при изменении их настроек аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="fb825-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="fb825-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="fb825-185">Вы также можете отправить пользователю сообщение электронной почты с настройками аудиоконференций, перейдя в свойства аудиоконференций пользователя и выбрав **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="fb825-185">You can also send email to a user with the audio conferencing settings by going to Audio conferencingUsers, selecting the user, and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="fb825-186">В этом случае, пользователям отправляются сообщения, содержащие идентификатор конференции и номер телефона, но не включающие в себя ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="fb825-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="fb825-187">См. статью [Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="fb825-188">Просмотр и задание основного (по умолчанию) и дополнительных (альтернативных) языков для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb825-188">See and set the primary and secondary languages on a dial-in conferencing bridge</span></span>

1. <span data-ttu-id="fb825-189">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fb825-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fb825-190">Выберите телефонный номер в списке и щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-190">Select a number from the list of phone numbers and click **Assign**.</span></span>

3. <span data-ttu-id="fb825-191">Выберите требуемые языки в полях **Язык по умолчанию** и **Альтернативные языки (дополнительно)**.</span><span class="sxs-lookup"><span data-stu-id="fb825-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>


<span data-ttu-id="fb825-192">См. статью [Установка языков автосекретаря для аудиоконференций](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="fb825-193">Просмотр номеров аудиоконференций с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="fb825-193">See dial-in conferencing dial-in numbers</span></span>


1. <span data-ttu-id="fb825-194">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fb825-194">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fb825-195">Выберите телефонный номер в списке и щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb825-195">Select a number from the list of phone numbers and click **Assign**.</span></span> <span data-ttu-id="fb825-196">Здесь вы можете:</span><span class="sxs-lookup"><span data-stu-id="fb825-196">Here you can Discover additional bots.</span></span>
    
  - <span data-ttu-id="fb825-197">просмотреть заданные Office 365 телефонные номера, которые будут использоваться для аудиоконференций;</span><span class="sxs-lookup"><span data-stu-id="fb825-197">You can view the phone numbers that are set by Office 365 to be used for dial-in conferencing.</span></span> 
    
  - <span data-ttu-id="fb825-198">просмотреть расположение и основной язык, которые будет использовать автосекретарь аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb825-198">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="fb825-199">См. статью [Просмотр списка номеров для аудиоконференций](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fb825-199">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fb825-200">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="fb825-200">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="fb825-p112">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="fb825-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fb825-204">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="fb825-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="fb825-205">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb825-205">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="fb825-206">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="fb825-206">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="fb825-207">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fb825-207">Related topics</span></span>

[<span data-ttu-id="fb825-208">Управление настройками аудиоконференций для пользователя</span><span class="sxs-lookup"><span data-stu-id="fb825-208">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


