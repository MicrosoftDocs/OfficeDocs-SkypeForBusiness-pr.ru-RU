---
title: Настройка автоматического ответа для Teams Android устройств
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Узнайте, как настроить функцию автоматического ответа для Комнаты Microsoft Teams на Android и Teams с помощью PowerShell.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646598"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Настройка автоматического ответа для Комнаты Microsoft Teams на Android и Teams видео телефонов

Эта статья поможет вам настроить функцию автоматического ответа на Комнаты Microsoft Teams на Android и Teams видео. Автоматический ответ позволяет пользователям в организации с правами администратора изменять параметры устройства, чтобы автоматически принимать приглашения на входящие собрания и автоматически принимать звонки с видео.

## <a name="enable-auto-answer-with-powershell"></a>Включение автоматического ответа с помощью PowerShell

Используйте следующие атрибуты, чтобы включить автоматический ответ на Комнаты Microsoft Teams на Android и Teams видео телефонов:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Включение автоматического ответа для входящих приглашений на собрания

**Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** используется для включения автоматического ответа для входящих приглашений на собрания. Автоматический ответ **по умолчанию** отключен. Эта политика применяется только к приглашениям на входящие собрания и не поддерживает другие типы вызовов. Дополнительные сведения о командлете см. в разделе [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) .

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Настройка режима входа устройства

Вы используете **Set-CsTeamsIPPhonePolicy -SignInMode**, чтобы задать режим входа для устройства, чтобы определить поведение при входе в Teams. [Дополнительные сведения о командлете см. в разделе Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy).

Существует три варианта режима входа:

- **UserSignIn:** Позволяет отдельному пользователю Teams на телефоне.
- **CommonAreaPhoneSignIn:** Включает общее взаимодействие с телефоном на телефоне.
- **MeetingSignIn:** Позволяет использовать конференц-зал на телефоне.

Например, приведенная ниже политика задает режим входа в конференц-зал.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Настройка параметров устройства

После включения автоматического ответа пользователи с правами администратора могут включить функцию в параметрах устройства. Чтобы включить эту функцию на уровне устройства, необходимо включить автоматическое **принятие входящих приглашений на собрания**. Вы также можете включить **автоматическое принятие с помощью видео**. Оба параметра отключены по умолчанию.

## <a name="related-topics"></a>Статьи по теме

[служба поддержки Майкрософт: звонки и устройства](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
