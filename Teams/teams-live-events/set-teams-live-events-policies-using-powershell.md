---
title: Настройка политик трансляции Microsoft Teams с помощью PowerShell
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
description: Примеры использования PowerShell для задания политик в Teams, чтобы управлять тем, кто может хранить события в сети в вашей организации, и функциональные возможности, доступные в создаваемых ими событиях.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb43e2a7420ef6c121cea93fd4cd8e4cc40ddfb2
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102360"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="9fed6-103">Настройка политик трансляции Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fed6-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="9fed6-104">Вы можете использовать следующие командлеты Windows PowerShell для задания и назначения параметров политики для событий Live Events в teams:</span><span class="sxs-lookup"><span data-stu-id="9fed6-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="9fed6-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9fed6-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9fed6-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9fed6-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9fed6-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9fed6-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="9fed6-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="9fed6-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="9fed6-109">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="9fed6-109">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="9fed6-110">Перед выполнением этих командлетов необходимо подключиться к Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fed6-110">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="9fed6-111">Дополнительные сведения можно найти [в разделе Управление Skype для бизнеса Online в Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="9fed6-111">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="9fed6-112">Разрешение пользователям планировать Интерактивные события</span><span class="sxs-lookup"><span data-stu-id="9fed6-112">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="9fed6-113">Эти примеры предназначены для событий, создаваемых в Teams.</span><span class="sxs-lookup"><span data-stu-id="9fed6-113">These examples are for events produced in Teams.</span></span> <span data-ttu-id="9fed6-114">Для событий, произвела внешние приложения или устройства, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="9fed6-114">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="9fed6-115">Дополнительные сведения можно найти [в разделе Предоставление пользователям возможности планировать события, созданные с помощью внешнего приложения или устройства](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="9fed6-115">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="9fed6-116">**Разрешение пользователю планировать события в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="9fed6-116">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="9fed6-117">Если пользователю назначена Глобальная политика, запустите и убедитесь, что для параметра *AllowBroadcastScheduling* задано *значение true*:</span><span class="sxs-lookup"><span data-stu-id="9fed6-117">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="9fed6-118">Затем назначьте пользователю глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="9fed6-118">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="9fed6-119">Пользовательские сценарии</span><span class="sxs-lookup"><span data-stu-id="9fed6-119">User scenarios</span></span>
<span data-ttu-id="9fed6-120">**Вы хотите, чтобы все пользователи в вашей организации смогли планировать мероприятия в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="9fed6-120">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="9fed6-121">Если пользователю назначена Глобальная политика, запустите и убедитесь, что для *AllowBroadcastScheduling* \* установлено *значение true*:</span><span class="sxs-lookup"><span data-stu-id="9fed6-121">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="9fed6-122">Если пользователю назначена политика, отличная от глобальной политики, запустите и убедитесь, что для параметра *-AllowBroadcastScheduling* задано *значение true*:</span><span class="sxs-lookup"><span data-stu-id="9fed6-122">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="9fed6-123">**Вы хотите, чтобы планирование событий в реальном времени была отключено в вашей организации**</span><span class="sxs-lookup"><span data-stu-id="9fed6-123">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="9fed6-124">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fed6-124">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="9fed6-125">Назначьте глобальным политикам всех пользователей в Организации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fed6-125">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="9fed6-126">**Вы хотите, чтобы у вас было большое количество пользователей для планирования событий в реальном времени и предотвратить их расписаний в наборе пользователей**</span><span class="sxs-lookup"><span data-stu-id="9fed6-126">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="9fed6-127">Запустите и убедитесь, что для *AllowBroadcastScheduling* установлено *значение true*:</span><span class="sxs-lookup"><span data-stu-id="9fed6-127">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="9fed6-128">Затем назначьте пользователю или пользователям глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="9fed6-128">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="9fed6-129">Создать новую политику, которая не позволяет планировать Интерактивные события, выполните:</span><span class="sxs-lookup"><span data-stu-id="9fed6-129">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="9fed6-130">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fed6-130">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="9fed6-131">Затем назначьте пользователям эту политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="9fed6-131">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="9fed6-132">**Вы хотите отключить планирование событий Live для большого количества пользователей и разрешить группе пользователей планировать их**</span><span class="sxs-lookup"><span data-stu-id="9fed6-132">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="9fed6-133">Отключите планирование событий в реальном времени, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fed6-133">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="9fed6-134">Затем назначьте этим пользователям глобальную политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="9fed6-134">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="9fed6-135">Создание политики для планирования событий в реальном времени, выполнение:</span><span class="sxs-lookup"><span data-stu-id="9fed6-135">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="9fed6-136">Включить планирование событий в реальном времени, выполнить:</span><span class="sxs-lookup"><span data-stu-id="9fed6-136">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="9fed6-137">Затем назначьте пользователям эту политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="9fed6-137">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="9fed6-138">Выбор пользователей, которые могут присоединиться к Live Events</span><span class="sxs-lookup"><span data-stu-id="9fed6-138">Set who can join live events</span></span>
 
<span data-ttu-id="9fed6-139">Настройте глобальную политику так, чтобы разрешить пользователям создавать события для всех пользователей, в том числе анонимных пользователей, а также выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9fed6-139">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="9fed6-140">Настройка параметров записи для событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="9fed6-140">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="9fed6-141">Этот параметр применяется только к событиям, созданным в Teams.</span><span class="sxs-lookup"><span data-stu-id="9fed6-141">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="9fed6-142">Установите для глобальной политики отключение записи для событий Live Events.</span><span class="sxs-lookup"><span data-stu-id="9fed6-142">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="9fed6-143">Настройка живых подписей и субтитров в Live Events</span><span class="sxs-lookup"><span data-stu-id="9fed6-143">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="9fed6-144">Этот параметр применяется только к событиям, созданным в Teams.</span><span class="sxs-lookup"><span data-stu-id="9fed6-144">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="9fed6-145">Настройте глобальную политику на включение субтитров и субтитров (транскрипция) для участников события:</span><span class="sxs-lookup"><span data-stu-id="9fed6-145">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="9fed6-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9fed6-146">Related topics</span></span>
- [<span data-ttu-id="9fed6-147">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="9fed6-147">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="9fed6-148">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="9fed6-148">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

