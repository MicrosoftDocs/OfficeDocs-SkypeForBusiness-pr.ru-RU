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
description: Примеры использования PowerShell для применения политик в Teams для контроля над тем, кто может проводить трансляции в организации, и возможностями, доступными для них.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119148"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="e81d1-103">Настройка политик трансляции Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e81d1-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="e81d1-104">Для настройки и назначения параметров политики для трансляций в Teams можно использовать следующие Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e81d1-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="e81d1-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="e81d1-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="e81d1-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="e81d1-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="e81d1-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="e81d1-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="e81d1-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="e81d1-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="e81d1-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="e81d1-109">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="e81d1-110">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="e81d1-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="e81d1-111">Перед запуском этих cmdlets необходимо подключение к Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e81d1-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="e81d1-112">Дополнительные сведения см. в Skype для бизнеса Online с [помощью Microsoft 365 или Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e81d1-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="e81d1-113">Разрешить пользователям планировать трансляции</span><span class="sxs-lookup"><span data-stu-id="e81d1-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="e81d1-114">Эти примеры можно привести для событий, которые были произведены в Teams.</span><span class="sxs-lookup"><span data-stu-id="e81d1-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="e81d1-115">Для событий, произведенных с помощью внешнего приложения или устройства, необходимо сделать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="e81d1-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="e81d1-116">Дополнительные сведения см. в статьи Возможность пользователям планировать события, которые были произведены с помощью [внешнего приложения или устройства.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="e81d1-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="e81d1-117">**Разрешить пользователю планировать трансляции**</span><span class="sxs-lookup"><span data-stu-id="e81d1-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="e81d1-118">Если пользователю назначена глобальная политика, запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет *true:*</span><span class="sxs-lookup"><span data-stu-id="e81d1-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="e81d1-119">Затем назначьте пользователя глобальной политике и запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="e81d1-120">Сценарии для пользователей</span><span class="sxs-lookup"><span data-stu-id="e81d1-120">User scenarios</span></span>
<span data-ttu-id="e81d1-121">**Вы хотите, чтобы все пользователи в организации могли планировать трансляции**</span><span class="sxs-lookup"><span data-stu-id="e81d1-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="e81d1-122">Если пользователям назначена глобальная политика, запустите и убедитесь, что *для allowBroadcastScheduling* \*установлено *true:*</span><span class="sxs-lookup"><span data-stu-id="e81d1-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="e81d1-123">Если пользователям назначена политика, которая не является глобальной, запустите и убедитесь, что для *-AllowBroadcastScheduling* за установлено *true:*</span><span class="sxs-lookup"><span data-stu-id="e81d1-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="e81d1-124">**Вы хотите отключить планирование трансляций в организации**</span><span class="sxs-lookup"><span data-stu-id="e81d1-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="e81d1-125">Отключите планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="e81d1-126">Назначьте глобальной политике всех пользователей в организации и запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="e81d1-127">**Вы хотите, чтобы большое количество пользователей могли планировать трансляции и запретить им планировать их**</span><span class="sxs-lookup"><span data-stu-id="e81d1-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="e81d1-128">Запустите и убедитесь, что *для allowBroadcastScheduling* за установлено *true:*</span><span class="sxs-lookup"><span data-stu-id="e81d1-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="e81d1-129">Затем назначьте пользователя или пользователей глобальной политике, запустите 2016.</span><span class="sxs-lookup"><span data-stu-id="e81d1-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="e81d1-130">Создайте политику, которая не позволяет запланировать трансляции, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="e81d1-131">Отключите планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="e81d1-132">Затем назначьте пользователей этой политике, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="e81d1-133">**Вы хотите отключить планирование трансляций для большого количества пользователей и разрешить им планировать события.**</span><span class="sxs-lookup"><span data-stu-id="e81d1-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="e81d1-134">Отключите планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="e81d1-135">Затем назначьте этих пользователей глобальной политике и запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="e81d1-136">Создайте политику, чтобы разрешить планирование трансляций, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="e81d1-137">Включить планирование трансляций, выполнить:</span><span class="sxs-lookup"><span data-stu-id="e81d1-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="e81d1-138">Затем назначьте пользователей этой политике, запустите:</span><span class="sxs-lookup"><span data-stu-id="e81d1-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="e81d1-139">Настройка того, кто может присоединяться к трансляциям</span><span class="sxs-lookup"><span data-stu-id="e81d1-139">Set who can join live events</span></span>
 
<span data-ttu-id="e81d1-140">Установите глобальную политику, чтобы разрешить пользователям создавать события, которые могут посещать все пользователи, включая анонимных, а также запускать:</span><span class="sxs-lookup"><span data-stu-id="e81d1-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="e81d1-141">Настройка параметра записи для трансляций</span><span class="sxs-lookup"><span data-stu-id="e81d1-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="e81d1-142">Этот параметр применяется только к событиям, которые были произведены Teams.</span><span class="sxs-lookup"><span data-stu-id="e81d1-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="e81d1-143">Установите глобальную политику, чтобы отключить запись для трансляций:</span><span class="sxs-lookup"><span data-stu-id="e81d1-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="e81d1-144">Настройка субтитров в трансляциях</span><span class="sxs-lookup"><span data-stu-id="e81d1-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="e81d1-145">Этот параметр применяется только к событиям, которые были произведены Teams.</span><span class="sxs-lookup"><span data-stu-id="e81d1-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="e81d1-146">Установите глобальную политику, чтобы включить субтитры (транскрипцию) для участников мероприятия:</span><span class="sxs-lookup"><span data-stu-id="e81d1-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="e81d1-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e81d1-147">Related topics</span></span>
- [<span data-ttu-id="e81d1-148">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="e81d1-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="e81d1-149">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="e81d1-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)