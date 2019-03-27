---
title: Развертывание распределенной линии для Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: В этом разделе описывается развертывание Shared Line Appearance (SLA) в накопительном пакете обновления Skype для бизнеса Server 2015 от ноября 2015 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.
ms.openlocfilehash: c0da29e54f03a5c328f1b65807f438b63c14a68f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878650"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="8ce24-104">Развертывание распределенной линии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ce24-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="8ce24-p102">В этом разделе описывается развертывание Shared Line Appearance (SLA) в накопительном пакете обновления Skype для бизнеса Server 2015 от ноября 2015 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.</span><span class="sxs-lookup"><span data-stu-id="8ce24-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="8ce24-107">Дополнительные сведения об этой функции см. в разделе [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="8ce24-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="8ce24-108">Внешний вид общей строки (SLA) — это новая возможность в Скайп для Business Server 2015 ноября накопительного обновления.</span><span class="sxs-lookup"><span data-stu-id="8ce24-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="8ce24-109">Для включения этой функции сначала требуется развернуть это обновление.</span><span class="sxs-lookup"><span data-stu-id="8ce24-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="8ce24-110">Установка Shared Line Appearance</span><span class="sxs-lookup"><span data-stu-id="8ce24-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="8ce24-111">После Скайп для Business Server 2015 ноября развертывается накопительное обновление, запустите `SkypeServerUpdateInstaller.exe` исправлений на каждом сервере переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="8ce24-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="8ce24-p104">Программа установки разворачивает последнюю версию приложения SLA, однако приложение не включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8ce24-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="8ce24-114">а.</span><span class="sxs-lookup"><span data-stu-id="8ce24-114">a.</span></span> <span data-ttu-id="8ce24-115">Зарегистрировать SLA в качестве серверного приложения, запустив следующую команду для каждого пула:</span><span class="sxs-lookup"><span data-stu-id="8ce24-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="8ce24-116">где %FQDN% — полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="8ce24-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="8ce24-117">б.</span><span class="sxs-lookup"><span data-stu-id="8ce24-117">b.</span></span> <span data-ttu-id="8ce24-118">Запустить следующую команду для обновления ролей RBAC для командлетов SLA:</span><span class="sxs-lookup"><span data-stu-id="8ce24-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```
   Update-CsAdminRole
   ```

    <span data-ttu-id="8ce24-119">в.</span><span class="sxs-lookup"><span data-stu-id="8ce24-119">c.</span></span> <span data-ttu-id="8ce24-120">Перезагрузить все серверы переднего плана (служба RTCSRV) во всех пулах, в которых установлено и включено приложение SLA:</span><span class="sxs-lookup"><span data-stu-id="8ce24-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="8ce24-121">Создать группу SLA и добавить в нее пользователей</span><span class="sxs-lookup"><span data-stu-id="8ce24-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="8ce24-122">Создать группу SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="8ce24-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="8ce24-p108">Командлет Set-CsSlaConfiguration отмечает SLAGroup1 учетной записи корпоративной голосовой связи в качестве объекта SLA, а номер SLAGroup1 становится номером группы SLA. Все вызовы в SLAGroup1 будут направлены всей группе SLA.</span><span class="sxs-lookup"><span data-stu-id="8ce24-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="8ce24-125">В следующем примере группа SLA создается для существующего пользователя корпоративной голосовой связи, SLAGroup1. Номер, назначенный для SLAGroup1, используется в качестве магистрального номера SLA.</span><span class="sxs-lookup"><span data-stu-id="8ce24-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="8ce24-126">Команда устанавливает максимальное количество одновременных звонков для новой группы SLA: 3. Четвертый и последующие вызовы будут получать сигнал "занято".</span><span class="sxs-lookup"><span data-stu-id="8ce24-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="8ce24-127">Set-CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.</span><span class="sxs-lookup"><span data-stu-id="8ce24-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8ce24-128">Обратите внимание на то, что указанное для `-Identity` должен быть допустимый существующей учетной записи пользователя с включенной поддержкой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8ce24-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="8ce24-129">Добавление делегатов в группы выполняется с помощью командлета [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="8ce24-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="8ce24-130">The following example adds a user to the SLA group.</span><span class="sxs-lookup"><span data-stu-id="8ce24-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="8ce24-131">Каждый пользователь добавлен в группу по должен быть допустимый пользователя с включенной поддержкой корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="8ce24-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="8ce24-p110">Повторите командлет для каждого пользователя, которого необходимо добавить в группу. Пользователи могут принадлежать только одной группе SLA.</span><span class="sxs-lookup"><span data-stu-id="8ce24-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="8ce24-134">Настройка опции "Занято" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="8ce24-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="8ce24-135">Настроить опцию "Занято" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="8ce24-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="8ce24-136">В следующем примере настраивается переадресация вызовов, превышающих максимальное количество одновременных вызовов, на телефонный номер 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="8ce24-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="8ce24-137">Целевой объект может быть пользователей в вашей организации, а не номер телефона; в этом случае используется следующий синтаксис для пользователя принимать звонки, перенаправленные то же, что при указании делегата: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="8ce24-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="8ce24-138">Возможные параметра для `BusyOption` — это `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="8ce24-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="8ce24-139">Настройка опции "Пропущенный вызов" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="8ce24-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="8ce24-140">Настроить опцию "Пропущенный вызов" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="8ce24-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="8ce24-141">В следующем примере указывается, что пропущенных звонков должны перенаправляться пользователю с именем `sla_forward_number`.</span><span class="sxs-lookup"><span data-stu-id="8ce24-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="8ce24-142">Допустимые параметры для `-MissedCallOption` , параметр `Forward`, `BusySignal`, или `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="8ce24-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="8ce24-143">Если выбрано `Forward`, необходимо также включить `-MissedCallForwardTarget` параметр с пользователя или на телефонный номер целевым:</span><span class="sxs-lookup"><span data-stu-id="8ce24-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="8ce24-144">Удаление делегата из группы</span><span class="sxs-lookup"><span data-stu-id="8ce24-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="8ce24-145">Удалить делегата из группы можно с помощью командлета [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="8ce24-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="8ce24-146">Например:</span><span class="sxs-lookup"><span data-stu-id="8ce24-146">For example:</span></span>

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="8ce24-147">Удаление группы SLA</span><span class="sxs-lookup"><span data-stu-id="8ce24-147">Delete an SLA group</span></span>

- <span data-ttu-id="8ce24-148">Удалить группу SLA можно с помощью командлета [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8ce24-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="8ce24-149">Например:</span><span class="sxs-lookup"><span data-stu-id="8ce24-149">For example:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


