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
ms.openlocfilehash: 112a2ac98ee22c46cb78c579ead947f70a1d6d447ac81ace3aef224304a281dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342973"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

> [!WARNING]
> Для Skype для бизнеса пользователей отключение голосовой почты с Microsoft Teams голосовой почты может также отключить службу голосовой почты для Skype для бизнеса пользователей.

## <a name="voicemail-organization-defaults-for-all-users"></a>Стандарты организации голосовой почты для всех пользователей
- Включена транскрибация голосовой почты.
- Расшифровка транскрибации голосовой почты отключена.
- Максимальная длительность записи — пять минут.

Вы можете управлять этими значениями по умолчанию с помощью cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) и [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

Сообщения голосовой почты, полученные пользователями в вашей организации, транскрибются в регионе, где Microsoft 365 или Office 365 организации. Регион, в котором размещен ваш клиент, может не быть регионом, в котором находится пользователь, получающий сообщение голосовой почты. Чтобы просмотреть регион размещения клиента, перейдите [](https://go.microsoft.com/fwlink/p/?linkid=2067339) на страницу профиля организации и щелкните Просмотреть **сведения** рядом с кнопкой **Расположение данных.**

> [!IMPORTANT]
> Вы не можете создать новый экземпляр политики для транскрибации и транскрибации с помощью cmdlet **New-CsOnlineVoiceMailPolicy** и удалить существующий экземпляр политики с помощью cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Чтобы увидеть все доступные экземпляры политик голосовой почты, используйте для этого cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

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
  
## <a name="turning-off-transcription-for-your-organization"></a>Выключение транскрибирования для организации

Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Для этого выполните команду:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Включение транскрибирования маскировки богохульства для вашей организации

Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации. Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Для этого выполните команду:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>Изменение длительности записи для организации

Максимальная длина записи для вашей организации по умолчанию составляет пять минут. Если необходимо увеличить или уменьшить максимальную длину записи, это можно сделать с помощью [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Например, чтобы установить максимальное время записи (60 секунд), запустите:

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>Запросы в двух языковых системах для организации

По умолчанию при настройке голосовой почты вызывателям будут предложены подсказки системы голосовой почты на языке, выбранном пользователем. Если необходимо, чтобы запросы системы голосовой почты были представлены на двух языках, это можно сделать с помощью [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Язык основного и дополнительного языков может быть не одинаковым. Для этого выполните команду:

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>Выключение транскрибирования для пользователя

Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации. Например, если транскрибация голосовой почты включена для всех пользователей, вы можете назначить политику, которая отключит транскрибцию для определенного пользователя, с помощью cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)

Для отключения транскрибирования для одиночного пользователя выполните команду:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Включение транскрибирования маскировки богохульства для пользователя

Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).

Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>Изменение длительности записи для пользователя

Сначала необходимо создать настраиваемую политику голосовой почты с помощью [cmdlet New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Команда, показанная ниже, создает политику голосовой почты oneMinuteVoicemailPolicy для каждого пользователя с максимальным значениемRecordingLength в течение 60 секунд, а другие поля — глобальным значением на уровне клиента.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

Чтобы назначить настраиваемую политику пользователю, запустите: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>Запросы двух языковых систем для пользователя

Сначала необходимо создать настраиваемую политику голосовой почты с помощью [cmdlet New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Команда, показанная ниже, создает политику голосовой почты для каждого пользователя enUS-esSP-VoicemailPolicy с primarySystemPromptLanguage en-US (английский язык - США) и SecondarySystemPromptLanguage с установленным значением es-SP (испанский (Испания).

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

Чтобы назначить настраиваемую политику пользователю, запустите: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> В Get-CsOnlineVoicemailPolicy в настоящее время не возвращаются значения primarySystemPromptLanguage и SecondarySystemPromptLanguage. Чтобы увидеть эти значения, измените команду следующим образом:
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> Замените **Имя политики** именем политики.


> [!IMPORTANT]
> Служба голосовой почты Microsoft 365 и Office 365 кэш политики голосовой почты и обновляет кэш каждые 6 часов. Таким образом, на внесение изменений политики может быть применено до 6 часов.
