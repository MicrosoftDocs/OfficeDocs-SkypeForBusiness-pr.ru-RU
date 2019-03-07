---
title: Настройка политик трансляции Microsoft Teams с помощью PowerShell
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Примеры того, как использовать PowerShell для определения политик в группах, чтобы контролировать, кто сохранения live события в вашей организации и функции, доступные в события, которые они создают
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23cf75c8e764920a2d77c3bbe6c0cb3711c22f04
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459630"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="b8780-103">Настройка политик трансляции Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8780-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="b8780-104">Можно использовать следующие командлеты Windows PowerShell для установки и назначить параметры политики для live событий в группах:</span><span class="sxs-lookup"><span data-stu-id="b8780-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="b8780-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="b8780-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="b8780-106">SET-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="b8780-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="b8780-107">Новый CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="b8780-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="b8780-108">Предоставление CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="b8780-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="b8780-109">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="b8780-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="b8780-110">Разрешить пользователям планировать событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="b8780-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="b8780-111">В этих примерах используются события быстрого запуска.</span><span class="sxs-lookup"><span data-stu-id="b8780-111">These examples are for quick start events.</span></span> <span data-ttu-id="b8780-112">Для внешних кодировщика событий существуют дополнительные действия, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="b8780-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="b8780-113">Дополнительные сведения можно [Разрешить пользователям планировать события внешнего кодировщика](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span><span class="sxs-lookup"><span data-stu-id="b8780-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="b8780-114">**Предоставление разрешений пользователю для планирования событий в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="b8780-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="b8780-115">Если пользователю назначена глобальную политику, запуск и убедитесь, что параметр *AllowBroadcastScheduling* задано значение *True*:</span><span class="sxs-lookup"><span data-stu-id="b8780-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="b8780-116">Назначьте пользователя для глобальной политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="b8780-117">Пользовательские сценарии</span><span class="sxs-lookup"><span data-stu-id="b8780-117">User scenarios</span></span>
<span data-ttu-id="b8780-118">**Все пользователи в вашей организации должны иметь возможность планирования событий в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="b8780-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="b8780-119">Если пользователи назначаются глобальную политику, запустите и убедитесь, что *AllowBroadcastScheduling* \* имеет значение *True*:</span><span class="sxs-lookup"><span data-stu-id="b8780-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="b8780-120">Если пользователи назначена политика, отличный от глобальной политики, запуск и убедитесь, что *- AllowBroadcastScheduling* задано значение *True*:</span><span class="sxs-lookup"><span data-stu-id="b8780-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="b8780-121">**Требуется событий в реальном времени планирования требуется запретить в организации**</span><span class="sxs-lookup"><span data-stu-id="b8780-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="b8780-122">Отключение планирования событий в реальном времени, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="b8780-123">Назначение всех пользователей в вашей организации для глобальной политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="b8780-124">**Большое число пользователи должны иметь возможность планировать события и предотвратить планирования их группы пользователей**</span><span class="sxs-lookup"><span data-stu-id="b8780-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="b8780-125">Запуск и убедитесь, что *AllowBroadcastScheduling* задано значение *True*:</span><span class="sxs-lookup"><span data-stu-id="b8780-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="b8780-126">Затем назначение одного или нескольких пользователей для глобальной политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="b8780-127">Создайте новую политику, которая не позволяет планирования live события, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="b8780-128">Отключение планирования событий в реальном времени, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="b8780-129">Затем назначение пользователей для этой политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="b8780-130">**Чтобы отключить трансляция расписания для большого числа пользователей и разрешить группы пользователей, чтобы запланировать их**</span><span class="sxs-lookup"><span data-stu-id="b8780-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="b8780-131">Отключение планирования событий в реальном времени, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="b8780-132">Затем назначение этих пользователей для глобальной политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="b8780-133">Создание политики, чтобы разрешить планирование событий в реальном времени, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="b8780-134">Включить планирование событий в реальном времени, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="b8780-135">Затем назначение пользователей для этой политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="b8780-136">Набор, который сможет присоединиться к событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="b8780-136">Set who can join live events</span></span>
 
<span data-ttu-id="b8780-137">Задайте для глобальной политики, чтобы разрешить пользователям создавать события, все, включая анонимных пользователей, можно посещение, выполните:</span><span class="sxs-lookup"><span data-stu-id="b8780-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="b8780-138">Установить параметр записи для событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="b8780-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="b8780-139">Этот параметр применяется только к события быстрого запуска.</span><span class="sxs-lookup"><span data-stu-id="b8780-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="b8780-140">Задайте для глобальной политики для отключения записи для событий в реальном времени:</span><span class="sxs-lookup"><span data-stu-id="b8780-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="b8780-141">Задайте транскрибирования и перевода в режиме реального времени события (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="b8780-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="b8780-142">Этот параметр применяется только к события быстрого запуска.</span><span class="sxs-lookup"><span data-stu-id="b8780-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="b8780-143">Задайте для глобальной политики для включения транскрибирования и перевода участников событий:</span><span class="sxs-lookup"><span data-stu-id="b8780-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="b8780-144">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b8780-144">Related topics</span></span>
- [<span data-ttu-id="b8780-145">Настройка для групп событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="b8780-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


