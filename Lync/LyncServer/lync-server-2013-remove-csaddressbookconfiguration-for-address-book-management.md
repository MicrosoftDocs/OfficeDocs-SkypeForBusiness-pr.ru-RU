---
title: Remove-CsAddressBookConfiguration для управления адресной книгой
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsAddressBookConfiguration for Address Book management
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48184258
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbb16b55191d115047208cd74f3276815f49b1d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536506"
---
# <a name="remove-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="1ff34-102">Remove-CsAddressBookConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff34-102">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff34-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1ff34-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1ff34-p101">По умолчанию право на локальный запуск командлета Remove-CsAddressBookConfiguration имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1ff34-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

<span data-ttu-id="1ff34-106">Как следует из названия, командлет Remove-CsAddressBookConfiguration будет удалять конфигурацию в зависимости от заданного удостоверения сайта.</span><span class="sxs-lookup"><span data-stu-id="1ff34-106">As the name implies, Remove-CsAddressBookConfiguration will remove the configuration based on the defined Site Identity.</span></span>

<span data-ttu-id="1ff34-107">Например:</span><span class="sxs-lookup"><span data-stu-id="1ff34-107">For example:</span></span>

    Remove-CsAddressBookConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="1ff34-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1ff34-108">See Also</span></span>


<span data-ttu-id="1ff34-109">[Remove — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1ff34-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

