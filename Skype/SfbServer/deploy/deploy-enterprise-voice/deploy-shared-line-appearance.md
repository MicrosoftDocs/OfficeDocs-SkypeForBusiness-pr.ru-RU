---
title: Развертывание общего внешнего вида линии в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этом разделе рассказывается, как развернуть общий внешний вид линии (SLA) в Skype для бизнеса Server 2015 с накопительным пакетом обновления за Ноябрь 2015 г. SLA — это функция для обработки нескольких звонков по определенному номеру, который называется общим номером.
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604226"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="124fa-104">Развертывание общего внешнего вида линии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="124fa-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="124fa-105">В этом разделе рассказывается, как развернуть общий внешний вид линии (SLA) в Skype для бизнеса Server 2015 с накопительным пакетом обновления за Ноябрь 2015 г.</span><span class="sxs-lookup"><span data-stu-id="124fa-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="124fa-106">SLA — это функция для обработки нескольких звонков по определенному номеру, который называется общим номером.</span><span class="sxs-lookup"><span data-stu-id="124fa-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="124fa-107">Дополнительные сведения об этой функции можно найти [в статье Plan for Shared Line Appearance в Skype для бизнеса Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="124fa-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="124fa-108">Общий вид линии (SLA) — это новая функция в Skype для бизнеса Server, накопительный пакет обновления за Ноябрь 2015 ноября.</span><span class="sxs-lookup"><span data-stu-id="124fa-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="124fa-109">Чтобы включить эту функцию, сначала необходимо развернуть это накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="124fa-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="124fa-110">Установка внешнего вида общей линии</span><span class="sxs-lookup"><span data-stu-id="124fa-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="124fa-111">После установки накопительного пакета обновления для Skype для бизнеса Server с 2015 ноября выполните `SkypeServerUpdateInstaller.exe` обновление на каждом сервере переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="124fa-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="124fa-112">Установщик будет развертывать последнюю версию приложения SLA, но приложение по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="124fa-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="124fa-113">Он включен, выполнив действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="124fa-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="124fa-114">а.</span><span class="sxs-lookup"><span data-stu-id="124fa-114">a.</span></span> <span data-ttu-id="124fa-115">Зарегистрируйте SLA как серверное приложение, выполнив следующую команду для каждого пула:</span><span class="sxs-lookup"><span data-stu-id="124fa-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="124fa-116">где% FQDN% — полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="124fa-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="124fa-117">б.</span><span class="sxs-lookup"><span data-stu-id="124fa-117">b.</span></span> <span data-ttu-id="124fa-118">Выполните следующую команду, чтобы обновить роли RBAC для командлетов SLA:</span><span class="sxs-lookup"><span data-stu-id="124fa-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="124fa-119">в.</span><span class="sxs-lookup"><span data-stu-id="124fa-119">c.</span></span> <span data-ttu-id="124fa-120">Перезапустите все серверы переднего плана (служба RTCSRV) во всех пулах, где установлено и включено соглашение об уровне обслуживания:</span><span class="sxs-lookup"><span data-stu-id="124fa-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="124fa-121">Создание группы SLA и добавление в нее пользователей</span><span class="sxs-lookup"><span data-stu-id="124fa-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="124fa-122">Создайте группу SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="124fa-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="124fa-123">Командлет Set – CsSlaConfiguration помечает учетную запись корпоративного голоса SLAGroup1 как сущность SLA, а число SLAGroup1 становится номером для группы SLA.</span><span class="sxs-lookup"><span data-stu-id="124fa-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="124fa-124">Все звонки на SLAGroup1 будут звонить всей группе SLA.</span><span class="sxs-lookup"><span data-stu-id="124fa-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="124fa-125">В следующем примере создается группа SLA для существующего пользователя корпоративной голосовой связи, SLAGroup1, и используется номер, назначенный для SLAGroup1, в качестве номера магистрали SLA.</span><span class="sxs-lookup"><span data-stu-id="124fa-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="124fa-126">Команда устанавливает максимальное количество одновременных вызовов для новой группы SLA равным 3, а для звонков, передаваемых по сигналу занятости:</span><span class="sxs-lookup"><span data-stu-id="124fa-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="124fa-127">Set – CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.</span><span class="sxs-lookup"><span data-stu-id="124fa-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="124fa-128">Обратите внимание, что вы `-Identity` указали действительную учетную запись пользователя с включенной поддержкой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="124fa-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="124fa-129">Добавьте делегатов для группы с помощью командлета [Add – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="124fa-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="124fa-130">В примере ниже показано, как добавить пользователя в группу SLA.</span><span class="sxs-lookup"><span data-stu-id="124fa-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="124fa-131">Каждый пользователь, добавляемый в группу, должен быть действительным пользователем корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="124fa-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="124fa-132">Повторите командлет для каждого пользователя, которого вы хотите добавить в группу.</span><span class="sxs-lookup"><span data-stu-id="124fa-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="124fa-133">Пользователи могут принадлежать только одной группе SLA.</span><span class="sxs-lookup"><span data-stu-id="124fa-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="124fa-134">Настройка параметра "занято" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="124fa-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="124fa-135">Настройте параметр "занято" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="124fa-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="124fa-136">В следующем примере задаются вызовы, которые превышают максимальное число одновременных вызовов, перенаправляемых на номер телефона 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="124fa-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="124fa-137">Целевой объект может быть пользователем в вашей организации, а не номером телефона; в этом случае синтаксис для человека, получающего переадресованные звонки, совпадает с тем, что при указании делегата: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="124fa-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="124fa-138">Второй возможный параметр `BusyOption` `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="124fa-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="124fa-139">Настройка функции "Пропущенный вызов" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="124fa-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="124fa-140">Настройте параметр "Пропущенный вызов" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="124fa-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="124fa-141">В приведенном ниже примере указывается, что пропущенные звонки пересылаются пользователю с `sla_forward_number`именем.</span><span class="sxs-lookup"><span data-stu-id="124fa-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="124fa-142">`-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect`</span><span class="sxs-lookup"><span data-stu-id="124fa-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="124fa-143">`Forward`Если выбран этот `-MissedCallForwardTarget` параметр, необходимо также включить параметр с номером пользователя или телефона в качестве целевого значения:</span><span class="sxs-lookup"><span data-stu-id="124fa-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="124fa-144">Удаление делегата из группы</span><span class="sxs-lookup"><span data-stu-id="124fa-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="124fa-145">Удаление делегата из группы с помощью командлета [Remove – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="124fa-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="124fa-146">Пример.</span><span class="sxs-lookup"><span data-stu-id="124fa-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="124fa-147">Удаление группы SLA</span><span class="sxs-lookup"><span data-stu-id="124fa-147">Delete an SLA group</span></span>

- <span data-ttu-id="124fa-148">Удалить группу SLA можно с помощью командлета [Remove – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="124fa-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="124fa-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="124fa-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


