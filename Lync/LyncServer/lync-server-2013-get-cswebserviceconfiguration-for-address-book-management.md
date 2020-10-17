---
title: 'Lync Server 2013: Get-CsWebServiceConfiguration для управления адресной книгой'
description: 'Lync Server 2013: Get-CsWebServiceConfiguration для управления адресной книгой.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb22d7607f9ac18cda9c8653374ae86839b033e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554645"
---
# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ba84b-103">Get-CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba84b-103">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba84b-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ba84b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ba84b-p101">Кто может запускать данный командлет: по умолчанию членам следующих групп разрешено локально запускать командлет Get-CsWebServiceConfiguration — RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы возвратить список всех ролей управления доступом на основе ролей, которым был назначен данный  командлет (включая любые настраиваемые роли управления доступом на основе ролей, созданные лично вами), выполните следующую команду из командной строки Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ba84b-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="ba84b-p102">Командлет Get-CsWebServiceConfiguration возвращает сведения о конфигурации веб-служб, которая в данный момент используется в организации. С точки зрения служб адресной книги интерес представляет состояние функции расширения списка рассылки. Если атрибут EnableGroupExpansion имеет значение True, ваша организация допускает углубление в группы.</span><span class="sxs-lookup"><span data-stu-id="ba84b-p102">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization. Of interest to the Address Book Services is the status of Distribution List Expansion function. If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="ba84b-110">Например:</span><span class="sxs-lookup"><span data-stu-id="ba84b-110">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="ba84b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ba84b-111">See Also</span></span>


[<span data-ttu-id="ba84b-112">Get — CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba84b-112">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

