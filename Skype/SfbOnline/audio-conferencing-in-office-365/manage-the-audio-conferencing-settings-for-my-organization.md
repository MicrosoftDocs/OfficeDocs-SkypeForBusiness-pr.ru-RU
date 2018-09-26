---
title: Управление параметрами аудиоконференций организации в Skype для бизнеса Online
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'В разделе Скайп для бизнеса в Интернет действия для назначения идентификатора лицензии и конференц-связь с телефонным пользователя и многие другие параметры конференц-связи. '
ms.openlocfilehash: 7e420ef2c434807bf9e78cc1c61f808db745f3bc
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018927"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="69041-103">Управление параметрами аудиоконференций организации в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="69041-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="69041-104">Для получения информации о том, как управлять этими параметрами с помощью Microsoft Teams, см. [Управление параметрами аудиоконференций для организаций в Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="69041-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="69041-105">Можно легко видеть все параметры аудиоконференций для Скайп для бизнеса в одном месте.</span><span class="sxs-lookup"><span data-stu-id="69041-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="69041-106">Назначение лицензии на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="69041-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="69041-107">Невозможно присвоить лицензии с **Скайп по центру администрирования бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="69041-108">Необходимо использовать Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="69041-108">You must use the Office 365 admin center.</span></span> <span data-ttu-id="69041-109">Назначение пользователю идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="69041-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="69041-110">**Назначение лицензии для пользователя**</span><span class="sxs-lookup"><span data-stu-id="69041-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="69041-111">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-112">В левой области переходов **центра администрирования Office 365**, перейдите к **пользователям** > **активных пользователей**и выберите одного или нескольких пользователей из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="69041-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69041-113">Если при назначении лицензии до 20 пользователями в то же время, можно использовать **Выберите представление** раскрывающемся списке а затем выберите один из параметров или создание собственного представления.</span><span class="sxs-lookup"><span data-stu-id="69041-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="69041-114">Нажмите на кнопку **Редактировать**, после чего, дважды нажмите на кнопку **Далее**, выделите лицензию и нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="69041-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="69041-115">Для назначения лицензии нескольким пользователям можно также воспользоваться Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="69041-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="69041-116">Для ознакомления с инструкцией и примерами скриптов PowerShell см. [Назначение лицензий в Skype для бизнеса](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="69041-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="69041-117">На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="69041-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="69041-118">На странице **Лицензии на продукты** включите функцию **Аудиконференции**, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69041-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="69041-119">Для получения дополнительных сведений о лицензировании см [Скайп для лицензирования дополнительный компонент Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="69041-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="69041-120">После назначения лицензии Майкрософт могут отсутствовать изначально в списке как поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="69041-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="69041-121">В таком случае выйдите из центра администрирования Office 365 или нажмите сочетание клавиш CTRL+F5 для обновления окна браузера.</span><span class="sxs-lookup"><span data-stu-id="69041-121">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="69041-122">Включение или отключение сообщений, отправляемых в пользователей аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="69041-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="69041-123">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="69041-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="69041-124">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-125">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="69041-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="69041-126">На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="69041-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="69041-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69041-127">Click **Save**.</span></span>

    <span data-ttu-id="69041-128">Также можно отправить по электронной почте для пользователя с помощью параметров аудиоконференций, перейдя к свойствам аудиоконференций пользователя и нажав кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="69041-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="69041-129">Конференции по умолчанию и идентификатор аудиоконференций номер телефона включен в приглашении на собрание, но не ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="69041-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="69041-130">[Использование Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="69041-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="69041-131">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="69041-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="69041-132">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="69041-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="69041-133">[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) можно использовать для управления другими параметрами для вашей организации, включая электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69041-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="69041-134">Изменить сведения о контакте отправителя в сообщениях электронной почты, отправляемое пользователю</span><span class="sxs-lookup"><span data-stu-id="69041-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="69041-135">В сообщение, которое отправляется пользователям автоматически, можно внести изменения, включив в него фактический адрес электронной почты и отобразив имя отправителя в составе контактной информации.</span><span class="sxs-lookup"><span data-stu-id="69041-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="69041-136">По умолчанию, отправителя сообщения электронной почты — Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69041-136">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="69041-137">Чтобы изменить адрес электронной почты, который отправляет сообщение электронной почты для пользователей, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="69041-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="69041-138">Введите адрес электронной почты с помощью параметра _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="69041-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="69041-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="69041-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="69041-140">Присвойте параметру _SendEmailOverride_ значение _True_.</span><span class="sxs-lookup"><span data-stu-id="69041-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="69041-141">Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69041-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="69041-142">Чтобы изменить адрес электронной почты, нужно убедиться в том, что применяемая организацией политика входящих сообщений позволяет принимать сообщения, отправленные с настраиваемого адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69041-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="69041-143">Командлет [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) можно использовать для управления другими параметрами для вашей организации, включая электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69041-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="69041-144">В разделе [сообщения электронной почты, которые отправляются пользователям при изменении их параметров звука конференц-связи, автоматически](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="69041-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="69041-145">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="69041-146">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-147">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-148">На панели навигации слева в **центре администрирования Skype для бизнеса** перейдите к секции **Аудиоконференции** и на панели действий в области**Идентификатор конференции** нажмите на кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="69041-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="69041-149">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="69041-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="69041-150">При этом будет автоматически создан идентификатор конференции и, если функция отправки сообщений включена, пользователям будут отправлены сообщения с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="69041-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="69041-151">По умолчанию эта настройка остается включенной.</span><span class="sxs-lookup"><span data-stu-id="69041-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="69041-152">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="69041-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="69041-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="69041-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="69041-154">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="69041-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="69041-155">Чтобы узнать, как для загрузки, установки и запуска Скайп для бизнеса средство обновления собрания, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, собрания Средство миграции (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="69041-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="69041-156">Сброс ПИН-кода организатора конференции</span><span class="sxs-lookup"><span data-stu-id="69041-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="69041-157">Сброс ПИН-кода организатора конференции</span><span class="sxs-lookup"><span data-stu-id="69041-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="69041-158">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="69041-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="69041-159">Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="69041-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="69041-160">Войдите в административную панель Skype для бизнеса и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="69041-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="69041-161">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-162">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="69041-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="69041-163">Щелкните элемент **Пользователи**, а затем выберите пользователя, который требуется сбросить ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="69041-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="69041-164">В области действий в разделе **ПИН-код**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="69041-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="69041-165">Пользователи будут получать сообщения электронной почты с свой ПИН-код, когда они будет включена поддержка аудиоконференций или когда сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="69041-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="69041-166">Но если вы отключили автоматически отправка по электронной почте, не будут отправляться электронной почты сброс ПИН-кода и необходимо вручную отправлять ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="69041-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="69041-167">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="69041-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="69041-168">После отображения сразу после сброса ПИН-код не будет больше отображаться на свойства пользователя; Вместо этого \*\*\* будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="69041-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="69041-169">В разделе [Сброс аудиоконференций ПИН-кода](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="69041-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="69041-170">Отправить сообщение электронной почты с информацией аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="69041-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="69041-171">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-172">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="69041-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="69041-173">Щелкните элемент **Пользователи**, а затем выберите пользователя, который требуется сбросить ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="69041-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="69041-174">На панели действий щелкните **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="69041-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69041-175">При этом аудиоконференций ПИН-код не отправляется для пользователя.</span><span class="sxs-lookup"><span data-stu-id="69041-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="69041-176">[Использование Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="69041-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="69041-177">Настройка телефона, номера, находящимся на приглашает</span><span class="sxs-lookup"><span data-stu-id="69041-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="69041-178">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-179">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-180">В панели навигации слева перейдите к секции **Аудиоконференции** > **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="69041-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="69041-181">Выберите пользователя, который необходимо включить для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="69041-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="69041-182">На панели «Действия» можно указать **Платный номер** и, если разрешено, **Бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="69041-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="69041-183">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69041-183">Click **Save**.</span></span>

<span data-ttu-id="69041-184">В разделе [Задайте телефона, номера, находящимся на приглашает](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="69041-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="69041-185">Выбор параметров моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="69041-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="69041-186">**Установка качества собрания при абонентов присоединиться к собранию**</span><span class="sxs-lookup"><span data-stu-id="69041-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="69041-187">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-188">Перейдите к **центру администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-189">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69041-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="69041-190">В разделе **при присоединении к собраниям**выберите следующие действия:</span><span class="sxs-lookup"><span data-stu-id="69041-190">Under **Meeting join experience**, select the following actions:</span></span>

  - <span data-ttu-id="69041-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="69041-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="69041-192">Если снять этот флажок, пользователей, которые уже присоединились к собранию по умолчанию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="69041-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="69041-193">Это можно установить на основе собрания с собрания при присоединении пользователя собрания с помощью Скайп для бизнес-приложения и их изменение **объявлений при людей введите или оставьте** параметр в меню Скайп собрания **Параметры** собрания.</span><span class="sxs-lookup"><span data-stu-id="69041-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

  - <span data-ttu-id="69041-194">**ASK абонентов записать их имя перед присоединением к собранию** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69041-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="69041-195">Если снять этот флажок, то предложение записать свое имя перед присоединением к собранию пользователям, совершающим вызов, не поступает.</span><span class="sxs-lookup"><span data-stu-id="69041-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="69041-196">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69041-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="69041-197">Просмотрите, [Изменить параметры для моста аудиоконференции](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="69041-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="69041-198">**Задать длину ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="69041-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="69041-199">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-200">Перейдите к **центру администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-201">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69041-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="69041-202">В разделе **Безопасность**введите количество цифр, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-код** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69041-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="69041-203">ПИН-код должен включать в себя от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="69041-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="69041-204">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="69041-204">The default is 5.</span></span>
    
<span data-ttu-id="69041-205">Просмотрите, [Изменить параметры для моста аудиоконференции](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="69041-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="69041-206">**Включение или отключение электронной почты с передачей звука пользователей**</span><span class="sxs-lookup"><span data-stu-id="69041-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="69041-207">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-208">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса** и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="69041-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="69041-209">На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="69041-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="69041-210">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69041-210">Click **Save**.</span></span>

    <span data-ttu-id="69041-211">Также можно отправить электронной почты для пользователя с параметрами аудиоконференций, перейдя к свойствам аудиоконференций пользователя и нажав кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="69041-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="69041-212">В этом случае, пользователям отправляются сообщения, содержащие идентификатор конференции и номер телефона, но не включающие в себя ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="69041-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="69041-213">Просмотр и установка основного и дополнительных языков для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="69041-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="69041-214">Просмотреть, задайте основной (по умолчанию) и дополнительных языков (альтернативного) на звукового конференц-канала</span><span class="sxs-lookup"><span data-stu-id="69041-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="69041-215">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-216">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-217">В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69041-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="69041-218">Выберите номер телефона в списке, нажмите кнопку **установить язык** в области действия и на странице **языков** выберите использование списке **основной язык** , чтобы просмотреть полный список поддерживаемых языков.</span><span class="sxs-lookup"><span data-stu-id="69041-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="69041-219">Также можно настроить основных и дополнительных языков, которые поддерживаются при выборе Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="69041-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="69041-220">Языки отображаются для участников конференции в том порядке, в котором они выбираются из списков.</span><span class="sxs-lookup"><span data-stu-id="69041-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="69041-221">См. номера для аудиоконференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="69041-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="69041-222">Просмотра аудиоконференций телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="69041-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="69041-223">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-224">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-225">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **мост Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="69041-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="69041-226">Здесь можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="69041-226">Here you can:</span></span>

  - <span data-ttu-id="69041-227">Просмотр номера телефонов, установленных с Office 365 для использования для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="69041-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

  - <span data-ttu-id="69041-228">Просмотр расположения и основных и дополнительных языки, которые будут использоваться автосекретарем конференц-связи звука.</span><span class="sxs-lookup"><span data-stu-id="69041-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  - <span data-ttu-id="69041-229">Выберите номер телефона по умолчанию, который будет предоставлен для пользователей, если они включены для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="69041-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="69041-230">Тем не менее при изменении номера телефона по умолчанию моста аудиоконференций не изменить номер телефона по умолчанию для существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="69041-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="69041-231">Можно перейти к **аудиоконференции** > **пользователей** и выберите Свойства пользователя, чтобы изменить значение по умолчанию, какой номер для пользователя, выбрав новый номер в списке чисел, которые доступны в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="69041-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="69041-232">В разделе [список номеров звук конференц-связи](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="69041-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="69041-233">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="69041-234">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="69041-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="69041-235">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="69041-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="69041-236">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции**> и затем **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="69041-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="69041-237">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69041-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="69041-238">Можно управлять определенными параметрами на уровне организации с использованием Windows PowerShell. Таким образом, упрощается применение параметров для всех пользователей. Далее представлены параметры на уровне организации:</span><span class="sxs-lookup"><span data-stu-id="69041-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="69041-239">Существует несколько параметров, которые можно управлять на уровне организации, с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69041-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="69041-240">Это упрощает для применения параметров для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="69041-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="69041-241">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="69041-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="69041-242">Ниже приведены параметры на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="69041-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="69041-243">**Настройка уведомлений о входе и выходе** Значением по умолчанию является _$true_.</span><span class="sxs-lookup"><span data-stu-id="69041-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="69041-244">**Настройка записи имени** Значением по умолчанию является _$true_.</span><span class="sxs-lookup"><span data-stu-id="69041-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="69041-245">**Настройка длины ПИН-кода** Значение по умолчанию равно 5.</span><span class="sxs-lookup"><span data-stu-id="69041-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="69041-246">**Настройка с телефона только для собраний с телефонным подключением** Значением по умолчанию является _$false_.</span><span class="sxs-lookup"><span data-stu-id="69041-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="69041-247">**Настройки отправки сообщений пользователям** Значением по умолчанию является _$true_.</span><span class="sxs-lookup"><span data-stu-id="69041-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="69041-248">**Настройка отправки сообщений с другой учетной записи** Значением по умолчанию является _$false_.</span><span class="sxs-lookup"><span data-stu-id="69041-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="69041-249">**Настройка адреса отправителя в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.</span><span class="sxs-lookup"><span data-stu-id="69041-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="69041-250">**Настройка имени, отображаемого в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.</span><span class="sxs-lookup"><span data-stu-id="69041-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="69041-251">Чтобы получить дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69041-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="69041-p119">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="69041-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="69041-255">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="69041-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="69041-256">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69041-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="69041-p120">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="69041-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="69041-259">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="69041-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="69041-260">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="69041-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="69041-261">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="69041-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="69041-p121">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="69041-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="69041-264">See also</span><span class="sxs-lookup"><span data-stu-id="69041-264">Related topics</span></span>

[<span data-ttu-id="69041-265">Управление настройками аудиоконференций для пользователя</span><span class="sxs-lookup"><span data-stu-id="69041-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


