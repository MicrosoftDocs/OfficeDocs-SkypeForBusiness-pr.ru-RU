---
title: Использование Teams со службами удаленных рабочих стола
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как использовать Microsoft Teams со службами удаленных рабочих стола.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119098"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="b01ec-103">Teams в службах удаленных рабочих стола</span><span class="sxs-lookup"><span data-stu-id="b01ec-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="b01ec-104">В этой статье описаны требования и ограничения для использования Microsoft Teams в среде служб удаленных рабочих стола .</span><span class="sxs-lookup"><span data-stu-id="b01ec-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="b01ec-105">Что такое RDS?</span><span class="sxs-lookup"><span data-stu-id="b01ec-105">What is RDS?</span></span>

<span data-ttu-id="b01ec-106">Службы удаленных рабочих стола (RDS) — это платформа для создания решений виртуализации для каждой потребности конечного клиента.</span><span class="sxs-lookup"><span data-stu-id="b01ec-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="b01ec-107">С помощью RDS вы можете создавать отдельные виртуализированные приложения, предоставлять безопасный мобильный и удаленный доступ к рабочему столу, а также предоставлять конечным пользователям возможность запускать свои приложения и рабочие столы из облака.</span><span class="sxs-lookup"><span data-stu-id="b01ec-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="b01ec-108">RDS обеспечивает гибкость развертывания, эффективность и разность.</span><span class="sxs-lookup"><span data-stu-id="b01ec-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="b01ec-109">RDS можно развертывать различными средствами, включая Windows Server 2016 для локального развертывания, Microsoft Azure облачных развертывании и надежный набор партнерских решений.</span><span class="sxs-lookup"><span data-stu-id="b01ec-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="b01ec-110">В зависимости от среды и настроек вы можете настроить решение RDS для виртуализации на основе сеансов как инфраструктуру виртуального рабочего стола (VDI).</span><span class="sxs-lookup"><span data-stu-id="b01ec-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="b01ec-111">В настоящее время Teams в среде служб удаленного рабочего стола доступны средства для совместной работы и чата.</span><span class="sxs-lookup"><span data-stu-id="b01ec-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="b01ec-112">Чтобы обеспечить оптимальный пользовательский интерфейс, следуйте указаниям в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b01ec-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-rds-with-chat-and-collaboration"></a><span data-ttu-id="b01ec-113">Teams RDS с чатом и совместной работой</span><span class="sxs-lookup"><span data-stu-id="b01ec-113">Teams on RDS with chat and collaboration</span></span>

<span data-ttu-id="b01ec-114">Если ваша организация хочет использовать функции чата и совместной работы только в Teams, вы можете настроить политики на уровне пользователя, чтобы отключить функции звонков и собраний в Teams.</span><span class="sxs-lookup"><span data-stu-id="b01ec-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="b01ec-115">Настройка политик для отключения функций звонков и собраний</span><span class="sxs-lookup"><span data-stu-id="b01ec-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="b01ec-116">Вы можете настроить политики с помощью Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b01ec-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="b01ec-117">Распространение изменений политики может занять некоторое время (несколько часов).</span><span class="sxs-lookup"><span data-stu-id="b01ec-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b01ec-118">Если вы не видите изменений для учетной записи сразу, попробуйте еще раз через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b01ec-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="b01ec-119">[**Политики звонков:**](teams-calling-policy.md)Teams включает встроенную политику звонков DisallowCalling, в которой отключены все функции звонков.</span><span class="sxs-lookup"><span data-stu-id="b01ec-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="b01ec-120">Назначьте политику DisallowCalling всем пользователям в организации, Teams виртуализированной среде.</span><span class="sxs-lookup"><span data-stu-id="b01ec-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="b01ec-121">[**Политики собраний:**](meeting-policies-in-teams.md)Teams включает встроенную политику собраний AllOff, в которой все функции собраний отключены.</span><span class="sxs-lookup"><span data-stu-id="b01ec-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="b01ec-122">Назначьте политику AllOff всем пользователям в организации, Teams виртуализированной среде.</span><span class="sxs-lookup"><span data-stu-id="b01ec-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b01ec-123">Назначение политик с помощью центра Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="b01ec-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b01ec-124">Чтобы назначить пользователю политику звонков DisallowCalling и политику собраний AllOff:</span><span class="sxs-lookup"><span data-stu-id="b01ec-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="b01ec-125">В левой области навигации центра администрирования Microsoft Teams перейдите в меню **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b01ec-126">Выберите пользователя, выбрав слева от его имени и выбрав изменить **параметры**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="b01ec-127">Сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b01ec-127">Do the following steps:</span></span>

    <span data-ttu-id="b01ec-128">а)</span><span class="sxs-lookup"><span data-stu-id="b01ec-128">a.</span></span>  <span data-ttu-id="b01ec-129">В **области Политика звонков** выберите **DisallowCalling**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="b01ec-130">б)</span><span class="sxs-lookup"><span data-stu-id="b01ec-130">b.</span></span>  <span data-ttu-id="b01ec-131">В **области Политика собраний** выберите **AllOff**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="b01ec-132">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-132">Select **Apply**.</span></span>

<span data-ttu-id="b01ec-133">Чтобы назначить политику нескольким пользователям одновременно:</span><span class="sxs-lookup"><span data-stu-id="b01ec-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b01ec-134">В левой области навигации Центра администрирования Microsoft Teams выберите **Пользователи** и найдите пользователей или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b01ec-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b01ec-135">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="b01ec-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b01ec-136">Чтобы выбрать всех пользователей, &#x2713; (check mark) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="b01ec-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b01ec-137">Выберите **Изменить параметры**, внесите нужные изменения и выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="b01ec-138">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="b01ec-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="b01ec-139">В левой области навигации центра администрирования Microsoft Teams перейдите к нужной политике.</span><span class="sxs-lookup"><span data-stu-id="b01ec-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b01ec-140">Например:</span><span class="sxs-lookup"><span data-stu-id="b01ec-140">For example:</span></span>

    - <span data-ttu-id="b01ec-141">Перейдите к  >  **политикам голосовых** звонков и выберите **DisallowCalling**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="b01ec-142">Перейдите **к политике**  >  **собраний собраний** и выберите **AllOff**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="b01ec-143">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="b01ec-144">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b01ec-145">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="b01ec-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b01ec-146">Завершив добавление пользователей, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b01ec-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b01ec-147">Назначение политик с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b01ec-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="b01ec-148">В следующем примере показано, как использовать [grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) для назначения пользователю политики вызовов DisallowCalling.</span><span class="sxs-lookup"><span data-stu-id="b01ec-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="b01ec-149">Дополнительные информацию об управлении политиками звонков с помощью PowerShell см. в теме [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b01ec-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b01ec-150">В следующем примере показано, как использовать [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) для назначения пользователю политики собраний AllOff.</span><span class="sxs-lookup"><span data-stu-id="b01ec-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="b01ec-151">Дополнительные информацию об управлении политиками собраний с помощью PowerShell см. в теме [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b01ec-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>