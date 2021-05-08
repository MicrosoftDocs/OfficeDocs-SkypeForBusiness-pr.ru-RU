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
ms.openlocfilehash: 739c0b5494b0ecc5b9a20fd8db4756313848325b
ms.sourcegitcommit: e5d6a2c3ad45c1285016b93ec4c7afea907d71a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275527"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Настройка вебинары в Microsoft Teams

Эта статья поможет вам настроить вебинары для организации.

## <a name="what-are-webinars"></a>Что такое вебинары?

Вебинары — это структурированные собрания, на которых преподаватели и участники имеют четкие роли, которые часто используются для обучения или для подготовки по продажам и маркетингу.

После настройки вебинары в организации пользователи могут планировать вебинары и открывать регистрацию для участников. В отличие от обычных собраний, которые содержат много обсуждений и заданий задач, вебинары предназначены для интерактивных презентаций и предоставляют инструменты для анализа участников.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Разрешить пользователям планировать вебинары с помощью PowerShell

Чтобы настроить вебинары в Teams, можно использовать следующие атрибуты Windows PowerShell **Set-CsTeamsMeetingPolicy:**

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Дополнительные сведения о cmdlet см. в документе [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Перед запуском этих cmdlets необходимо подключение к Skype для бизнеса Online PowerShell. Дополнительные сведения см. в Skype для бизнеса Online с [помощью Microsoft 365 или Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

### <a name="allow-users-to-schedule-webinars"></a>Разрешить пользователям планировать вебинары

Чтобы разрешить пользователям в организации планировать вебинары, запустите:

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a>Настройка пользователей, которые могут регистрироваться на вебинары

Вы можете ограничить регистрацию только пользователями в организации или открыть ее для всех пользователей в клиенте и за ее пределами. По умолчанию **whoCanRegister** включен и установлено значение **Все**. Если вы хотите отключить регистрацию на собрании, установите **для WhoCanRegister (WhoCanRegister)** веское.) 

> [!IMPORTANT]
> Помните, что для работы **WhoCanRegister** для  планирования **allowPrivateMeeting Должно** быть задано true. Кроме того, списки Майкрософт необходимо настроить в SharePoint. Дополнительные параметры см. [в параметрах управления списками Майкрософт.](/sharepoint/control-lists)

**Чтобы разрешить *только* пользователям в вашей организации регистрироваться для вебинары, запустите:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Затем запустите:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Чтобы разрешить всем пользователям, в том числе анонимным пользователям, регистрироваться в вебинары, запустите:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Затем запустите:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> Если в параметрах собрания отключено анонимное участие, анонимные пользователи не смогут присоединяться к вебинасам. Дополнительные узнать и включить этот параметр см. в [Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>Сбор участия в собраниях

Если вы хотите, чтобы организаторы проанализировали, кто зарегистрировал вебинары и участвовал в них, необходимо включить политику **AllowEngagementReport.** Для этого в PowerShell запустите следующую команду:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>Настройка параметров вебинара

После включения вашей среды для вебинаеров больше не требуется управление администраторами. Политика управляет тем, какие параметры будут доступны организаторам вебинаров.

## <a name="related-topics"></a>Статьи по теме

- [Политики собраний в Teams - общие](meeting-policies-in-teams-general.md)
- [Документация по Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
