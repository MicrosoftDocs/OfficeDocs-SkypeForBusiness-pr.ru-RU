---
title: Развертывание общих строк в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Ознакомьтесь с этой темой, чтобы узнать о развертывании общего внешнего вида (SLA) в Skype для бизнеса Server 2015, ноябрь 2015 г. Накопительное обновление. SLA — это функция для обработки нескольких вызовов на определенном номере, называемом общим номером.
ms.openlocfilehash: 7758354b7c4be123cb9b5a482af3304b069931a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104915"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="2e5f9-104">Развертывание общих строк в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e5f9-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="2e5f9-105">Ознакомьтесь с этой темой, чтобы узнать о развертывании общего внешнего вида (SLA) в Skype для бизнеса Server 2015, ноябрь 2015 г. Накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="2e5f9-106">SLA — это функция для обработки нескольких вызовов на определенном номере, называемом общим номером.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="2e5f9-107">Дополнительные сведения об этой функции см. в раздел [Plan for Shared Line Appearance in Skype for Business Server 2015.](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="2e5f9-108">Общий внешний вид строки (SLA) — это новая функция в Skype для бизнеса Server, накопительное обновление за ноябрь 2015 г.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="2e5f9-109">Чтобы включить эту функцию, необходимо сначала развернуть это накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="2e5f9-110">Установка общего внешнего вида строки</span><span class="sxs-lookup"><span data-stu-id="2e5f9-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="2e5f9-111">После развертывания Skype для бизнеса Server в ноябре 2015 г. будет развернуто накопительное обновление, запустите исправление на каждом переднем сервере в  `SkypeServerUpdateInstaller.exe` пуле.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="2e5f9-112">Установщик развернет последнюю версию приложения SLA, однако по умолчанию приложение не включено.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="2e5f9-113">Она включена, следуя описанным ниже шагам:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="2e5f9-114">а)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-114">a.</span></span> <span data-ttu-id="2e5f9-115">Зарегистрируйте SLA в качестве серверного приложения, задав следующую команду для каждого пула:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="2e5f9-116">где %FQDN% — это полностью квалифицированное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="2e5f9-117">б)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-117">b.</span></span> <span data-ttu-id="2e5f9-118">Запустите следующую команду, чтобы обновить роли RBAC для командлетов SLA:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="2e5f9-119">в.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-119">c.</span></span> <span data-ttu-id="2e5f9-120">Перезапустите все серверы переднего конца (служба RTCSRV) во всех пулах, где была установлена и включена SLA:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="2e5f9-121">Создание группы SLA и добавление пользователей в нее</span><span class="sxs-lookup"><span data-stu-id="2e5f9-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="2e5f9-122">Создайте группу SLA с помощью [комлета Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-122">Create the SLA group by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="2e5f9-123">В Set-CsSlaConfiguration кодлета Корпоративная голосовая связь SLAGroup1 в качестве объекта SLA, а число SLAGroup1 становится номером для группы SLA.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="2e5f9-124">Все вызовы в SLAGroup1 обзывают всю группу SLA.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="2e5f9-125">В следующем примере создается группа SLA для существующего Корпоративная голосовая связь, SLAGroup1, и в качестве основного номера SLAGroup1 используется номер SLAGroup1.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="2e5f9-126">Команда задает максимальное количество одновременного вызова для новой группы SLA до 3, а для вызовов, превышает это, чтобы услышать сигнал загруженного:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="2e5f9-127">Вы можете Set-CsSlaConfiguration создать новую группу SLA или изменить существующую.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e5f9-128">Обратите внимание, что указанная вами учетная запись должна быть действительной Корпоративная голосовая связь  `-Identity` учетной записью пользователя с включенной поддержкой.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="2e5f9-129">Добавление делегатов в группу с помощью [cmdlet Add-CsSlaDelegates:](/powershell/module/skype/add-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-129">Add delegates to the group by using the [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="2e5f9-130">В следующем примере пользователь добавляется в группу SLA.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="2e5f9-131">Каждый пользователь, добавленный в группу, должен быть действительным Корпоративная голосовая связь с включенной поддержкой:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="2e5f9-132">Повторите cmdlet для каждого пользователя, который необходимо добавить в группу.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="2e5f9-133">Пользователи могут принадлежать только к одной группе SLA.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="2e5f9-134">Настройка параметра занятости группы SLA</span><span class="sxs-lookup"><span data-stu-id="2e5f9-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="2e5f9-135">Настройка параметра занятости группы SLA с помощью группы [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="2e5f9-136">В следующем примере задаются вызовы, которые превышают максимальное количество одновременно переадверяемых вызовов на телефонный номер 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="2e5f9-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="2e5f9-137">Целью может быть пользователь в организации, а не номер телефона; в этом случае синтаксис для лица, получаюющего переададные вызовы, такой же, как при указании делегата:  `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="2e5f9-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="2e5f9-138">Другой возможный `BusyOption` параметр: `Voicemail`</span><span class="sxs-lookup"><span data-stu-id="2e5f9-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="2e5f9-139">Настройка параметра пропущенных вызовов группы SLA</span><span class="sxs-lookup"><span data-stu-id="2e5f9-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="2e5f9-140">Настройка параметра пропущенных вызовов группы SLA с помощью комлета [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="2e5f9-141">В следующем примере указывается, что пропущенные вызовы должны быть переад. `sla_forward_number`</span><span class="sxs-lookup"><span data-stu-id="2e5f9-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="2e5f9-142">Допустимые  `-MissedCallOption` параметры `Forward` :  `BusySignal` , или  `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="2e5f9-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="2e5f9-143">Если вы  `Forward` решите, необходимо также включить параметр, с пользователем или номером телефона  `-MissedCallForwardTarget` в качестве цели:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="2e5f9-144">Удаление делегата из группы</span><span class="sxs-lookup"><span data-stu-id="2e5f9-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="2e5f9-145">Удаление делегата из группы с помощью группы [Remove-CsSlaDelegates:](/powershell/module/skype/remove-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="2e5f9-146">Например:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="2e5f9-147">Удаление группы SLA</span><span class="sxs-lookup"><span data-stu-id="2e5f9-147">Delete an SLA group</span></span>

- <span data-ttu-id="2e5f9-148">Удалите группу SLA с помощью [комлета Remove-CsSlaConfiguration:](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2e5f9-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="2e5f9-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="2e5f9-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```