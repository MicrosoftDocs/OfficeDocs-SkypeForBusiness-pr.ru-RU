---
title: Управление параметрами звука конференц-связи для организации в Скайп для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'В разделе Скайп для бизнеса в Интернет действия для назначения идентификатора лицензии и конференц-связь с телефонным пользователя и многие другие параметры конференц-связи. '
ms.openlocfilehash: fe5de9aa17a242337776c04178fe36bab24ca8f9
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490813"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="a0cda-103">Управление параметрами звука конференц-связи для организации в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="a0cda-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="a0cda-104">Если вы хотите управлять эти параметры в группах, ознакомьтесь со [управлять параметрами звука конференц-связи для организации в группах Microsoft](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a0cda-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="a0cda-105">Можно легко видеть все параметры аудиоконференций для Скайп для бизнеса в одном месте.</span><span class="sxs-lookup"><span data-stu-id="a0cda-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span> 

  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="a0cda-106">Назначение лицензии на аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="a0cda-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="a0cda-107">Невозможно присвоить лицензии с **Скайп по центру администрирования бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="a0cda-108">Необходимо использовать Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0cda-108">You must use the Office 365 admin center.</span></span> <span data-ttu-id="a0cda-109">Назначение пользователю идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="a0cda-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="a0cda-110">**Назначение лицензии для пользователя**</span><span class="sxs-lookup"><span data-stu-id="a0cda-110">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="a0cda-111">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-112">В левой области переходов **центра администрирования Office 365**, перейдите к **пользователям** > **активных пользователей**и выберите одного или нескольких пользователей из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0cda-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a0cda-113">Если при назначении лицензии до 20 пользователями в то же время, можно использовать **Выберите представление** раскрывающемся списке а затем выберите один из параметров или создание собственного представления.</span><span class="sxs-lookup"><span data-stu-id="a0cda-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="a0cda-114">Затем нажмите кнопку **Изменить**, **Далее** два раза а затем выберите лицензии и нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="a0cda-115">Также можно назначить лицензий для нескольких пользователей с помощью Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="a0cda-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="a0cda-116">Инструкции и примеры скриптов PowerShell в разделе [Назначение Скайп для лицензий на бизнес](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="a0cda-117">На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-117">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="a0cda-118">На странице **Лицензий на продукт** Включение **Звука конференц-связи** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="a0cda-119">Для получения дополнительных сведений о лицензировании см [Скайп для лицензирования дополнительный компонент Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a0cda-120">После назначения лицензии Майкрософт могут отсутствовать изначально в списке как поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="a0cda-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="a0cda-121">В таком случае выйдите из центра администрирования Office 365 или нажмите сочетание клавиш CTRL+F5 для обновления окна браузера.</span><span class="sxs-lookup"><span data-stu-id="a0cda-121">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="a0cda-122">Включение или отключение сообщений, отправляемых в пользователей аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="a0cda-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="a0cda-123">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a0cda-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a0cda-124">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-124">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-125">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a0cda-126">На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="a0cda-127">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-127">Click **Save**.</span></span>
    
    <span data-ttu-id="a0cda-128">Также можно отправить по электронной почте для пользователя с помощью параметров аудиоконференций, перейдя к свойствам аудиоконференций пользователя и нажав кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="a0cda-129">Конференции по умолчанию и идентификатор аудиоконференций номер телефона включен в приглашении на собрание, но не ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="a0cda-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="a0cda-130">[Использование Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="a0cda-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
<span data-ttu-id="a0cda-131">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a0cda-131">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="a0cda-132">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="a0cda-132">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="a0cda-133">[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) можно использовать для управления другими параметрами для вашей организации, включая электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a0cda-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="a0cda-134">Изменить сведения о контакте отправителя в сообщениях электронной почты, отправляемое пользователю</span><span class="sxs-lookup"><span data-stu-id="a0cda-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="a0cda-135">Можно внести изменения в сообщение электронной почты, которое отправляется автоматически для пользователей, включая адрес электронной почты фактические и отображаемое имя отправителя контактные данные.</span><span class="sxs-lookup"><span data-stu-id="a0cda-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="a0cda-136">По умолчанию, отправителя сообщения электронной почты — Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0cda-136">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="a0cda-137">Чтобы изменить адрес электронной почты, который отправляет сообщение электронной почты для пользователей, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="a0cda-137">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="a0cda-138">Введите адрес электронной почты с помощью параметра _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="a0cda-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="a0cda-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="a0cda-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="a0cda-140">Установите для параметра _SendEmailOverride_ значение _True_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="a0cda-141">Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a0cda-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="a0cda-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="a0cda-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="a0cda-143">Командлет [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) можно использовать для управления другими параметрами для вашей организации, включая электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a0cda-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="a0cda-144">В разделе [сообщения электронной почты, которые отправляются пользователям при изменении их параметров звука конференц-связи, автоматически](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="a0cda-145">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="a0cda-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="a0cda-146">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-147">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-148">В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и в области действий в разделе **Идентификатор конференции**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="a0cda-149">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="a0cda-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="a0cda-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="a0cda-151">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="a0cda-151">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="a0cda-152">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="a0cda-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a0cda-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="a0cda-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="a0cda-154">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="a0cda-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="a0cda-155">Чтобы узнать, как для загрузки, установки и запуска Скайп для бизнеса средство обновления собрания, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](http://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, собрания Средство миграции (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="a0cda-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="a0cda-156">Сброс ПИН-кода организатора конференции</span><span class="sxs-lookup"><span data-stu-id="a0cda-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="a0cda-157">Сброс ПИН-кода организатора конференции</span><span class="sxs-lookup"><span data-stu-id="a0cda-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="a0cda-158">Каждое собрание, который пользователь планирует будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="a0cda-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="a0cda-159">Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="a0cda-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="a0cda-160">Скайп по центру администрирования бизнеса и Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="a0cda-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="a0cda-161">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-161">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-162">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a0cda-163">Щелкните элемент **Пользователи**, а затем выберите пользователя, который требуется сбросить ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="a0cda-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="a0cda-164">В области действий в разделе **ПИН-код**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-164">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="a0cda-165">Пользователи будут получать сообщения электронной почты с свой ПИН-код, когда они будет включена поддержка аудиоконференций или когда сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="a0cda-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="a0cda-166">Но если вы отключили автоматически отправка по электронной почте, не будут отправляться электронной почты сброс ПИН-кода и необходимо вручную отправлять ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0cda-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="a0cda-167">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="a0cda-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="a0cda-168">После отображения сразу после сброса ПИН-код не будет больше отображаться на свойства пользователя; Вместо этого \*\*\* будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="a0cda-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="a0cda-169">В разделе [Сброс аудиоконференций ПИН-кода](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="a0cda-170">Отправить сообщение электронной почты с информацией аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="a0cda-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="a0cda-171">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-171">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-172">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a0cda-173">Щелкните элемент **Пользователи**, а затем выберите пользователя, который требуется сбросить ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="a0cda-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="a0cda-174">На панели действий щелкните **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-174">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a0cda-175">При этом аудиоконференций ПИН-код не отправляется для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0cda-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="a0cda-176">[Использование Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="a0cda-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="a0cda-177">Настройка телефона, номера, находящимся на приглашает</span><span class="sxs-lookup"><span data-stu-id="a0cda-177">Setting the phone numbers included on invites</span></span>
  
1. <span data-ttu-id="a0cda-178">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-178">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-179">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-180">В левой области переходов, перейдите к **аудиоконференции** > **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="a0cda-181">Выберите пользователя, который необходимо включить для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a0cda-181">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="a0cda-182">В области действий можно задать **бесплатный номер** и, если это разрешено, **телефоны**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="a0cda-183">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-183">Click **Save**.</span></span>
    
<span data-ttu-id="a0cda-184">В разделе [Задайте телефона, номера, находящимся на приглашает](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="a0cda-185">Выбор параметров моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="a0cda-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="a0cda-186">**Установка качества собрания при абонентов присоединиться к собранию**</span><span class="sxs-lookup"><span data-stu-id="a0cda-186">**Set the meeting experience when callers join a meeting**</span></span>

   
1. <span data-ttu-id="a0cda-187">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-187">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-188">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-189">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a0cda-190">В разделе **при присоединении к собраниям**выберите следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a0cda-190">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="a0cda-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="a0cda-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="a0cda-192">Если снять этот флажок, пользователей, которые уже присоединились к собранию по умолчанию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="a0cda-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="a0cda-193">Это можно установить на основе собрания с собрания при присоединении пользователя собрания с помощью Скайп для бизнес-приложения и их изменение **объявлений при людей введите или оставьте** параметр в меню Скайп собрания **Параметры** собрания.</span><span class="sxs-lookup"><span data-stu-id="a0cda-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="a0cda-194">**ASK абонентов записать их имя перед присоединением к собранию** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0cda-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="a0cda-195">Если снять этот флажок, вызывающие объекты не будет предложено записать их имя перед их присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="a0cda-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="a0cda-196">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="a0cda-197">Просмотрите, [Изменить параметры для моста аудиоконференции](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-197">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="a0cda-198">**Задать длину ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="a0cda-198">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="a0cda-199">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-199">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-200">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-201">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a0cda-202">В разделе **Безопасность**введите количество цифр, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-код** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="a0cda-203">ПИН-код должен быть от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="a0cda-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="a0cda-204">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="a0cda-204">The default is 5.</span></span>
    
<span data-ttu-id="a0cda-205">Просмотрите, [Изменить параметры для моста аудиоконференции](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-205">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="a0cda-206">**Включение или отключение электронной почты с передачей звука пользователей**</span><span class="sxs-lookup"><span data-stu-id="a0cda-206">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="a0cda-207">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-208">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a0cda-209">На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="a0cda-210">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-210">Click **Save**.</span></span>
    
    <span data-ttu-id="a0cda-211">Также можно отправить электронной почты для пользователя с параметрами аудиоконференций, перейдя к свойствам аудиоконференций пользователя и нажав кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="a0cda-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="a0cda-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="a0cda-213">Просмотр и установка основного и дополнительных языков для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="a0cda-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="a0cda-214">Просмотреть, задайте основной (по умолчанию) и дополнительных языков (альтернативного) на звукового конференц-канала</span><span class="sxs-lookup"><span data-stu-id="a0cda-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="a0cda-215">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-215">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-216">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-217">В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="a0cda-218">Выберите номер телефона в списке, нажмите кнопку **установить язык** в области действия и на странице **языков** выберите использование списке **основной язык** , чтобы просмотреть полный список поддерживаемых языков.</span><span class="sxs-lookup"><span data-stu-id="a0cda-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="a0cda-219">Также можно настроить основных и дополнительных языков, которые поддерживаются при выборе Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="a0cda-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="a0cda-220">Порядок, в котором можно выбрать в списках является том же порядке, в котором будут представлены языков для вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="a0cda-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="a0cda-221">См. номера для аудиоконференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a0cda-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="a0cda-222">Просмотра аудиоконференций телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="a0cda-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="a0cda-223">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-223">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-224">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-225">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **мост Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="a0cda-226">Здесь можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a0cda-226">Here you can:</span></span>
    
  - <span data-ttu-id="a0cda-227">Просмотр номера телефонов, установленных с Office 365 для использования для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a0cda-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="a0cda-228">Просмотр расположения и основных и дополнительных языки, которые будут использоваться автосекретарем конференц-связи звука.</span><span class="sxs-lookup"><span data-stu-id="a0cda-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="a0cda-229">Выберите номер телефона по умолчанию, который будет предоставлен для пользователей, если они включены для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a0cda-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a0cda-230">Тем не менее при изменении номера телефона по умолчанию моста аудиоконференций не изменить номер телефона по умолчанию для существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0cda-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="a0cda-231">Можно перейти к **аудиоконференции** > **пользователей** и выберите Свойства пользователя, чтобы изменить значение по умолчанию, какой номер для пользователя, выбрав новый номер в списке чисел, которые доступны в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a0cda-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="a0cda-232">В разделе [список номеров звук конференц-связи](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="a0cda-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="a0cda-233">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="a0cda-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="a0cda-234">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="a0cda-234">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0cda-235">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0cda-236">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции**> и затем **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a0cda-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="a0cda-237">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0cda-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a0cda-238">Можно управлять определенными параметрами на уровне организации с использованием Windows PowerShell. Таким образом, упрощается применение параметров для всех пользователей. Далее представлены параметры на уровне организации:</span><span class="sxs-lookup"><span data-stu-id="a0cda-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="a0cda-239">Существует несколько параметров, которые можно управлять на уровне организации, с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0cda-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="a0cda-240">Это упрощает для применения параметров для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0cda-240">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="a0cda-241">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a0cda-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="a0cda-242">Ниже приведены параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="a0cda-242">Here are the organization-level settings:</span></span> 
 
- <span data-ttu-id="a0cda-243">**Настройка уведомлений входа и выхода** Значение по умолчанию — _$true_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="a0cda-244">**Параметр имя записи** Значение по умолчанию — _$true_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="a0cda-245">**Установка длины ПИН-кода** Значение по умолчанию равно 5.</span><span class="sxs-lookup"><span data-stu-id="a0cda-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="a0cda-246">**Установка только телефонных собраний, с телефона** По умолчанию _$false_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="a0cda-247">**Установка необходимость отправки электронной почты для пользователей** Значение по умолчанию — _$true_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="a0cda-248">**Установка необходимость отправки электронной почты с другой учетной записи** Значение по умолчанию — _$false_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="a0cda-249">**Установка адреса отправителя на электронной почты, которое отправляется пользователям** Значение по умолчанию — _$null_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="a0cda-250">**Установка отображаемое имя для электронной почты, отправляемое пользователям** Значение по умолчанию — _$null_.</span><span class="sxs-lookup"><span data-stu-id="a0cda-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a0cda-251">Чтобы получить дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0cda-251">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="a0cda-p119">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a0cda-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a0cda-255">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a0cda-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a0cda-256">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0cda-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a0cda-p120">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a0cda-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a0cda-259">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a0cda-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a0cda-260">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a0cda-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a0cda-261">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a0cda-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="a0cda-p121">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="a0cda-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a0cda-264">See also</span><span class="sxs-lookup"><span data-stu-id="a0cda-264">Related topics</span></span>

[<span data-ttu-id="a0cda-265">Управление настройками аудиоконференций для пользователя</span><span class="sxs-lookup"><span data-stu-id="a0cda-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


