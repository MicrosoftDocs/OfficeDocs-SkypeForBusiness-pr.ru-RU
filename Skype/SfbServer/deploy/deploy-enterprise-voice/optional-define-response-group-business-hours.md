---
title: Необязательно Определение группы ответа "Часы" в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Создавайте и изменяйте рабочие часы группы ответа в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 602494d014c1a3c7874c91462f88b4bcd84f0abb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003109"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="2e1af-103">Необязательно Определение группы ответа "Часы" в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2e1af-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="2e1af-104">Создавайте и изменяйте рабочие часы группы ответа в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2e1af-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="2e1af-105">Определение рабочих часов</span><span class="sxs-lookup"><span data-stu-id="2e1af-105">Defining Business Hours</span></span>

<span data-ttu-id="2e1af-106">Настройки рабочих часов определяют, когда рабочий процесс доступен для ответа на вызовы, и задают процессы обработки вызовов, поступающих в нерабочее время.</span><span class="sxs-lookup"><span data-stu-id="2e1af-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="2e1af-107">Администраторы группы ответа могут использовать командлет **New-CsRgsHoursOfBusiness** для создания предварительно заданных расписаний, которые можно использовать для любого количества групп ответа.</span><span class="sxs-lookup"><span data-stu-id="2e1af-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="2e1af-108">При создании или изменении рабочего процесса можно задать настраиваемое расписание, которое будет применяться только к этому рабочему процессу.</span><span class="sxs-lookup"><span data-stu-id="2e1af-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="2e1af-109">Подробные сведения можно найти [в разделе Создание и создание рабочих процессов групп ответа в Skype для бизнеса](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="2e1af-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2e1af-110">Если рабочий процесс был определен как управляемый, все пользователи, которым назначена роль CsResponseGroupManager, могут задавать и изменять рабочие часы для управляемых ими рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="2e1af-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2e1af-111">Время для параметров в этих командлетах задается в 24-часовом формате (например, 20:00=8:00 PM).</span><span class="sxs-lookup"><span data-stu-id="2e1af-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="2e1af-112">Создание предварительно определенной коллекции рабочих часов</span><span class="sxs-lookup"><span data-stu-id="2e1af-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="2e1af-113">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="2e1af-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="2e1af-114">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2e1af-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2e1af-115">Для каждого уникального определяемого диапазона рабочих часов выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2e1af-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="2e1af-116">Чтобы создать коллекцию рабочих часов, использующую заданные диапазоны, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2e1af-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="2e1af-p103">Ниже приведены примеры, в которых указываются рабочие часы с 9:00 до 17:00 для рабочих дней; с 8:00 до 10:00 и с 14:00 до 18:00 для суббот и не задаются рабочие часы для воскресений:</span><span class="sxs-lookup"><span data-stu-id="2e1af-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="2e1af-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2e1af-124">See also</span></span>

[<span data-ttu-id="2e1af-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="2e1af-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="2e1af-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="2e1af-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
