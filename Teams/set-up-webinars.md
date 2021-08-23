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
ms.openlocfilehash: 23c637c1b4192f02ab3e95aa75bf434ae6453afd
ms.sourcegitcommit: 3650579196d5f340ef32b31ba975285e08ab1848
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2021
ms.locfileid: "58392916"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Настройка вебинары в Microsoft Teams

Эта статья поможет вам настроить вебинары для организации.

## <a name="what-are-webinars"></a>Что такое вебинары?

Вебинары — это структурированные собрания, на которых у участников и участников есть четкие роли, которые часто используются для обучения или для подготовки по продажам и маркетингу.

После настройки вебинары в организации пользователи могут планировать вебинары и открывать регистрацию для участников. В отличие от традиционных собраний, включавших множество обсуждений и заданий задач, вебинары предназначены для интерактивных презентаций и предоставляют инструменты для анализа участников.

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Разрешить пользователям планировать вебинары в центре Teams администрирования

В Центре администрирования Teams можно настроить вебинары для своей организации. Политики для вебинары можно найти в центре администрирования Teams в статье Политики собраний для  >  **собраний.**

### <a name="allow-meeting-registration"></a>Разрешить регистрацию на собрании

Если включить этот режим, пользователи смогут планировать вебинары. По умолчанию этот режим включен. Если вы хотите отключить регистрацию на собрании, установите для этой политики **отключение**.

> [!IMPORTANT]
> **Для регистрации собраний** необходимо разрешить планирование частных собраний. По умолчанию эта политика включена в центре Teams администрирования. Для учащихся в клиентах для образования эта политика по умолчанию отключена. Дополнительные сведения о том, как включить планирование частных собраний для учащихся, см. в Teams для образования политики и [пакеты политик.](policy-packages-edu.md)

### <a name="who-can-register"></a>Кто можете зарегистрировать

Если выбрать **Все**, все пользователи, включая анонимных пользователей, смогут зарегистрироваться и посетить вебинары. Если выбрать **Все в организации**, зарегистрировать вебинары могут только пользователи в организации. Если регистрация на собрании отключена, этот параметр будет не доступен и никто не сможет зарегистрироваться для вебинары.

> [!NOTE]
> По умолчанию для Кто **можно зарегистрировать** значение Все **в организации в** клиентах для образования. Дополнительные сведения см. [в Teams для образования политики](easy-policy-setup-edu.md).

### <a name="allow-engagement-report"></a>Разрешить отчет о взаимодействии

Если включить эту службу, организаторы смогут видеть отчеты о том, кто зарегистрировался и участвовал в вебинары, которые они настроили. По умолчанию эта политика отключена. Дополнительные сведения см. в теме [Политики собраний в Teams - Разрешить отчет о взаимодействии.](meeting-policies-in-teams-general.md#allow-engagement-report) Сведения о пользовательском интерфейсе см. в сведениях о просмотре [и скачии отчетов](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)об посещении собраний.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Разрешить пользователям планировать вебинары с помощью PowerShell

Чтобы настроить вебинары в Windows PowerShell, можно использовать следующие Teams атрибуты Windows PowerShell **Set-CsTeamsMeetingPolicy.**

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Дополнительные [сведения о cmdlet см.](/powershell/module/skype/set-csteamsmeetingpolicy) в этой публикации.

> [!NOTE]
> Перед запуском этих cmdlets необходимо подключение к Microsoft Teams PowerShell. Дополнительные сведения см. в [Teams помощью Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Разрешить пользователям планировать вебинары

Вы можете ограничить регистрацию только пользователями в организации или открыть ее для всех пользователей в клиенте и за ее пределами. По умолчанию **whoCanRegister** включен и установлено значение **Все**. Если вы хотите отключить регистрацию на собрании, установите **для allowMeetingRegistration (РазрешитьMeetingRegistration)** false **(Ложь).**

> [!IMPORTANT]
> **Чтобы разрешитьMeetingRegistration, задайте для allowPrivateMeetingMeetingScheduling** (Планирование планирования событий **AllowPrivateMeetingScheduling)** true.  Кроме того, Microsoft Списки необходимо настроить в SharePoint. Дополнительные параметры см. в [Microsoft Списки.](/sharepoint/control-lists)

1. Включить регистрацию собраний

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Включить планирование частных собраний

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Настройка пользователей, которые могут регистрироваться на вебинары

**Разрешить *регистрироваться* в вебинары только пользователям в организации**

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

## <a name="configure-webinar-settings"></a>Настройка параметров вебинара

После включения вашей среды для вебинары больше не требуется управление администраторами. Политика управляет тем, какие параметры будут доступны организаторам вебинаров.

## <a name="related-topics"></a>Связанные статьи

- [Политики собраний в Teams - общие](meeting-policies-in-teams-general.md)
- [Документация по Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams для образования Мастер политик](easy-policy-setup-edu.md)
