---
title: Настройка политик трансляций с помощью PowerShell
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Примеры использования PowerShell для применения политик в Teams для контроля над тем, кто может проводить трансляции в организации и какие функции доступны для них.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815629"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="6264b-103">Настройка политик трансляции Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6264b-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="6264b-104">Для настройки и назначения параметров политики для трансляций в Teams можно использовать следующие Windows PowerShell командлеты:</span><span class="sxs-lookup"><span data-stu-id="6264b-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="6264b-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="6264b-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="6264b-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="6264b-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="6264b-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="6264b-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="6264b-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="6264b-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="6264b-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6264b-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="6264b-110">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="6264b-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="6264b-111">Перед запуском этих cmdlets необходимо подключение к Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6264b-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="6264b-112">Дополнительные сведения см. в управлении [Skype для бизнеса Online с помощью Microsoft 365 или Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="6264b-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="6264b-113">Разрешить пользователям планировать трансляции</span><span class="sxs-lookup"><span data-stu-id="6264b-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="6264b-114">Эти примеры можно привести для событий, произведенных в Teams.</span><span class="sxs-lookup"><span data-stu-id="6264b-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="6264b-115">Для событий, произведенных с внешним приложением или устройством, необходимо сделать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="6264b-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="6264b-116">Дополнительные сведения см. в статьи "Возможность планировать события, произведенные с помощью внешнего [приложения или устройства".](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="6264b-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="6264b-117">**Разрешить пользователю планировать трансляции**</span><span class="sxs-lookup"><span data-stu-id="6264b-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="6264b-118">Если пользователю назначена глобальная политика, запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет *true:*</span><span class="sxs-lookup"><span data-stu-id="6264b-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="6264b-119">Затем назначьте пользователя глобальной политике и запустите 3</span><span class="sxs-lookup"><span data-stu-id="6264b-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="6264b-120">Сценарии для пользователей</span><span class="sxs-lookup"><span data-stu-id="6264b-120">User scenarios</span></span>
<span data-ttu-id="6264b-121">**Вы хотите, чтобы все пользователи в организации могли планировать трансляции**</span><span class="sxs-lookup"><span data-stu-id="6264b-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="6264b-122">Если пользователям назначена глобальная политика, запустите и убедитесь, что для *allowBroadcastScheduling* \*установлено *true:*</span><span class="sxs-lookup"><span data-stu-id="6264b-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="6264b-123">Если пользователям назначена политика, которая не является глобальной, запустите и проверьте, установлено ли для этого правила *-AllowBroadcastScheduling (Планирование AllowBroadcast)* *true:*</span><span class="sxs-lookup"><span data-stu-id="6264b-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="6264b-124">**Вы хотите отключить возможность планирования трансляций в организации**</span><span class="sxs-lookup"><span data-stu-id="6264b-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="6264b-125">Отключите планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="6264b-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="6264b-126">Назначьте глобальной политике всех пользователей в организации, запустите 4</span><span class="sxs-lookup"><span data-stu-id="6264b-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="6264b-127">**Вы хотите, чтобы большое количество пользователей могли планировать трансляции и не допустить их планирование для набора пользователей**</span><span class="sxs-lookup"><span data-stu-id="6264b-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="6264b-128">Запустите и убедитесь, что *для allowBroadcastScheduling* установлено *true:*</span><span class="sxs-lookup"><span data-stu-id="6264b-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="6264b-129">Затем назначьте пользователя или пользователей глобальной политике и запустите 3</span><span class="sxs-lookup"><span data-stu-id="6264b-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="6264b-130">Создайте политику, которая не позволяет запланировать трансляции, запустите 4</span><span class="sxs-lookup"><span data-stu-id="6264b-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="6264b-131">Отключите планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="6264b-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="6264b-132">Затем назначьте пользователей этой политике и запустите 3</span><span class="sxs-lookup"><span data-stu-id="6264b-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="6264b-133">**Вы хотите отключить планирование трансляций для большого количества пользователей и разрешить им планировать трансляции.**</span><span class="sxs-lookup"><span data-stu-id="6264b-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="6264b-134">Отключите планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="6264b-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="6264b-135">Затем назначьте этим пользователям глобальную политику и запустите 3</span><span class="sxs-lookup"><span data-stu-id="6264b-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="6264b-136">Создайте политику, чтобы разрешить планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="6264b-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="6264b-137">Включить планирование трансляций, выполнить:</span><span class="sxs-lookup"><span data-stu-id="6264b-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="6264b-138">Затем назначьте пользователей этой политике и запустите 3</span><span class="sxs-lookup"><span data-stu-id="6264b-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="6264b-139">Настройка того, кто может присоединяться к трансляциям</span><span class="sxs-lookup"><span data-stu-id="6264b-139">Set who can join live events</span></span>
 
<span data-ttu-id="6264b-140">Установите глобальную политику, чтобы разрешить пользователям создавать события, в которых могут участвовать все пользователи, в том числе анонимные пользователи, и запускать:</span><span class="sxs-lookup"><span data-stu-id="6264b-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="6264b-141">Настройка параметра записи для трансляций</span><span class="sxs-lookup"><span data-stu-id="6264b-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="6264b-142">Этот параметр применяется только к мероприятиям, проданной в Teams.</span><span class="sxs-lookup"><span data-stu-id="6264b-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="6264b-143">Установите глобальную политику для отключения записи трансляций.</span><span class="sxs-lookup"><span data-stu-id="6264b-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="6264b-144">Настройка субтитров в трансляциях</span><span class="sxs-lookup"><span data-stu-id="6264b-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="6264b-145">Этот параметр применяется только к мероприятиям, проданной в Teams.</span><span class="sxs-lookup"><span data-stu-id="6264b-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="6264b-146">Установите глобальную политику, чтобы включить живые субтитры (транскрипцию) для участников события:</span><span class="sxs-lookup"><span data-stu-id="6264b-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="6264b-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6264b-147">Related topics</span></span>
- [<span data-ttu-id="6264b-148">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="6264b-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="6264b-149">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="6264b-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

