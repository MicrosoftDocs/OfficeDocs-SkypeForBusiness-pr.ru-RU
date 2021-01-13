---
title: (Необязательно) Определение наборов праздников группы ответа в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Создание или изменение наборов праздников группы ответа в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: dd3144c687329f82542d5b658c47212dd390c9fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830989"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="0aa48-103">(Необязательно) Определение наборов праздников группы ответа в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0aa48-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="0aa48-104">Создание или изменение наборов праздников группы ответа в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="0aa48-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0aa48-p101">Параметры праздников служат для определения дней, в которые группа ответа закрыта для использования, а также для определения действия в эти дни. Набор праздников — это коллекция праздников, которая применяется к группе ответа.</span><span class="sxs-lookup"><span data-stu-id="0aa48-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0aa48-107">Если рабочий процесс определяется как управляемый рабочий процесс, пользователь, которому была назначена роль CsResponseGroupManager, может изменять праздники для управляемых им рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="0aa48-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="0aa48-108">Чтобы создать набор праздников</span><span class="sxs-lookup"><span data-stu-id="0aa48-108">To create a holiday set</span></span>

1. <span data-ttu-id="0aa48-109">Войдите в качестве члена группы RTCUniversalServerAdmins или одной из предопределяемых административных ролей, которые поддерживают группу ответа.</span><span class="sxs-lookup"><span data-stu-id="0aa48-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="0aa48-110">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="0aa48-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0aa48-111">Для каждого праздника, который следует определить, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0aa48-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="0aa48-112">Чтобы создать набор праздников, содержащий определенные праздники, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0aa48-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="0aa48-113">В следующем примере приведен набор праздников, включающий два праздника:</span><span class="sxs-lookup"><span data-stu-id="0aa48-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="0aa48-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0aa48-114">See also</span></span>

[<span data-ttu-id="0aa48-115">Проектирование и создание рабочих процессов группы ответа в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0aa48-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="0aa48-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="0aa48-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="0aa48-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="0aa48-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
