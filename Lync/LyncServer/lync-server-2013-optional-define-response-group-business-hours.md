---
title: 'Lync Server 2013: определение рабочих часов для группы ответа (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891dd05caf5e2ec3411da73c1151ae61c2d0630c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524466"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="9a568-102">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a568-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a568-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9a568-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="9a568-104">Определение рабочих часов</span><span class="sxs-lookup"><span data-stu-id="9a568-104">Defining Business Hours</span></span>

<span data-ttu-id="9a568-105">Настройки рабочих часов определяют, когда рабочий процесс доступен для ответа на вызовы, и задают процессы обработки вызовов, поступающих в нерабочее время.</span><span class="sxs-lookup"><span data-stu-id="9a568-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="9a568-106">Администраторы группы ответа могут использовать командлет **New-CsRgsHoursOfBusiness** для создания предварительно заданных расписаний, которые можно использовать для любого количества групп ответа.</span><span class="sxs-lookup"><span data-stu-id="9a568-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9a568-107">При создании или изменении рабочего процесса можно указать настраиваемое расписание, которое применяется только к этому рабочему процессу.</span><span class="sxs-lookup"><span data-stu-id="9a568-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="9a568-108">Дополнительные сведения см. <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">в статье Создание или изменение рабочего процесса сервисной группы в Lync server 2013</A> или <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9a568-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9a568-109">Если рабочий процесс был определен как управляемый, все пользователи, которым назначена роль CsResponseGroupManager, могут задавать и изменять рабочие часы для управляемых ими рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="9a568-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a568-110">Время для параметров в этих командлетах задается в 24-часовом формате (например, 20:00=8:00 PM).</span><span class="sxs-lookup"><span data-stu-id="9a568-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="9a568-111">Создание предварительно определенной коллекции рабочих часов</span><span class="sxs-lookup"><span data-stu-id="9a568-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="9a568-112">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9a568-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="9a568-113">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a568-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a568-114">Для каждого уникального определяемого диапазона рабочих часов выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9a568-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="9a568-115">Чтобы создать коллекцию рабочих часов, использующую заданные диапазоны, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9a568-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="9a568-p103">Ниже приведены примеры, в которых указываются рабочие часы с 9:00 до 17:00 для рабочих дней; с 8:00 до 10:00 и с 14:00 до 18:00 для суббот и не задаются рабочие часы для воскресений:</span><span class="sxs-lookup"><span data-stu-id="9a568-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a568-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9a568-123">See Also</span></span>


[<span data-ttu-id="9a568-124">Создание или изменение рабочего процесса сервисной группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a568-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="9a568-125">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a568-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="9a568-126">New — CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="9a568-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="9a568-127">New — CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="9a568-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

