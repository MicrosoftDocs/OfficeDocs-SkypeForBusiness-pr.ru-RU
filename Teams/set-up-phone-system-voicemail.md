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
description: 'Узнайте, как настроить облачная голосовая почта для пользователей. '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117067"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="ced2e-103">Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="ced2e-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="ced2e-104">Эта статья адресовна администратору Microsoft 365 или Office 365, [](/microsoft-365/admin/add-users/about-admin-roles) как описано в статье Роли администраторов, которые хотят настроить облачная голосовая почта для всех в компании.</span><span class="sxs-lookup"><span data-stu-id="ced2e-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="ced2e-105">облачная голосовая почта поддерживает хранение сообщений голосовой почты только Exchange почтовом ящике и не поддерживает сторонние почтовые системы.</span><span class="sxs-lookup"><span data-stu-id="ced2e-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="ced2e-106">Когда делегат отвечает на звонок от имени представителя, в облачная голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="ced2e-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="ced2e-107">Пользователи могут получать уведомления о пропущенных звонках.</span><span class="sxs-lookup"><span data-stu-id="ced2e-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="ced2e-108">Облачные среды: настройка облачная голосовая почта для телефонная система Online</span><span class="sxs-lookup"><span data-stu-id="ced2e-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="ced2e-109">Для телефонная система Online облачная голосовая почта автоматически устанавливается и подготовка для пользователей после назначения им  лицензии телефонная система лицензии.</span><span class="sxs-lookup"><span data-stu-id="ced2e-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="ced2e-110">Для пользователей Online Skype для бизнеса телефонная система с предоставленными телефонными номерами локальной службы может потребоваться включить услугу голосовой почты в [Set-CsUser -HostedVoicemail $True.](/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ced2e-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="ced2e-111">Настройка облачная голосовая почта для Exchange Server почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="ced2e-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="ced2e-112">Ниже данная информация о настройке облачная голосовая почта для работы с пользователями, которые находятся в сети телефонная система но имеют свой почтовый ящик Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ced2e-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="ced2e-113">Сообщения голосовой почты доставляются в почтовый Exchange пользователей через SMTP, маршрутный через Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="ced2e-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="ced2e-114">Чтобы обеспечить успешную доставку этих сообщений, убедитесь, что соединители Exchange правильно настроены между серверами Exchange и Exchange Online Protection; [Настройте почтовые Flow с помощью соедините Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="ced2e-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="ced2e-115">Чтобы включить функции голосовой почты, такие как настройка приветствий и визуальной голосовой почты в клиентах Skype для бизнеса, требуется подключение из Microsoft 365 или Office 365 к почтовому ящику Exchange сервера через веб-службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="ced2e-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="ced2e-116">Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности Exchange Oauth, описанный в окне Настройка проверки подлинности [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)между организациями Exchange и Exchange Online, или запустить мастер гибридной конфигурации Exchange в Exchange 2013 CU5 или более новой.</span><span class="sxs-lookup"><span data-stu-id="ced2e-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="ced2e-117">Кроме того, необходимо настроить интеграцию и Oauth между серверами Skype для бизнеса Online и Exchange, описанными в окне Настройка интеграции и [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)между Skype для бизнеса Online и Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ced2e-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="ced2e-118">Настройка облачная голосовая почта для Skype для бизнеса Server пользователей</span><span class="sxs-lookup"><span data-stu-id="ced2e-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="ced2e-119">Чтобы настроить Skype для бизнеса серверов для облачная голосовая почта, см. облачная голосовая почта планирования службы для пользователей [локальной сети.](/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="ced2e-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="ced2e-120">Включение защищенной голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="ced2e-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="ced2e-121">Когда кто-то покидает сообщение голосовой почты для пользователя в вашей организации, голосовая почта доставляется в почтовый ящик пользователя в виде вложения сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ced2e-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="ced2e-122">Используя правила потока почты для применения шифрования сообщений, вы можете запретить их пересылку другим получателям.</span><span class="sxs-lookup"><span data-stu-id="ced2e-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="ced2e-123">Если включить защищенную голосовую почту, пользователи смогут прослушивать защищенные сообщения голосовой почты, позвонив в свой почтовый ящик голосовой почты или открыв их в Outlook, Outlook в Интернете или Outlook для Android или iOS.</span><span class="sxs-lookup"><span data-stu-id="ced2e-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="ced2e-124">Защищенные сообщения голосовой почты нельзя открывать в Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ced2e-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="ced2e-125">Дополнительные сведения о шифровании сообщений см. в теме [Шифрование электронной почты.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="ced2e-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="ced2e-126">Чтобы настроить защищенную голосовую почту, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ced2e-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="ced2e-127">Перейдите к учетной записи с разрешениями глобального администратора и войдите https://admin.microsoft.com в нее.</span><span class="sxs-lookup"><span data-stu-id="ced2e-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="ced2e-128">Выберите **Показать все,** а затем перейдите **в** центр администрирования  >  **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="ced2e-129">В Центре Exchange выберите правила потока **обработки**  >  **почты**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="ced2e-130">Выберите **+** **Добавить**, а затем **выберите Применить шифрование сообщений Office 365 и защиту прав к сообщениям**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="ced2e-131">Введите имя для нового правила потока почты, а затем в списке Применить это **правило,** если , выберите Свойства сообщенияВключите тип  >    >  **сообщения Голосовая почта**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="ced2e-132">Выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-132">Select **OK**.</span></span>
6. <span data-ttu-id="ced2e-133">В **области Сделать следующее** выберите Применить шифрование сообщений Office 365 и защиту **прав** к сообщению с помощью и выберите Выберите **один**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="ced2e-134">В **области Шаблон RMS** выберите Не **переадваровываться**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="ced2e-135">Выберите **ОК,** а затем **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ced2e-136">Если список **шаблонов RMS** пуст, необходимо настроить шифрование сообщений.</span><span class="sxs-lookup"><span data-stu-id="ced2e-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="ced2e-137">Дополнительные сведения о настройке шифрования сообщений см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ced2e-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="ced2e-138">Настройка новых возможностей шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="ced2e-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="ced2e-139">Настройка шаблонов для Azure Information Protection и управление их использованием</span><span class="sxs-lookup"><span data-stu-id="ced2e-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="ced2e-140">Параметр "Не переадваровыть" для сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="ced2e-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="ced2e-141">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="ced2e-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="ced2e-142">Для Skype для бизнеса пользователей отключение голосовой почты с Microsoft Teams голосовой почты может также отключить службу голосовой почты для Skype для бизнеса пользователей.</span><span class="sxs-lookup"><span data-stu-id="ced2e-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="ced2e-143">Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) и [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="ced2e-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="ced2e-144">Сообщения голосовой почты, полученные пользователями в вашей организации, транскрибются в регионе, где Microsoft 365 или Office 365 организации.</span><span class="sxs-lookup"><span data-stu-id="ced2e-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="ced2e-145">Регион, в котором размещен ваш клиент, может не быть регионом, в котором находится пользователь, получающий сообщение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="ced2e-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="ced2e-146">Чтобы просмотреть регион размещения клиента, перейдите [](https://go.microsoft.com/fwlink/p/?linkid=2067339) на страницу профиля организации и щелкните Просмотреть **сведения** рядом с кнопкой **Расположение данных.**</span><span class="sxs-lookup"><span data-stu-id="ced2e-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ced2e-147">Вы не можете создать новый экземпляр политики для транскрибации и транскрибации с помощью cmdlet **New-CsOnlineVoiceMailPolicy,** а также удалить существующий экземпляр политики с помощью cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="ced2e-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="ced2e-148">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="ced2e-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="ced2e-149">Чтобы увидеть все доступные экземпляры политик голосовой почты, используйте для этого cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="ced2e-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="ced2e-150">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="ced2e-150">Turning off transcription for your organization</span></span>

<span data-ttu-id="ced2e-p110">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ced2e-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="ced2e-153">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="ced2e-153">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="ced2e-154">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ced2e-154">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="ced2e-155">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="ced2e-155">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="ced2e-156">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ced2e-156">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="ced2e-157">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="ced2e-157">Turning off transcription for a user</span></span>

<span data-ttu-id="ced2e-158">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="ced2e-158">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="ced2e-159">Например, если транскрибация голосовой почты включена для всех пользователей, вы можете назначить политику, которая отключит транскрибцию для определенного пользователя, с помощью cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="ced2e-159">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="ced2e-160">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ced2e-160">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="ced2e-161">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="ced2e-161">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="ced2e-162">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="ced2e-162">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="ced2e-163">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ced2e-163">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="ced2e-164">Служба голосовой почты Microsoft 365 и Office 365 кэш политики голосовой почты и обновляет кэш каждые 4 часа.</span><span class="sxs-lookup"><span data-stu-id="ced2e-164">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="ced2e-165">Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="ced2e-165">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="ced2e-166">Помощь пользователям в Teams голосовой почты</span><span class="sxs-lookup"><span data-stu-id="ced2e-166">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="ced2e-167">Ниже представлены сведения для пользователей об управлении настройками голосовой почты, а также другими функциями звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="ced2e-167">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="ced2e-168">[Управление настройками параметров звонка в Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="ced2e-168">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="ced2e-169">В этой статье объясняется, как управлять всеми функциями звонков Teams пользователями.</span><span class="sxs-lookup"><span data-stu-id="ced2e-169">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="ced2e-170">Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ced2e-170">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="ced2e-p115">Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="ced2e-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="ced2e-173">[Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="ced2e-173">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="ced2e-174">Обучение работе со Skype для бизнеса 2016</span><span class="sxs-lookup"><span data-stu-id="ced2e-174">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="ced2e-175">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ced2e-175">Related topics</span></span>
[<span data-ttu-id="ced2e-176">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ced2e-176">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="ced2e-177">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="ced2e-177">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ced2e-178">Планирование миграции Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ced2e-178">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)