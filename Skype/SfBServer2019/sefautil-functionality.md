---
title: Поддержка использования функций SEFAUtil в PowerShell в Skype для бизнеса Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Узнайте, как использовать PowerShell для получения функций SEFAUtil в Skype для бизнеса Server 2019 после установки накопительного обновления 1.
ms.openlocfilehash: d97dd84a3d05cf18752e40dd73a8c5f7e9752d3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120510"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="fc813-103">Использование функций SEFAUtil с помощью PowerShell в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc813-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="fc813-104">SEFAUtil (активация дополнительных функций расширения) позволяет администраторам и агентам службы поддержки Skype для бизнеса настраивать параметры делегирования, переададации вызовов и группового вызова от имени пользователя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fc813-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="fc813-105">Этот инструмент также позволяет администраторам запрашивать параметры маршрутивки вызовов, опубликованные для конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc813-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="fc813-106">После установки накопительного обновления Skype для бизнеса Server 2019 июля следующие функции, которые в настоящее время можно управлять только с помощью SEFAUtil, также будут управляться с помощью PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc813-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="fc813-107">Параметры переададки вызовов</span><span class="sxs-lookup"><span data-stu-id="fc813-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="fc813-108">Параметры делегирования</span><span class="sxs-lookup"><span data-stu-id="fc813-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="fc813-109">Члены группы и связанные с ними параметры</span><span class="sxs-lookup"><span data-stu-id="fc813-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="fc813-110">Параметры переададки вызовов</span><span class="sxs-lookup"><span data-stu-id="fc813-110">Call forwarding settings</span></span>

<span data-ttu-id="fc813-111">Администраторы могут изменять параметры переадправления вызовов, используя следующий cmdlet в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc813-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="fc813-112">Этот комдлет возвращает указанные параметры переададки вызовов пользователя в качестве объекта и отображает то же самое на экране.</span><span class="sxs-lookup"><span data-stu-id="fc813-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="fc813-113">Этот cmdlet изменяет параметры переададции вызовов указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc813-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="fc813-114">Этот комдлет возвращает указанные параметры переададки зовов пользователя в качестве объекта и отображает то же самое на экране в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="fc813-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="fc813-115">В случае сбоя будет показано соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fc813-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="fc813-116">Этот кодлет отключает параметры переададки вызовов пользователя (здесь мы покажем два разных примера параметров).</span><span class="sxs-lookup"><span data-stu-id="fc813-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="fc813-117">Этот кодлет изменяет параметры переададции вызовов пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc813-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="fc813-118">Этот cmdlet изменяет параметры SimulRing (опять же, с двумя примерами параметров, один для голосовой почты без ответа, а второй без ответа на другие).</span><span class="sxs-lookup"><span data-stu-id="fc813-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="fc813-119">Параметры делегирования</span><span class="sxs-lookup"><span data-stu-id="fc813-119">Delegation settings</span></span>

<span data-ttu-id="fc813-120">Администраторы могут изменять параметры делегирования, используя следующий cmdlet в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc813-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="fc813-121">Этот комлет возвращает объект списка делегатов и отображает указанный список делегатов пользователя в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="fc813-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="fc813-122">В случае сбоя будет показано соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fc813-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="fc813-123">Этот кодлет изменяет параметры делегирования указанного пользователя, возвращает объект списка делегатов и отображает список делегатов в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="fc813-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="fc813-124">В случае сбоя будет показано соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fc813-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="fc813-125">Этот кодлет добавляет или удаляет делегата.</span><span class="sxs-lookup"><span data-stu-id="fc813-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="fc813-126">Этот список задает список делегатов определенным делегатам.</span><span class="sxs-lookup"><span data-stu-id="fc813-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="fc813-127">Члены группы и связанные с ними параметры</span><span class="sxs-lookup"><span data-stu-id="fc813-127">Team members and related settings</span></span>

<span data-ttu-id="fc813-128">Администраторы могут изменять членов группы и связанные с ними параметры, используя следующий командлет в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc813-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="fc813-129">Этот командлет возвращает объект, содержащий список членов группы, и отображает объект на экране в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="fc813-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="fc813-130">В случае сбоя будет показано соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fc813-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="fc813-131">Этот командлет изменяет список членов команды указанного пользователя, возвращает объект, содержащий список членов группы, и отображает объект на экране в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="fc813-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="fc813-132">В случае сбоя будет показано соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fc813-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="fc813-133">Этот командлет добавляет или удаляет членов группы.</span><span class="sxs-lookup"><span data-stu-id="fc813-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="fc813-134">Этот командлет задает список команд определенным участникам.</span><span class="sxs-lookup"><span data-stu-id="fc813-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="fc813-135">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="fc813-135">More information</span></span>

<span data-ttu-id="fc813-136">Для локального развертывания команды, введенные в эту функцию, могут запускаться только членами следующих групп на уровне доступа, указанном ниже:</span><span class="sxs-lookup"><span data-stu-id="fc813-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="fc813-137">CsAdministrator — get and Set for all cmdlets</span><span class="sxs-lookup"><span data-stu-id="fc813-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="fc813-138">CsVoiceAdministrator — get and Set for all cmdlets</span><span class="sxs-lookup"><span data-stu-id="fc813-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="fc813-139">CsHelpDesk — get for all cmdlets</span><span class="sxs-lookup"><span data-stu-id="fc813-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="fc813-140">Дополнительные сведения об этих ролях администратора см. в рублях [Create Skype for Business Server Control Panel Administrators.](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)</span><span class="sxs-lookup"><span data-stu-id="fc813-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="fc813-141">Администратор может получить доступ к этим комлетам, непосредственно или удаленно войдя на серверный компьютер.</span><span class="sxs-lookup"><span data-stu-id="fc813-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="fc813-142">Для гибридного развертывания администраторы Skype для бизнеса должны иметь возможность вызывать get and Set для всех cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fc813-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="fc813-143">Дополнительные сведения о полном списке ролей см. в дополнительных [сведениях о ролях администратора.](/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="fc813-143">For more information about the full list of roles, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="fc813-144">Необходимо включить автоматическое обнаружение сервера.</span><span class="sxs-lookup"><span data-stu-id="fc813-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="fc813-145">Дополнительные требования к лицензированию для использования этих кодлетов не будут введены.</span><span class="sxs-lookup"><span data-stu-id="fc813-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>