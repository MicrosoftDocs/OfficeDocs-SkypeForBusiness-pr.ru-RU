---
title: 'Lync Server 2013: Remove-CsWebServiceConfiguration для управления адресной книгой'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62ad914027fc1d406ba66d2dead2b8eab7601ff7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536496"
---
# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="64522-102">Remove-CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64522-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64522-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="64522-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="64522-p101">Кто может выполнять этот командлет: по умолчанию право на локальный запуск командлета Remove-CsWebServiceConfiguration имеют члены следующих групп: RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.</span><span class="sxs-lookup"><span data-stu-id="64522-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="64522-p102">Командлет Remove-CsWebServiceConfiguration позволяет администратору удалять ранее созданную конфигурацию веб-служб. Командлет не позволяет удалять глобальную конфигурацию веб-служб.</span><span class="sxs-lookup"><span data-stu-id="64522-p102">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration. The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="64522-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="64522-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="64522-109">См. также</span><span class="sxs-lookup"><span data-stu-id="64522-109">See Also</span></span>


[<span data-ttu-id="64522-110">Remove — CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="64522-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

