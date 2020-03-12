---
title: 'Lync Server 2013: развертывание общей линии внешнего вида'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80c58b532c36e74aecd4d7ecb758afee1e2c2bdd
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="8d574-102">Развертывание общего внешнего вида линии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d574-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d574-103">_**Последнее изменение темы:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="8d574-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="8d574-104">В этом разделе рассказывается, как развернуть общий вид линии (SLA) в Lync Server 2013, накопительный пакет обновления от 2016 апреля.</span><span class="sxs-lookup"><span data-stu-id="8d574-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="8d574-105">SLA — это функция для обработки нескольких звонков по определенному номеру, который называется общим номером.</span><span class="sxs-lookup"><span data-stu-id="8d574-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="8d574-106">Дополнительные сведения об этой функции можно найти [в статье Plan for Shared Line Appearance в Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="8d574-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="8d574-107">Общий вид линии (SLA) — это новая функция в Lync Server 2013, накопительный пакет обновления от 2016 апреля.</span><span class="sxs-lookup"><span data-stu-id="8d574-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="8d574-108">Чтобы включить эту функцию, сначала необходимо развернуть это накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="8d574-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="8d574-109">Установка внешнего вида общей линии</span><span class="sxs-lookup"><span data-stu-id="8d574-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="8d574-110">После развертывания Lync Server 2013 обновление до 2016 апреля не включается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d574-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="8d574-111">Чтобы включить приложение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8d574-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="8d574-112">Зарегистрируйте SLA как серверное приложение, выполнив следующую команду для каждого пула:</span><span class="sxs-lookup"><span data-stu-id="8d574-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="8d574-113">где% FQDN% — полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="8d574-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="8d574-114">Выполните следующую команду, чтобы обновить роли RBAC для командлетов SLA:</span><span class="sxs-lookup"><span data-stu-id="8d574-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="8d574-115">Перезапустите все серверы переднего плана (служба RTCSRV) во всех пулах, где установлено и включено соглашение об уровне обслуживания:</span><span class="sxs-lookup"><span data-stu-id="8d574-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="8d574-116">Создание группы SLA и добавление в нее пользователей</span><span class="sxs-lookup"><span data-stu-id="8d574-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="8d574-117">Создайте группу SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="8d574-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="8d574-118">Командлет Set – CsSlaConfiguration помечает учетную запись корпоративного голоса SLAGroup1 как сущность SLA, а число SLAGroup1 становится номером для группы SLA.</span><span class="sxs-lookup"><span data-stu-id="8d574-118">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="8d574-119">Все звонки на SLAGroup1 будут звонить всей группе SLA.</span><span class="sxs-lookup"><span data-stu-id="8d574-119">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="8d574-120">В следующем примере создается группа SLA для существующего пользователя корпоративной голосовой связи, SLAGroup1, и используется номер, назначенный для SLAGroup1, в качестве номера магистрали SLA.</span><span class="sxs-lookup"><span data-stu-id="8d574-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="8d574-121">Команда устанавливает максимальное количество одновременных вызовов для новой группы SLA равным 3, а для звонков, передаваемых по сигналу занятости:</span><span class="sxs-lookup"><span data-stu-id="8d574-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="8d574-122">Set – CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.</span><span class="sxs-lookup"><span data-stu-id="8d574-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d574-123">Обратите внимание, что вы <CODE>-Identity</CODE> указали действительную учетную запись пользователя с включенной поддержкой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8d574-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="8d574-124">Добавьте делегатов для группы с помощью командлета [Add – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="8d574-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="8d574-125">В примере ниже показано, как добавить пользователя в группу SLA.</span><span class="sxs-lookup"><span data-stu-id="8d574-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="8d574-126">Каждый пользователь, добавляемый в группу, должен быть действительным пользователем корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="8d574-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="8d574-127">Повторите командлет для каждого пользователя, которого вы хотите добавить в группу.</span><span class="sxs-lookup"><span data-stu-id="8d574-127">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="8d574-128">Пользователи могут принадлежать только одной группе SLA.</span><span class="sxs-lookup"><span data-stu-id="8d574-128">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="8d574-129">Настройка параметра "занято" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="8d574-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="8d574-130">Настройте параметр "занято" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="8d574-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="8d574-131">В следующем примере задаются вызовы, которые превышают максимальное число одновременных вызовов, перенаправляемых на номер телефона 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="8d574-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="8d574-132">Целевой объект может быть пользователем в вашей организации, а не номером телефона; в этом случае синтаксис для человека, получающего переадресованные звонки, совпадает с тем, что при указании делегата: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="8d574-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="8d574-133">Второй возможный параметр `BusyOption` `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="8d574-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="8d574-134">Настройка функции "Пропущенный вызов" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="8d574-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="8d574-135">Настройте параметр "Пропущенный вызов" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="8d574-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="8d574-136">В приведенном ниже примере указывается, что пропущенные звонки пересылаются пользователю с `sla_forward_number`именем.</span><span class="sxs-lookup"><span data-stu-id="8d574-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="8d574-137">`-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect`</span><span class="sxs-lookup"><span data-stu-id="8d574-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="8d574-138">`Forward`Если выбран этот `-MissedCallForwardTarget` параметр, необходимо также включить параметр с номером пользователя или телефона в качестве целевого значения:</span><span class="sxs-lookup"><span data-stu-id="8d574-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="8d574-139">Удаление делегата из группы</span><span class="sxs-lookup"><span data-stu-id="8d574-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="8d574-140">Удаление делегата из группы с помощью командлета [Remove – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="8d574-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="8d574-141">Пример.</span><span class="sxs-lookup"><span data-stu-id="8d574-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="8d574-142">Удаление группы SLA</span><span class="sxs-lookup"><span data-stu-id="8d574-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="8d574-143">Удалить группу SLA можно с помощью командлета [Remove – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="8d574-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="8d574-144">Пример:</span><span class="sxs-lookup"><span data-stu-id="8d574-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

