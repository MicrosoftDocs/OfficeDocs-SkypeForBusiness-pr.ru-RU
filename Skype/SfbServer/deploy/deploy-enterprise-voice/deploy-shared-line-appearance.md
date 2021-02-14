---
title: Развертывание общей линии в Skype для бизнеса Server 2015
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
description: В этом разделе вы узнаете, как развернуть SLA в накопительном обновлении Skype для бизнеса Server 2015 за ноябрь 2015 г. SLA — это функция для обработки нескольких вызовов на определенный номер, называемый общим номером.
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812409"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="e1f85-104">Развертывание общей линии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e1f85-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="e1f85-105">В этом разделе вы узнаете, как развернуть SLA в накопительном обновлении Skype для бизнеса Server 2015 за ноябрь 2015 г.</span><span class="sxs-lookup"><span data-stu-id="e1f85-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="e1f85-106">SLA — это функция для обработки нескольких вызовов на определенный номер, называемый общим номером.</span><span class="sxs-lookup"><span data-stu-id="e1f85-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="e1f85-107">Дополнительные сведения об этой функции см. в подстройки [Plan for Shared Line Appearance in Skype for Business Server 2015.](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)</span><span class="sxs-lookup"><span data-stu-id="e1f85-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="e1f85-108">Shared Line Appearance (SLA) — это новая функция в Накопительном обновлении Skype для бизнеса Server за ноябрь 2015 г.</span><span class="sxs-lookup"><span data-stu-id="e1f85-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="e1f85-109">Чтобы включить эту функцию, необходимо сначала развернуть это накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="e1f85-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="e1f85-110">Установка внешнего вида общей линии</span><span class="sxs-lookup"><span data-stu-id="e1f85-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="e1f85-111">После развертывания накопительного обновления Skype для бизнеса Server за ноябрь 2015 г. запустите исправление на каждом сервере переднего сервера  `SkypeServerUpdateInstaller.exe` в пуле.</span><span class="sxs-lookup"><span data-stu-id="e1f85-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="e1f85-112">Установщик развернет последнюю версию приложения SLA, однако по умолчанию приложение не включено.</span><span class="sxs-lookup"><span data-stu-id="e1f85-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="e1f85-113">Она включена с помощью описанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e1f85-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="e1f85-114">а.</span><span class="sxs-lookup"><span data-stu-id="e1f85-114">a.</span></span> <span data-ttu-id="e1f85-115">Зарегистрируйте SLA в качестве серверного приложения, выдав следующую команду для каждого пула:</span><span class="sxs-lookup"><span data-stu-id="e1f85-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="e1f85-116">где %FQDN% — это полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="e1f85-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="e1f85-117">б.</span><span class="sxs-lookup"><span data-stu-id="e1f85-117">b.</span></span> <span data-ttu-id="e1f85-118">Чтобы обновить роли RBAC для командлетов SLA, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e1f85-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="e1f85-119">в.</span><span class="sxs-lookup"><span data-stu-id="e1f85-119">c.</span></span> <span data-ttu-id="e1f85-120">Перезапустите все серверы переднего сервера (служба RTCSRV) во всех пулах, где было установлено и включено SLA:</span><span class="sxs-lookup"><span data-stu-id="e1f85-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="e1f85-121">Создание группы SLA и добавление в нее пользователей</span><span class="sxs-lookup"><span data-stu-id="e1f85-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="e1f85-122">Создайте группу SLA с помощью [cmdlet Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e1f85-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="e1f85-123">Этот Set-CsSlaConfiguration пометит учетную запись Корпоративная голосовая связь SLAGroup1 как сущность SLA, а число SLAGroup1 станет номером для группы SLA.</span><span class="sxs-lookup"><span data-stu-id="e1f85-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="e1f85-124">Все вызовы SLAGroup1 будут звонить всей группе SLA.</span><span class="sxs-lookup"><span data-stu-id="e1f85-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="e1f85-125">В следующем примере создается группа SLA для существующего пользователя Корпоративная голосовая связь SLAGroup1 и используется номер, присвоенный SLAGroup1 в качестве номера основной линии SLA.</span><span class="sxs-lookup"><span data-stu-id="e1f85-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="e1f85-126">Эта команда задает максимальное число одновременно звонков для новой группы SLA как 3, так и для вызовов, превышает которые, чтобы прослушать сигнал "занято":</span><span class="sxs-lookup"><span data-stu-id="e1f85-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="e1f85-127">С помощью Set-CsSlaConfiguration можно создать новую группу SLA или изменить существующую.</span><span class="sxs-lookup"><span data-stu-id="e1f85-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1f85-128">Обратите внимание, что указанная учетная запись должна быть действительной  `-Identity` Корпоративная голосовая связь с включенной поддержкой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1f85-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="e1f85-129">Добавьте делегатов в группу с помощью [cmdlet Add-CsSlaDelegates:](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e1f85-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="e1f85-130">В следующем примере пользователь добавляется в группу SLA.</span><span class="sxs-lookup"><span data-stu-id="e1f85-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="e1f85-131">Каждый пользователь, добавленный в группу, должен быть действительным Корпоративная голосовая связь с включенной поддержкой:</span><span class="sxs-lookup"><span data-stu-id="e1f85-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="e1f85-132">Повторите этот действия для каждого пользователя, который требуется добавить в группу.</span><span class="sxs-lookup"><span data-stu-id="e1f85-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="e1f85-133">Пользователи могут принадлежать только одной группе SLA.</span><span class="sxs-lookup"><span data-stu-id="e1f85-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="e1f85-134">Настройка параметра занятости группы SLA</span><span class="sxs-lookup"><span data-stu-id="e1f85-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="e1f85-135">Настройте параметр занятости группы SLA с помощью [cmdlet Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e1f85-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="e1f85-136">В следующем примере задаются вызовы, превышающего максимальное количество одновременно переадреаментных вызовов на телефонный номер 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="e1f85-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="e1f85-137">Целью может быть пользователь в организации, а не номер телефона; в этом случае синтаксис для лица, который будет принимать переад вперед вызовы, такой же, как при указании делегата:  `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="e1f85-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="e1f85-138">Другой возможный `BusyOption` параметр: `Voicemail`</span><span class="sxs-lookup"><span data-stu-id="e1f85-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="e1f85-139">Настройка параметра "Пропущенный звонок" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="e1f85-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="e1f85-140">Настройте параметр "Пропущенный звонок" для группы SLA с помощью [cmdlet Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e1f85-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="e1f85-141">В следующем примере указывается, что пропущенные вызовы необходимо переадлить пользователю с именем  `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="e1f85-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="e1f85-142">Допустимые  `-MissedCallOption` параметры: `Forward`  `BusySignal` , , или  `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="e1f85-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="e1f85-143">При выборе этого параметра необходимо также включить параметр с пользователем или номером телефона  `Forward`  `-MissedCallForwardTarget` в качестве целевого параметра:</span><span class="sxs-lookup"><span data-stu-id="e1f85-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="e1f85-144">Удаление делегата из группы</span><span class="sxs-lookup"><span data-stu-id="e1f85-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="e1f85-145">Удалите делегата из группы с помощью [cmdlet Remove-CsSlaDelegates:](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e1f85-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="e1f85-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1f85-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="e1f85-147">Удаление группы SLA</span><span class="sxs-lookup"><span data-stu-id="e1f85-147">Delete an SLA group</span></span>

- <span data-ttu-id="e1f85-148">Удалите группу SLA с помощью [cmdlet Remove-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e1f85-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="e1f85-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1f85-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


