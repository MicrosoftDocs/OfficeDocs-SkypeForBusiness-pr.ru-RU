---
title: 'Lync Server 2013: Set-Ксаддрессбукконфигуратион для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a45d5fb9e8ea6eb4b37c34c5347c37c6c9bfe940
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2bd45-102">Set-Ксаддрессбукконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bd45-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bd45-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2bd45-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2bd45-104">Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет Set-Ксаддрессбукконфигуратион локально: Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="2bd45-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="2bd45-105">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2bd45-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="2bd45-106">Set-Ксаддрессбукконфигуратион похож на командлет New-Ксаддрессбукконфигуратион, за исключением того, что он используется для изменения существующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2bd45-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="2bd45-107">Например:</span><span class="sxs-lookup"><span data-stu-id="2bd45-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="2bd45-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2bd45-108">See Also</span></span>


[<span data-ttu-id="2bd45-109">Set-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="2bd45-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

