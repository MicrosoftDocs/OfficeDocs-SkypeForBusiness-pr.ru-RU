---
title: 'Lync Server 2013: (необязательно) Определение наборов праздников группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e6751a5f5915e73d181efba40976640c65e0909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a>Необязательно Определение наборов праздников группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-07_

Параметры праздников служат для определения дней, в которые группа ответа закрыта для использования, а также для определения действия в эти дни. Набор праздников — это коллекция праздников, которая применяется к группе ответа.

<div>


> [!NOTE]  
> Если рабочий процесс определяется как управляемый рабочий процесс, пользователь, которому была назначена роль CsResponseGroupManager, может изменять праздники для управляемых им рабочих процессов.



</div>

<div>

## <a name="to-create-a-holiday-set"></a>Чтобы создать набор праздников

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Для каждого праздника, который следует определить, выполните следующую команду:
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Чтобы создать набор праздников, содержащий определенные праздники, выполните следующую команду:
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    В следующем примере приведен набор праздников, включающий два праздника:
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение рабочего процесса группы слежения в Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Создание или изменение интерактивного рабочего процесса в Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[New-Ксргшолидай](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

