---
title: 'Lync Server 2013: командлеты для прав и разрешений пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User rights and permissions cmdlets
ms:assetid: b53aae4c-651f-4cbc-a762-ba818d63897e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415672(v=OCS.15)
ms:contentKeyID: 48185178
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2351e00a947a1612d0e7fb05d724ad190404475a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-rights-and-permissions-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f33e1-102">Командлеты прав и разрешений пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f33e1-102">User rights and permissions cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f33e1-103">_**Последнее изменение темы:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="f33e1-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="f33e1-104">Командлеты разрешений пользователя в основном используются для управления доступом на основе ролей (RBAC), новой технологией для делегирования административного управления Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f33e1-104">The user permission cmdlets are primarily used to manage role-based access control (RBAC), the new technology for delegating administrative control of Microsoft Lync Server 2013.</span></span>

<div>

## <a name="user-permission-cmdlets"></a><span data-ttu-id="f33e1-105">Командлеты разрешений пользователей</span><span class="sxs-lookup"><span data-stu-id="f33e1-105">User Permission Cmdlets</span></span>

<span data-ttu-id="f33e1-106">Ниже приведен список командлетов, которые относятся непосредственно к управлению разрешениями пользователей:</span><span class="sxs-lookup"><span data-stu-id="f33e1-106">The following is a list of cmdlets that relate directly to managing user permissions:</span></span>

<span data-ttu-id="f33e1-107">**Разрешения пользователей**</span><span class="sxs-lookup"><span data-stu-id="f33e1-107">**User Permissions**</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-108">[Get — CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-108">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-109">[New — CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-109">[New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-110">[Remove — CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-110">[Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-111">[Set — CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-111">[Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-112">[Update — CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-112">[Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f33e1-113">[Get — CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-113">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f33e1-114">[Granting — CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-114">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-115">[Revoke CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-115">[Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-116">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-116">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f33e1-117">[Granting — CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-117">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-118">[REVOKE CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-118">[Revoke-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f33e1-119">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f33e1-119">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f33e1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f33e1-120">See Also</span></span>


[<span data-ttu-id="f33e1-121">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f33e1-121">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

