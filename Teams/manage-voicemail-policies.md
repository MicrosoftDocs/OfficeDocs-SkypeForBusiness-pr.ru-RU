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
ms.openlocfilehash: 213908183c0d1dc608626272c0ea8aa5af308aff
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796928"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

> [!WARNING]
> Для Skype для бизнеса пользователей отключение голосовой почты с Microsoft Teams голосовой почты может также отключить службу голосовой почты для Skype для бизнеса пользователей.

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) и [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy).

Сообщения голосовой почты, полученные пользователями в вашей организации, транскрибются в том регионе, где Microsoft 365 или Office 365 организации. Регион, в котором размещен ваш клиент, может не быть регионом, в котором находится пользователь, получающий сообщение голосовой почты. Чтобы просмотреть регион размещения клиента, перейдите [](https://go.microsoft.com/fwlink/p/?linkid=2067339) на страницу профиля организации и щелкните Просмотреть **сведения** рядом с кнопкой **Расположение данных.**

> [!IMPORTANT]
> Вы не можете создать новый экземпляр политики для транскрибации и транскрибации с помощью cmdlet **New-CsOnlineVoiceMailPolicy,** а также удалить существующий экземпляр политики с помощью cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Чтобы увидеть все доступные экземпляры политик голосовой почты, воспользуйтесь [cmdlet Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

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

> [!IMPORTANT]
> Служба голосовой почты Microsoft 365 и Office 365 кэш политики голосовой почты и обновляет кэш каждые 6 часов. Таким образом, на внесение изменений политики может быть применено до 6 часов.
