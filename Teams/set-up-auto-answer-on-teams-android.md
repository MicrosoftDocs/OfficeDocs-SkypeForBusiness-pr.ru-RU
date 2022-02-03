---
title: Настройка автоотвода для Teams Android
author: KarliStites
ms.author: kastites
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
description: Узнайте, как настроить функцию автоотвода для Teams устройств с Android с помощью PowerShell.
ms.openlocfilehash: e25b0694b54d1047c64ecaba026380ac9c4a9949
ms.sourcegitcommit: 5e9a8d3cdb72b57adfb842200159c5d753b70ecb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2022
ms.locfileid: "62329108"
---
# <a name="set-up-auto-answer-for-teams-android-devices"></a>Настройка автоотвода для Teams Android

Эта статья поможет вам настроить функцию автоотвода на Teams устройствах с Android. Автоответ позволяет пользователям в вашей организации с административными привилегиями изменять параметры устройства, чтобы автоматически принимать входящие приглашения на собрания и автоматически принимать звонки с видео.

## <a name="enable-auto-answer-with-powershell"></a>Включить автоотвод с помощью PowerShell

Используйте следующие атрибуты, чтобы включить автоот ответ на Teams устройствах с Android:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Включить автоматический ответ для входящих приглашений на собрания

Чтобы включить автоответ для входящих приглашений на собрания, используйте **set-CsTeamsCallingPolicy -AutoAnswerEnabledType** . По умолчанию **автоотполнение** отключено. Эта политика применяется только к входящие приглашениям на собрания и не поддерживает другие типы зовов. [Дополнительные сведения о cmdlet см. в документе Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Настройка режима для устройства

**Set-CsTeamsIPPhonePolicy -SignInMode** используется для определения поведения устройства при входе в Teams. [Дополнительные сведения о cmdlet см. в документе Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy).

Для режима вход в 2010 году доступны три параметра:

- **UserSignIn:** Позволяет отдельному пользователю Teams на телефоне.
- **CommonAreaPhoneSignIn:** Включает общую телефонную зону работы с телефоном.
- **MeetingSignIn:** Включает возможности комнаты для собрания по телефону.

Например, следующая политика задает для режима входов режим комнаты собрания.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Настройка параметров устройства

После включения автоотвода пользователи с административными разрешениями могут включить эту функцию в параметрах устройства. Чтобы включить эту функцию на уровне устройства, необходимо включить функцию Автоматическое **принятие входящих приглашений на собрания**. Вы также можете включить автоматическое **принятие с видео**. По умолчанию оба параметра отключены.

## <a name="related-topics"></a>Статьи по теме

[Служба поддержки Майкрософт: звонки и устройства](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)