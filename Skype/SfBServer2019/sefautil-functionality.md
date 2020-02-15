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
description: 'Сводка: в этой статье рассказывается, как использовать PowerShell для получения функциональных возможностей SEFAUtil в Skype для бизнеса Server 2019 после установки накопительного пакета обновления 1.'
ms.openlocfilehash: 1a18a954e40ba7a0c72e4d87b4b3c943e827f2a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049141"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="4eea0-103">Использование функций SEFAUtil с помощью PowerShell в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="4eea0-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="4eea0-104">SEFAUtil (дополнительный добавочный номер функции расширения) позволяет администраторам и агентам службы поддержки пользователей Skype для бизнеса Server настраивать параметры ответа на звонки, переадресацию звонка и групповые звонки от имени пользователя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4eea0-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="4eea0-105">Это средство также позволяет администраторам запрашивать параметры маршрутизации вызовов, опубликованные для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4eea0-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="4eea0-106">После установки накопительного пакета обновления для Skype для бизнеса Server 2019 Июль в настоящее время можно управлять следующими функциями, которые в настоящее время управляются только с помощью SEFAUtil, с помощью PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eea0-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="4eea0-107">Параметры переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="4eea0-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="4eea0-108">Параметры делегирования</span><span class="sxs-lookup"><span data-stu-id="4eea0-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="4eea0-109">Участники группы и связанные с ней параметры</span><span class="sxs-lookup"><span data-stu-id="4eea0-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="4eea0-110">Параметры переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="4eea0-110">Call forwarding settings</span></span>

<span data-ttu-id="4eea0-111">Администраторы могут изменять параметры переадресации звонков с помощью следующего командлета в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eea0-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="4eea0-112">Этот командлет возвращает параметры переадресации вызовов указанного пользователя в виде объекта и отображает то же самое на экране.</span><span class="sxs-lookup"><span data-stu-id="4eea0-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="4eea0-113">Этот командлет изменяет параметры переадресации звонков указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4eea0-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="4eea0-114">Этот командлет возвращает параметры переадресации вызовов указанного пользователя в виде объекта и отображается на экране в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="4eea0-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="4eea0-115">В случае сбоя отображается соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4eea0-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="4eea0-116">Этот командлет отключает параметры переадресации звонков пользователя (здесь показаны два различных примера параметров).</span><span class="sxs-lookup"><span data-stu-id="4eea0-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="4eea0-117">Этот командлет изменяет параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="4eea0-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="4eea0-118">Этот командлет изменяет параметры выполнение (опять с двумя примерами параметров, один из которых не отвечает на голосовую почту, а второй не отвечает другим).</span><span class="sxs-lookup"><span data-stu-id="4eea0-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="4eea0-119">Параметры делегирования</span><span class="sxs-lookup"><span data-stu-id="4eea0-119">Delegation settings</span></span>

<span data-ttu-id="4eea0-120">Администраторы могут изменить параметры делегирования с помощью следующего командлета в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eea0-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="4eea0-121">Этот командлет возвращает объект List делегата и отображает список делегатов указанного пользователя в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="4eea0-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="4eea0-122">В случае сбоя отображается соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4eea0-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="4eea0-123">Этот командлет изменяет параметры делегирования указанного пользователя, возвращает объект List of delegates и отображает список делегатов в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="4eea0-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="4eea0-124">В случае сбоя отображается соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4eea0-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="4eea0-125">Этот командлет добавляет или удаляет делегата.</span><span class="sxs-lookup"><span data-stu-id="4eea0-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="4eea0-126">Этот командлет задает список делегатов для определенных делегатов.</span><span class="sxs-lookup"><span data-stu-id="4eea0-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="4eea0-127">Участники группы и связанные с ней параметры</span><span class="sxs-lookup"><span data-stu-id="4eea0-127">Team members and related settings</span></span>

<span data-ttu-id="4eea0-128">Администраторы могут изменять участников группы и связанные с ней параметры с помощью следующего командлета в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eea0-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="4eea0-129">Этот командлет возвращает объект, содержащий список участников группы, и отображает объект на экране в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="4eea0-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="4eea0-130">В случае сбоя отображается соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4eea0-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="4eea0-131">Этот командлет изменяет список участников группы указанного пользователя, возвращает объект, который содержит список участников группы, и отображает объект на экране в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="4eea0-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="4eea0-132">В случае сбоя отображается соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4eea0-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="4eea0-133">Этот командлет добавляет или удаляет участников группы.</span><span class="sxs-lookup"><span data-stu-id="4eea0-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="4eea0-134">Этот командлет задает список определенных членов группы.</span><span class="sxs-lookup"><span data-stu-id="4eea0-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="4eea0-135">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4eea0-135">More information</span></span>

<span data-ttu-id="4eea0-136">Для локальных развертываний командлеты, представленные в этой функции, могут запускаться только членами следующих групп на уровне доступа, указанным ниже:</span><span class="sxs-lookup"><span data-stu-id="4eea0-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="4eea0-137">CsAdministrator — Get и Set для всех командлетов</span><span class="sxs-lookup"><span data-stu-id="4eea0-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="4eea0-138">CsVoiceAdministrator — Get и Set для всех командлетов</span><span class="sxs-lookup"><span data-stu-id="4eea0-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="4eea0-139">CsHelpDesk — Get для всех командлетов</span><span class="sxs-lookup"><span data-stu-id="4eea0-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="4eea0-140">Более подробную информацию об этих ролях администратора можно узнать в статье [Создание администраторов панели управления Skype для бизнеса Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="4eea0-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="4eea0-141">Администратор может получить доступ к этим командлетам непосредственно или с удаленного компьютера для входа на сервер.</span><span class="sxs-lookup"><span data-stu-id="4eea0-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="4eea0-142">Для гибридного развертывания администраторы Skype для бизнеса должны иметь возможность вызывать Get и Set для всех командлетов.</span><span class="sxs-lookup"><span data-stu-id="4eea0-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="4eea0-143">Для получения дополнительных сведений о полном списке ролей, ознакомьтесь со статьями [About Office 365 Admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="4eea0-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="4eea0-144">Автоматическое обнаружение сервера должно быть включено.</span><span class="sxs-lookup"><span data-stu-id="4eea0-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="4eea0-145">Для использования командлетов не будут использоваться дополнительные требования к лицензированию.</span><span class="sxs-lookup"><span data-stu-id="4eea0-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
