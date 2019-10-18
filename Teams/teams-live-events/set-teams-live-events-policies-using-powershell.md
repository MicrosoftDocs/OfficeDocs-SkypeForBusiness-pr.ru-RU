---
title: Настройка политик трансляции Microsoft Teams с помощью PowerShell
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Примеры использования PowerShell для задания политик в Teams, чтобы управлять тем, кто может хранить события в сети в вашей организации, и функциональные возможности, доступные в создаваемых ими событиях.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570172"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="0416d-103">Настройка политик трансляции Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0416d-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="0416d-104">Вы можете использовать следующие командлеты Windows PowerShell для задания и назначения параметров политики для событий Live Events в teams:</span><span class="sxs-lookup"><span data-stu-id="0416d-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="0416d-105">Get-Кстеамсмитингброадкастполици</span><span class="sxs-lookup"><span data-stu-id="0416d-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="0416d-106">Set-Кстеамсмитингброадкастполици</span><span class="sxs-lookup"><span data-stu-id="0416d-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="0416d-107">New-Кстеамсмитингброадкастполици</span><span class="sxs-lookup"><span data-stu-id="0416d-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="0416d-108">Grant-Кстеамсмитингброадкастполици</span><span class="sxs-lookup"><span data-stu-id="0416d-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="0416d-109">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="0416d-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="0416d-110">Разрешение пользователям планировать Интерактивные события</span><span class="sxs-lookup"><span data-stu-id="0416d-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="0416d-111">Эти примеры предназначены для событий, создаваемых в Teams.</span><span class="sxs-lookup"><span data-stu-id="0416d-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="0416d-112">Для событий, произвела внешние приложения или устройства, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="0416d-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="0416d-113">Дополнительные сведения можно найти [в разделе Предоставление пользователям возможности планировать события, созданные с помощью внешнего приложения или устройства](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="0416d-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="0416d-114">**Разрешение пользователю планировать события в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="0416d-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="0416d-115">Если пользователю назначена Глобальная политика, запустите и убедитесь, что для параметра *алловброадкастсчедулинг* задано *значение true*:</span><span class="sxs-lookup"><span data-stu-id="0416d-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="0416d-116">Затем назначьте пользователю глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="0416d-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="0416d-117">Пользовательские сценарии</span><span class="sxs-lookup"><span data-stu-id="0416d-117">User scenarios</span></span>
<span data-ttu-id="0416d-118">**Вы хотите, чтобы все пользователи в вашей организации смогли планировать мероприятия в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="0416d-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="0416d-119">Если пользователю назначена Глобальная политика, запустите и убедитесь, что для *алловброадкастсчедулинг* \* установлено *значение true*:</span><span class="sxs-lookup"><span data-stu-id="0416d-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="0416d-120">Если пользователю назначена политика, отличная от глобальной политики, запустите и убедитесь, что для параметра *-алловброадкастсчедулинг* задано *значение true*:</span><span class="sxs-lookup"><span data-stu-id="0416d-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="0416d-121">**Вы хотите, чтобы планирование событий в реальном времени была отключено в вашей организации**</span><span class="sxs-lookup"><span data-stu-id="0416d-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="0416d-122">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0416d-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="0416d-123">Назначьте глобальным политикам всех пользователей в Организации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0416d-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="0416d-124">**Вы хотите, чтобы у вас было большое количество пользователей для планирования событий в реальном времени и предотвратить их расписаний в наборе пользователей**</span><span class="sxs-lookup"><span data-stu-id="0416d-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="0416d-125">Запустите и убедитесь, что для *алловброадкастсчедулинг* установлено *значение true*:</span><span class="sxs-lookup"><span data-stu-id="0416d-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="0416d-126">Затем назначьте пользователю или пользователям глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="0416d-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="0416d-127">Создать новую политику, которая не позволяет планировать Интерактивные события, выполните:</span><span class="sxs-lookup"><span data-stu-id="0416d-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="0416d-128">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0416d-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="0416d-129">Затем назначьте пользователям эту политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="0416d-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="0416d-130">**Вы хотите отключить планирование событий Live для большого количества пользователей и разрешить группе пользователей планировать их**</span><span class="sxs-lookup"><span data-stu-id="0416d-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="0416d-131">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0416d-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="0416d-132">Затем назначьте этим пользователям глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="0416d-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="0416d-133">Создание политики для планирования событий в реальном времени, выполнение:</span><span class="sxs-lookup"><span data-stu-id="0416d-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="0416d-134">Включить планирование событий в реальном времени, выполнить:</span><span class="sxs-lookup"><span data-stu-id="0416d-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="0416d-135">Затем назначьте пользователям эту политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="0416d-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="0416d-136">Выбор пользователей, которые могут присоединиться к Live Events</span><span class="sxs-lookup"><span data-stu-id="0416d-136">Set who can join live events</span></span>
 
<span data-ttu-id="0416d-137">Настройте глобальную политику так, чтобы разрешить пользователям создавать события для всех пользователей, в том числе анонимных пользователей, а также выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0416d-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="0416d-138">Настройка параметров записи для событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="0416d-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="0416d-139">Этот параметр применяется только к событиям, созданным в Teams.</span><span class="sxs-lookup"><span data-stu-id="0416d-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="0416d-140">Установите для глобальной политики отключение записи для событий Live Events.</span><span class="sxs-lookup"><span data-stu-id="0416d-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="0416d-141">Настройка живых подписей и субтитров в Live Events</span><span class="sxs-lookup"><span data-stu-id="0416d-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="0416d-142">Этот параметр применяется только к событиям, созданным в Teams.</span><span class="sxs-lookup"><span data-stu-id="0416d-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="0416d-143">Настройте глобальную политику на включение субтитров и субтитров (транскрипция) для участников события:</span><span class="sxs-lookup"><span data-stu-id="0416d-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="0416d-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0416d-144">Related topics</span></span>
- [<span data-ttu-id="0416d-145">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="0416d-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


