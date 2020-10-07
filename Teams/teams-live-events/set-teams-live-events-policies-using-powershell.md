---
title: Настройка политик живых событий с помощью PowerShell
author: lanachin
ms.author: v-lanac
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
description: Примеры использования PowerShell для настройки политик в Teams, чтобы управлять тем, кто может вести в организации события в реальном времени, и возможности, доступные в событиях.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e49c2dca91dca56366dd6b8a8ce460547043c120
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369154"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="5a9ca-103">Настройка политик трансляции Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a9ca-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="5a9ca-104">Вы можете использовать следующие командлеты Windows PowerShell для задания и назначения параметров политики для событий Live Events в teams:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="5a9ca-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5a9ca-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5a9ca-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5a9ca-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5a9ca-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5a9ca-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5a9ca-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="5a9ca-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="5a9ca-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="5a9ca-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="5a9ca-110">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="5a9ca-111">Перед выполнением этих командлетов необходимо подключиться к Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="5a9ca-112">Дополнительные сведения можно найти [в разделе Управление Skype для бизнеса Online с помощью Microsoft 365 или Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="5a9ca-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="5a9ca-113">Разрешение пользователям планировать Интерактивные события</span><span class="sxs-lookup"><span data-stu-id="5a9ca-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="5a9ca-114">Эти примеры предназначены для событий, создаваемых в Teams.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="5a9ca-115">Для событий, произвела внешние приложения или устройства, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="5a9ca-116">Дополнительные сведения можно найти [в разделе Предоставление пользователям возможности планировать события, созданные с помощью внешнего приложения или устройства](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="5a9ca-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="5a9ca-117">**Разрешение пользователю планировать события в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="5a9ca-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="5a9ca-118">Если пользователю назначена Глобальная политика, запустите и убедитесь, что для параметра *AllowBroadcastScheduling* задано *значение true*:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5a9ca-119">Затем назначьте пользователю глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="5a9ca-120">Пользовательские сценарии</span><span class="sxs-lookup"><span data-stu-id="5a9ca-120">User scenarios</span></span>
<span data-ttu-id="5a9ca-121">**Вы хотите, чтобы все пользователи в вашей организации смогли планировать мероприятия в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="5a9ca-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="5a9ca-122">Если пользователю назначена Глобальная политика, запустите и убедитесь, что для *AllowBroadcastScheduling* \* установлено *значение true*:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="5a9ca-123">Если пользователю назначена политика, отличная от глобальной политики, запустите и убедитесь, что для параметра *-AllowBroadcastScheduling* задано *значение true*:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="5a9ca-124">**Вы хотите, чтобы планирование событий в реальном времени была отключено в вашей организации**</span><span class="sxs-lookup"><span data-stu-id="5a9ca-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="5a9ca-125">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="5a9ca-126">Назначьте глобальным политикам всех пользователей в Организации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="5a9ca-127">**Вы хотите, чтобы у вас было большое количество пользователей для планирования событий в реальном времени и предотвратить их расписаний в наборе пользователей**</span><span class="sxs-lookup"><span data-stu-id="5a9ca-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="5a9ca-128">Запустите и убедитесь, что для *AllowBroadcastScheduling* установлено *значение true*:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="5a9ca-129">Затем назначьте пользователю или пользователям глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="5a9ca-130">Создать новую политику, которая не позволяет планировать Интерактивные события, выполните:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="5a9ca-131">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="5a9ca-132">Затем назначьте пользователям эту политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="5a9ca-133">**Вы хотите отключить планирование событий Live для большого количества пользователей и разрешить группе пользователей планировать их**</span><span class="sxs-lookup"><span data-stu-id="5a9ca-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="5a9ca-134">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="5a9ca-135">Затем назначьте этим пользователям глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="5a9ca-136">Создание политики для планирования событий в реальном времени, выполнение:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="5a9ca-137">Включить планирование событий в реальном времени, выполнить:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="5a9ca-138">Затем назначьте пользователям эту политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="5a9ca-139">Выбор пользователей, которые могут присоединиться к Live Events</span><span class="sxs-lookup"><span data-stu-id="5a9ca-139">Set who can join live events</span></span>
 
<span data-ttu-id="5a9ca-140">Настройте глобальную политику так, чтобы разрешить пользователям создавать события для всех пользователей, в том числе анонимных пользователей, а также выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="5a9ca-141">Настройка параметров записи для событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="5a9ca-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="5a9ca-142">Этот параметр применяется только к событиям, созданным в Teams.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="5a9ca-143">Установите для глобальной политики отключение записи для событий Live Events.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="5a9ca-144">Настройка живых подписей и субтитров в Live Events</span><span class="sxs-lookup"><span data-stu-id="5a9ca-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="5a9ca-145">Этот параметр применяется только к событиям, созданным в Teams.</span><span class="sxs-lookup"><span data-stu-id="5a9ca-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="5a9ca-146">Настройте глобальную политику на включение субтитров и субтитров (транскрипция) для участников события:</span><span class="sxs-lookup"><span data-stu-id="5a9ca-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="5a9ca-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5a9ca-147">Related topics</span></span>
- [<span data-ttu-id="5a9ca-148">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="5a9ca-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="5a9ca-149">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="5a9ca-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

