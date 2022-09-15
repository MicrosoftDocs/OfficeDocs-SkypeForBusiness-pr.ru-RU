---
title: Подготовка к вебинарам в Microsoft Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Узнайте, как управлять политиками вебинара для собраний Teams.
ms.openlocfilehash: 26863b26f960b50d81fa1d98090c3616d5b492a7
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706486"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Подготовка к вебинарам в Microsoft Teams

Эта статья поможет вам настроить организацию для размещения вебинары.

## <a name="what-are-webinars"></a>Что такое вебинары?

Вебинары — это структурированные собрания, на которых выступающие и участники имеют четкие роли, которые часто используются в целях обучения или в сценариях создания потенциальных клиентов по продажам и маркетингу.

После настройки вебинары в организации пользователи могут планировать вебинары и открывать регистрацию для участников. В отличие от традиционных собраний, которые включают множество обсуждений и назначений задач, вебинары предназначены для интерактивных презентаций и предоставляют средства для анализа участников.

> [!IMPORTANT]
> Чтобы разрешить пользователям настраивать вебинары, Microsoft Списки необходимо настроить в SharePoint, включив создание личных списков. Дополнительные сведения см. в [разделе "Параметры управления для Microsoft Списки](/sharepoint/control-lists)".

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Разрешить пользователям планировать вебинары в Центре администрирования Teams

Вы можете использовать Центр администрирования Teams для настройки вебинары для вашей организации. Политики для настройки вебинары можно найти в Центре администрирования Teams в разделе **"Политики** > **собраний"**.

### <a name="meeting-registration"></a>Регистрация собрания

Если вы включите эту функцию, пользователи смогут планировать вебинары. По умолчанию этот параметр включен. Если вы хотите отключить регистрацию собрания, задайте для этой политики значение **"Отключено"**.

> [!IMPORTANT]
> **Чтобы регистрация собрания была** включена, необходимо включить планирование частного собрания. По умолчанию эта политика включена в Центре администрирования Teams. Для учащихся в клиентах для образовательных учреждений эта политика по умолчанию отключена. Дополнительные сведения о том, как включить планирование частных собраний для учащихся, см. в Teams для образования [политиках и пакетах политик](policy-packages-edu.md).

### <a name="who-can-register"></a>Кто может зарегистрироваться

Если выбрать " **Все"**, все пользователи, включая анонимных пользователей, смогут зарегистрироваться и посетить вебинары. Если вы **выберете "Все в организации"**, только пользователи в организации смогут зарегистрироваться для вебинары. Если регистрация собрания отключена, этот параметр будет недоступен и никто не сможет зарегистрироваться для вебинары.

> [!NOTE]
> Значение по умолчанию для **параметра "Кто может зарегистрироваться****" — "Все в организации**" в клиентах для образовательных учреждений. Дополнительные сведения см[. в Teams для образования политики](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Отчет о задействовании

После этого организаторы могут просматривать отчеты о том, кто зарегистрировал и принял участие в вебинаре, которые они настроили. Эта политика включена по умолчанию. Дополнительные сведения см. в [разделе "Политики собраний" в отчете Teams — Engagement](meeting-policies-in-teams-general.md#engagement-report). Сведения о пользовательском интерфейсе см. в статье "Просмотр и скачивание отчетов о присутствии [на собраниях"](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Разрешить пользователям планировать вебинары с помощью PowerShell

Вы можете использовать следующие атрибуты в командлете **Set-CsTeamsMeetingPolicy** Windows PowerShell, чтобы настроить вебинары в Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Дополнительные сведения о командлете см. в разделе [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) .

> [!NOTE]
> Перед выполнением этих командлетов необходимо подключиться к Microsoft Teams PowerShell. Дополнительные сведения см. в [разделе "Управление Teams с помощью Microsoft Teams PowerShell"](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Разрешить пользователям планировать вебинары

Вы можете ограничить регистрацию только пользователями в организации или открыть ее для всех пользователей в клиенте и за его пределами. По умолчанию **whoCanRegister** включен и имеет значение **"Все** " для глобальной **политики (по умолчанию для всей** организации). Если вы хотите отключить регистрацию собрания, задайте **для параметра AllowMeetingRegistration значение** **False**.

> [!IMPORTANT]
> **Для работы AllowMeetingRegistration параметр AllowPrivateMeetingScheduling** должен иметь значение **True**.

1. Включение регистрации собрания

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Включение планирования частных собраний

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Настройка пользователей, которые могут зарегистрироваться для вебинары

**Разрешить *регистрацию* в вебинаре только пользователям в организации**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Чтобы разрешить всем, включая анонимных пользователей, регистрироваться в вебинаре, выполните следующую команду:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Если анонимное присоединение отключено в параметрах собрания, анонимные пользователи не могут присоединяться к вебинаре. Дополнительные сведения и включение этого параметра см. [в разделе "Параметры собрания" в Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Сбор сведений о присутствии на собрании

Параметр **AllowEngagementReport** позволяет узнать, кто зарегистрировал вебинары и участвовал в них. Эта политика включена по умолчанию. Чтобы отключить его, выполните следующую команду в PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Настройка параметров вебинара

После включения среды для вебинары дальнейшее управление администраторами не требуется. Политика определяет, какие параметры отображаются для организаторов вебинаров.

## <a name="related-topics"></a>См. также

- [Политики собраний в Teams — общие](meeting-policies-in-teams-general.md)
- [Документация по Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams для образования политики](easy-policy-setup-edu.md)
