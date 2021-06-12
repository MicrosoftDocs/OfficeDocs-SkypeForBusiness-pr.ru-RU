---
title: Управление политиками голосовой почты
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
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
description: Управление политиками голосовой почты для пользователей.
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910061"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="2b284-103">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="2b284-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="2b284-104">Для Skype для бизнеса пользователей отключение голосовой почты с Microsoft Teams голосовой почты может также отключить службу голосовой почты для Skype для бизнеса пользователей.</span><span class="sxs-lookup"><span data-stu-id="2b284-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="2b284-105">Стандарты организации голосовой почты для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="2b284-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="2b284-106">Транскрибация голосовой почты включена.</span><span class="sxs-lookup"><span data-stu-id="2b284-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="2b284-107">Расшифровка транскрибации голосовой почты отключена.</span><span class="sxs-lookup"><span data-stu-id="2b284-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="2b284-108">Максимальная длительность записи — пять минут.</span><span class="sxs-lookup"><span data-stu-id="2b284-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="2b284-109">Вы можете управлять этими значениями по умолчанию с помощью cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) и [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="2b284-110">Сообщения голосовой почты, полученные пользователями в вашей организации, транскрибются в регионе, где Microsoft 365 или Office 365 организации.</span><span class="sxs-lookup"><span data-stu-id="2b284-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="2b284-111">Регион, в котором размещен ваш клиент, может не быть регионом, в котором находится пользователь, получающий сообщение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="2b284-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="2b284-112">Чтобы просмотреть регион размещения клиента, перейдите [](https://go.microsoft.com/fwlink/p/?linkid=2067339) на страницу профиля организации и щелкните Просмотреть **сведения** рядом с кнопкой **Расположение данных.**</span><span class="sxs-lookup"><span data-stu-id="2b284-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b284-113">Вы не можете создать новый экземпляр политики для транскрибации и транскрибации с помощью cmdlet **New-CsOnlineVoiceMailPolicy,** а также удалить существующий экземпляр политики с помощью cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="2b284-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="2b284-114">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="2b284-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="2b284-115">Чтобы увидеть все доступные экземпляры политик голосовой почты, воспользуйтесь [cmdlet Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="2b284-116">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="2b284-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="2b284-p103">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2b284-p103">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="2b284-119">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="2b284-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="2b284-120">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2b284-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="2b284-121">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="2b284-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="2b284-122">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2b284-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="2b284-123">Изменение длительности записи для организации</span><span class="sxs-lookup"><span data-stu-id="2b284-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="2b284-124">Максимальная длина записи для вашей организации по умолчанию составляет пять минут.</span><span class="sxs-lookup"><span data-stu-id="2b284-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="2b284-125">Если необходимо увеличить или уменьшить максимальную длину записи, это можно сделать с помощью [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="2b284-126">Например, чтобы установить максимальное время записи (60 секунд), запустите:</span><span class="sxs-lookup"><span data-stu-id="2b284-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="2b284-127">Запросы двух языковых систем для организации</span><span class="sxs-lookup"><span data-stu-id="2b284-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="2b284-128">По умолчанию при настройке голосовой почты вызывателям будут предложены подсказки системы голосовой почты на языке, выбранном пользователем.</span><span class="sxs-lookup"><span data-stu-id="2b284-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="2b284-129">Если необходимо, чтобы запросы системы голосовой почты были представлены на двух языках, это можно сделать с помощью [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="2b284-130">Язык основного и дополнительного языков может быть не одинаковым.</span><span class="sxs-lookup"><span data-stu-id="2b284-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="2b284-131">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2b284-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="2b284-132">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="2b284-132">Turning off transcription for a user</span></span>

<span data-ttu-id="2b284-133">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="2b284-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="2b284-134">Например, если транскрибация голосовой почты включена для всех пользователей, вы можете назначить политику, которая отключит транскрибцию для определенного пользователя, с помощью cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="2b284-135">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2b284-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="2b284-136">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="2b284-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="2b284-137">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="2b284-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="2b284-138">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2b284-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="2b284-139">Изменение длительности записи для пользователя</span><span class="sxs-lookup"><span data-stu-id="2b284-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="2b284-140">Сначала необходимо создать настраиваемую политику голосовой почты с помощью [cmdlet New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="2b284-141">Команда, показанная ниже, создает политику голосовой почты oneMinuteVoicemailPolicy для каждого пользователя с максимальным значениемRecordingLength в течение 60 секунд, а другие поля — глобальным значением на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="2b284-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="2b284-142">Чтобы назначить настраиваемую политику пользователю, запустите:</span><span class="sxs-lookup"><span data-stu-id="2b284-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="2b284-143">Запросы в двух языковых системах для пользователя</span><span class="sxs-lookup"><span data-stu-id="2b284-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="2b284-144">Сначала необходимо создать настраиваемую политику голосовой почты с помощью [cmdlet New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="2b284-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="2b284-145">Команда, показанная ниже, создает политику голосовой почты для каждого пользователя enUS-esSP-VoicemailPolicy с primarySystemPromptLanguage en-US (английский язык - США) и SecondarySystemPromptLanguage с установленным значением es-SP (испанский (Испания).</span><span class="sxs-lookup"><span data-stu-id="2b284-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="2b284-146">Чтобы назначить настраиваемую политику пользователю, запустите:</span><span class="sxs-lookup"><span data-stu-id="2b284-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="2b284-147">В Get-CsOnlineVoicemailPolicy в настоящее время не возвращаются значения primarySystemPromptLanguage и SecondarySystemPromptLanguage.</span><span class="sxs-lookup"><span data-stu-id="2b284-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="2b284-148">Чтобы увидеть эти значения, измените команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2b284-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="2b284-149">Замените **Имя политики** именем политики.</span><span class="sxs-lookup"><span data-stu-id="2b284-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2b284-150">Служба голосовой почты Microsoft 365 и Office 365 кэш политики голосовой почты и обновляет кэш каждые 6 часов.</span><span class="sxs-lookup"><span data-stu-id="2b284-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="2b284-151">Таким образом, внесение изменений в политику может занять до 6 часов.</span><span class="sxs-lookup"><span data-stu-id="2b284-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
