---
title: Настройка облачной голосовой почты
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Узнайте, как настроить облачную голосовую почту для пользователей. '
ms.openlocfilehash: fa30184d38822141d0f30404fb55b79eefd5d33d
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997427"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="7c85a-103">Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="7c85a-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="7c85a-104">Эта статья адресовна администратору Microsoft 365 или Office [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 365, как описано в статье "Роли администраторов, которые хотят настроить облачную голосовую почту для всех в компании".</span><span class="sxs-lookup"><span data-stu-id="7c85a-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="7c85a-105">Облачная голосовая почта поддерживает хранение сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние почтовые системы.</span><span class="sxs-lookup"><span data-stu-id="7c85a-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="7c85a-106">Когда делегат отвечает на звонок от имени представителя, в облачной голосовой почте уведомления недоступны.</span><span class="sxs-lookup"><span data-stu-id="7c85a-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="7c85a-107">Пользователи могут получать уведомления о пропущенных звонках.</span><span class="sxs-lookup"><span data-stu-id="7c85a-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="7c85a-108">Облачные среды: настройка облачной голосовой почты для пользователей телефонной системы Online</span><span class="sxs-lookup"><span data-stu-id="7c85a-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="7c85a-109">Для пользователей телефонной системы Online облачная голосовая почта автоматически устанавливается  и устанавливается для пользователей после назначения им лицензии на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="7c85a-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="7c85a-110">Для пользователей телефонной системы Skype для бизнеса Online с телефонными номерами, предоставленными локально, может потребоваться включить услугу голосовой почты на сервере [Set-CsUser -HostedVoicemail $True.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7c85a-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="7c85a-111">Настройка облачной голосовой почты для Exchange Server пользователей почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="7c85a-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="7c85a-112">Ниже приводится информация о настройке облачной голосовой почты для работы с пользователями, которые находятся в сети для телефонной системы, но имеют свой почтовый ящик Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7c85a-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="7c85a-113">Сообщения голосовой почты доставляются в почтовый ящик Exchange пользователей через SMTP, маршрутный через Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="7c85a-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="7c85a-114">Чтобы обеспечить их успешную доставку, убедитесь, что соединители Exchange Connectors правильно настроены на серверах Exchange Server и в службе Exchange Online Protection. [Используйте соединители для настройки потока почты.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="7c85a-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="7c85a-115">Чтобы включить функции голосовой почты, такие как настройка приветствий и визуальной голосовой почты в клиентах Skype для бизнеса, требуется подключение Microsoft 365 или Office 365 к почтовому ящику сервера Exchange через веб-службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c85a-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="7c85a-116">Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности Exchange Oauth, описанный в описании функции "Настройка проверки подлинности [OAuth"](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)между организациями Exchange и Exchange Online, или запустить мастер гибридного подключения Exchange из Exchange 2013 CU5 или более новой модели.</span><span class="sxs-lookup"><span data-stu-id="7c85a-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="7c85a-117">Кроме того, необходимо настроить интеграцию и Oauth между Skype для бизнеса Online и сервером Exchange, описанными в описании функций "Настройка интеграции" и ["OAuth"](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)между Skype для бизнеса Online и Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7c85a-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="7c85a-118">Настройка облачной голосовой почты для пользователей Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7c85a-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="7c85a-119">Чтобы настроить пользователей сервера Skype для бизнеса для облачной голосовой почты, см. план обслуживания облачной голосовой почты для пользователей [локальной службы.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="7c85a-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="7c85a-120">Включение защищенной голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="7c85a-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="7c85a-121">Когда кто-то покидает сообщение голосовой почты пользователя в вашей организации, голосовая почта доставляется в почтовый ящик пользователя в виде вложения.</span><span class="sxs-lookup"><span data-stu-id="7c85a-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="7c85a-122">Используя правила потока почты для применения шифрования сообщений, можно запретить их пересылку другим получателям.</span><span class="sxs-lookup"><span data-stu-id="7c85a-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="7c85a-123">Если включить защищенную голосовую почту, пользователи смогут прослушивать защищенные сообщения голосовой почты, позвонив в свой почтовый ящик голосовой почты или открыв их в Outlook, Outlook в Интернете или Outlook для Android или iOS.</span><span class="sxs-lookup"><span data-stu-id="7c85a-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="7c85a-124">Защищенные сообщения голосовой почты нельзя открыть в Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7c85a-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="7c85a-125">Дополнительные сведения о шифровании сообщений см. в [теме "Шифрование электронной почты".](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="7c85a-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="7c85a-126">Чтобы настроить защищенную голосовую почту, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="7c85a-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="7c85a-127">Перейдите к учетной записи и войдите в нее с https://admin.microsoft.com разрешениями глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7c85a-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="7c85a-128">Выберите **"Показать все",** а затем перейдите в **центры администрирования**  >  **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="7c85a-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="7c85a-129">В Центре администрирования Exchange выберите правила **потока обработки**  >  **почты.**</span><span class="sxs-lookup"><span data-stu-id="7c85a-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="7c85a-130">Выберите **+** **"Добавить",** а затем выберите "Применить шифрование сообщений **Office 365 и защиту прав к письмам".**</span><span class="sxs-lookup"><span data-stu-id="7c85a-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="7c85a-131">Введите имя для нового правила потока почты, а затем в списке "Применить это правило", если выберите свойства сообщения: "Голосовая почта".  >    >  </span><span class="sxs-lookup"><span data-stu-id="7c85a-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="7c85a-132">Выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="7c85a-132">Select **OK**.</span></span>
6. <span data-ttu-id="7c85a-133">В **области "Сделать следующее"** выберите "Применить шифрование сообщений **Office 365** и защиту прав к сообщению" и выберите **один из них.**</span><span class="sxs-lookup"><span data-stu-id="7c85a-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="7c85a-134">В **области шаблона RMS выберите** **"Не переадваровываться".**</span><span class="sxs-lookup"><span data-stu-id="7c85a-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="7c85a-135">Выберите **"ОК"** и **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="7c85a-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7c85a-136">Если список **шаблонов RMS** пуст, необходимо настроить шифрование сообщений.</span><span class="sxs-lookup"><span data-stu-id="7c85a-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="7c85a-137">Дополнительные сведения о настройке шифрования сообщений см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="7c85a-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="7c85a-138">Настройка новых возможностей шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="7c85a-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="7c85a-139">Настройка шаблонов и управление их использованием в Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="7c85a-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="7c85a-140">Параметр "Не переадваровыть" для сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="7c85a-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="7c85a-141">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="7c85a-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="7c85a-142">Для пользователей Skype для бизнеса отключение голосовой почты с помощью политики звонков Microsoft Teams также может отключить службу голосовой почты для пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c85a-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="7c85a-143">Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c85a-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="7c85a-144">Сообщения голосовой почты, полученные пользователями в вашей организации, транскрибются в регионе, где находится ваша организация Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c85a-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="7c85a-145">Регион, в котором размещен клиент, может не быть регионом, в котором находится пользователь, получающий сообщение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="7c85a-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="7c85a-146">Чтобы просмотреть регион размещения клиента, перейдите [](https://go.microsoft.com/fwlink/p/?linkid=2067339) на страницу профиля организации и нажмите кнопку "Просмотреть **сведения"** рядом с расположением **данных.**</span><span class="sxs-lookup"><span data-stu-id="7c85a-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c85a-147">С помощью cmdlet **New-CsOnlineVoiceMailPolicy** нельзя создать новый экземпляр политики для транскрибации и транскрибации, а также удалить существующий экземпляр политики с помощью cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="7c85a-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="7c85a-148">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="7c85a-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="7c85a-149">Чтобы увидеть все доступные экземпляры политик голосовой почты, используйте для этого cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c85a-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="7c85a-150">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="7c85a-150">Turning off transcription for your organization</span></span>

<span data-ttu-id="7c85a-p110">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7c85a-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="7c85a-153">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="7c85a-153">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="7c85a-154">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7c85a-154">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="7c85a-155">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c85a-155">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="7c85a-156">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7c85a-156">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="7c85a-157">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="7c85a-157">Turning off transcription for a user</span></span>

<span data-ttu-id="7c85a-158">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="7c85a-158">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="7c85a-159">Например, если транскрибация голосовой почты включена для всех пользователей, вы можете назначить политику для отключения транскрибации для конкретного пользователя с помощью cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c85a-159">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="7c85a-160">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7c85a-160">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="7c85a-161">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="7c85a-161">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="7c85a-162">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c85a-162">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="7c85a-163">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c85a-163">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="7c85a-164">Служба голосовой почты в Microsoft 365 и Office 365 кэшетет политик голосовой почты и обновляет кэш каждые 4 часа.</span><span class="sxs-lookup"><span data-stu-id="7c85a-164">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="7c85a-165">Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="7c85a-165">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="7c85a-166">Помощь пользователям в доступе к функциям голосовой почты Teams</span><span class="sxs-lookup"><span data-stu-id="7c85a-166">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="7c85a-167">Ниже данная информация содержит сведения об управлении настройками голосовой почты, а также другими функциями звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="7c85a-167">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="7c85a-168">[Управление настройками параметров звонка в Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="7c85a-168">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="7c85a-169">В этой статье объясняется, как управлять всеми функциями звонков Teams для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="7c85a-169">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="7c85a-170">Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c85a-170">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="7c85a-p115">Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="7c85a-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="7c85a-173">[Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="7c85a-173">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="7c85a-174">Обучение работе со Skype для бизнеса 2016</span><span class="sxs-lookup"><span data-stu-id="7c85a-174">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="7c85a-175">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7c85a-175">Related topics</span></span>
[<span data-ttu-id="7c85a-176">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7c85a-176">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="7c85a-177">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="7c85a-177">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="7c85a-178">Планирование миграции Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7c85a-178">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
