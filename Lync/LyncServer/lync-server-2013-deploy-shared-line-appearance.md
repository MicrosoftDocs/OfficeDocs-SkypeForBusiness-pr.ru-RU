---
title: 'Lync Server 2013: развертывание представления общей линии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6893dbda1c8f9ecf61319d19a24b896ff67de20b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="e9adc-102">Развертывание представления общей линии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9adc-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9adc-103">_**Тема последнего изменения:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="e9adc-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="e9adc-104">В этой статье рассказывается о том, как развернуть общий вид линии (SLA) в Lync Server 2013, Накопительное обновление от апреля 2016 г.</span><span class="sxs-lookup"><span data-stu-id="e9adc-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="e9adc-105">SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.</span><span class="sxs-lookup"><span data-stu-id="e9adc-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="e9adc-106">Подробнее об этой функции можно найти в разделе [планирование отображения общей линии в Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="e9adc-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="e9adc-107">Общий вид линии (SLA) — это новая функция в Lync Server 2013, Накопительное обновление от 2016 апреля.</span><span class="sxs-lookup"><span data-stu-id="e9adc-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="e9adc-108">Для включения этой функции сначала требуется развернуть это обновление.</span><span class="sxs-lookup"><span data-stu-id="e9adc-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="e9adc-109">Установка Shared Line Appearance</span><span class="sxs-lookup"><span data-stu-id="e9adc-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="e9adc-110">После того как Lync Server 2013, Накопительное обновление от апреля 2016 развернуто, приложение SLA по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="e9adc-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="e9adc-111">Чтобы включить приложение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e9adc-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="e9adc-112">Зарегистрировать SLA в качестве серверного приложения, запустив следующую команду для каждого пула:</span><span class="sxs-lookup"><span data-stu-id="e9adc-112">Register SLA as a server application by running the following command for each pool:</span></span>
        
            New-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                            http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                            $true -Priority (Get-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/UserServices').Priority 
        
        <span data-ttu-id="e9adc-113">где %FQDN% — полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="e9adc-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="e9adc-114">Запустить следующую команду для обновления ролей RBAC для командлетов SLA:</span><span class="sxs-lookup"><span data-stu-id="e9adc-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        
            Update-CsAdminRole 
    
    3.  <span data-ttu-id="e9adc-115">Перезагрузить все серверы переднего плана (служба RTCSRV) во всех пулах, в которых установлено и включено приложение SLA:</span><span class="sxs-lookup"><span data-stu-id="e9adc-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ``` 
         Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="e9adc-116">Создать группу SLA и добавить в нее пользователей</span><span class="sxs-lookup"><span data-stu-id="e9adc-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="e9adc-117">Создать группу SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="e9adc-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -MaxNumberOfCalls <Number> -BusyOption
                  <BusyOnBusy|Voicemail|Forward> [-Target
                  <TargetUserOrPhoneNumber>]
    
    <span data-ttu-id="e9adc-p104">Командлет Set-CsSlaConfiguration отмечает SLAGroup1 учетной записи корпоративной голосовой связи в качестве объекта SLA, а номер SLAGroup1 становится номером группы SLA. Все вызовы в SLAGroup1 будут направлены всей группе SLA.</span><span class="sxs-lookup"><span data-stu-id="e9adc-p104">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="e9adc-120">В следующем примере группа SLA создается для существующего пользователя корпоративной голосовой связи, SLAGroup1. Номер, назначенный для SLAGroup1, используется в качестве магистрального номера SLA.</span><span class="sxs-lookup"><span data-stu-id="e9adc-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="e9adc-121">Команда устанавливает максимальное количество одновременных звонков для новой группы SLA: 3. Четвертый и последующие вызовы будут получать сигнал "занято".</span><span class="sxs-lookup"><span data-stu-id="e9adc-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                  -BusyOption BusyOnBusy
    
    <span data-ttu-id="e9adc-122">Set-CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.</span><span class="sxs-lookup"><span data-stu-id="e9adc-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9adc-123">Обратите внимание, что заданное вами значение <CODE>-Identity</CODE> должно быть действительной существующей учетной записью пользователя, поддерживающего голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="e9adc-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="e9adc-124">Добавление делегатов в группы выполняется с помощью командлета [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates):</span><span class="sxs-lookup"><span data-stu-id="e9adc-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    
        Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    <span data-ttu-id="e9adc-125">The following example adds a user to the SLA group.</span><span class="sxs-lookup"><span data-stu-id="e9adc-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="e9adc-126">Каждый пользователь, добавленный в группу, должен быть допустимым корпоративным пользователям с поддержкой голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="e9adc-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    
        Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate1@contoso.com
    
    <span data-ttu-id="e9adc-p106">Повторите командлет для каждого пользователя, которого необходимо добавить в группу. Пользователи могут принадлежать только одной группе SLA.</span><span class="sxs-lookup"><span data-stu-id="e9adc-p106">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="e9adc-129">Настройка опции "Занято" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="e9adc-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="e9adc-130">Настроить опцию "Занято" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="e9adc-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    
    <span data-ttu-id="e9adc-131">В следующем примере настраивается переадресация вызовов, превышающих максимальное количество одновременных вызовов, на телефонный номер 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="e9adc-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="e9adc-132">Конечный объект может быть пользователем в вашей организации вместо номера телефона; в этом случае синтаксис для абонента, получающего переадресованные звонки, такой же, как и при указании делегата `sip:<NameofDelegate@domain>`:.</span><span class="sxs-lookup"><span data-stu-id="e9adc-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="e9adc-133">Другой возможный параметр `BusyOption` `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="e9adc-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
                  -Target tel:+2025551234]

</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="e9adc-134">Настройка опции "Пропущенный вызов" для группы SLA</span><span class="sxs-lookup"><span data-stu-id="e9adc-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="e9adc-135">Настроить опцию "Пропущенный вызов" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="e9adc-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
                  -MissedCallOption <Option> -MissedCallForwardTarget
                  <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    
    <span data-ttu-id="e9adc-136">В следующем примере задается, что пропущенные звонки будут переадресованы пользователю `sla_forward_number`с именем.</span><span class="sxs-lookup"><span data-stu-id="e9adc-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="e9adc-137">`-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect`</span><span class="sxs-lookup"><span data-stu-id="e9adc-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="e9adc-138">Если выбрать `Forward`, необходимо также указать `-MissedCallForwardTarget `параметр, указав в качестве целевого номера пользователя или номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e9adc-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget `parameter, with a user or phone number as the target:</span></span>
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
                  Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
            -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 

</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="e9adc-139">Удаление делегата из группы</span><span class="sxs-lookup"><span data-stu-id="e9adc-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="e9adc-140">Удалить делегата из группы можно с помощью командлета [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates):</span><span class="sxs-lookup"><span data-stu-id="e9adc-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    
        Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    <span data-ttu-id="e9adc-141">Например:</span><span class="sxs-lookup"><span data-stu-id="e9adc-141">For example:</span></span>
    
        Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate3@contoso.com

</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="e9adc-142">Удаление группы SLA</span><span class="sxs-lookup"><span data-stu-id="e9adc-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="e9adc-143">Удалить группу SLA можно с помощью командлета [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e9adc-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ``` 
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="e9adc-144">Например:</span><span class="sxs-lookup"><span data-stu-id="e9adc-144">For example:</span></span>
    
        Remove-CsSlaConfiguration -Identity SLAGroup1 

</div>

</div>

<span> </span>

</div>

</div>

</div>

