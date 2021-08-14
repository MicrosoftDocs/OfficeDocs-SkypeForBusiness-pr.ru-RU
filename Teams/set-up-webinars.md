---
title: Настройка вебинары в Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Узнайте, как управлять политиками веб-Teams собраний.
ms.openlocfilehash: 8386ef4ea9dd90d60cdc8c891461c3dc1a6b37ad4f3f7c47e42808e3c8f826a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330883"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Настройка вебинары в Microsoft Teams

Эта статья поможет вам настроить вебинары для организации.

## <a name="what-are-webinars"></a>Что такое вебинары?

Вебинары — это структурированные собрания, на которых у участников и участников есть четкие роли, которые часто используются для обучения или для подготовки по продажам и маркетингу.

После настройки вебинары в организации пользователи могут планировать вебинары и открывать регистрацию для участников. В отличие от обычных собраний, которые содержат много обсуждений и заданий задач, вебинары предназначены для интерактивных презентаций и предоставляют инструменты для анализа участников.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Разрешить пользователям планировать вебинары с помощью PowerShell

Чтобы настроить вебинары в Teams, можно использовать следующие атрибуты Windows PowerShell **Set-CsTeamsMeetingPolicy:**

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Дополнительные сведения о cmdlet см. в документе [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Перед запуском этих cmdlets необходимо подключение к Microsoft Teams PowerShell. Дополнительные сведения см. в [Teams помощью Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Разрешить пользователям планировать вебинары

Вы можете ограничить регистрацию только пользователями в организации или открыть ее для всех пользователей в клиенте и за ее пределами. По умолчанию **whoCanRegister** включен и установлено значение **Все**. Если вы хотите отключить регистрацию на собрании, установите **для allowMeetingRegistration (РазрешитьMeetingRegistration)** **ложное.**

> [!IMPORTANT]
> Чтобы разрешитьMeetingRegistration, задайте для  **allowPrivateMeetingMeetingScheduling** (Планирование планирования событий **allowPrivateMeetingScheduling)** true. Кроме того, Microsoft Списки необходимо настроить в SharePoint. Дополнительные параметры [см.](/sharepoint/control-lists)в Microsoft Списки.

1. Включить регистрацию собраний

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Включить планирование частных собраний

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Настройка пользователей, которые могут регистрироваться на вебинары

**Разрешить *только* пользователям в организации регистрироваться для вебинары**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Чтобы разрешить всем пользователям, в том числе анонимным пользователям, регистрироваться в вебинары, запустите:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Если в параметрах собрания отключено анонимное участие, анонимные пользователи не смогут присоединяться к вебинасам. Дополнительные узнать и включить этот параметр см. в [Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>Сбор участия в собраниях

Если вы хотите, чтобы организаторы проанализировали, кто зарегистрировал вебинары и участвовал в них, необходимо включить политику **AllowEngagementReport.** Для этого в PowerShell запустите следующую команду:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>Настройка параметров вебинара

После включения вашей среды для вебинары больше не требуется управление администраторами. Политика управляет тем, какие параметры будут доступны организаторам вебинаров.

## <a name="related-topics"></a>Статьи по теме

- [Политики собраний в Teams - общие](meeting-policies-in-teams-general.md)
- [Документация по Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
