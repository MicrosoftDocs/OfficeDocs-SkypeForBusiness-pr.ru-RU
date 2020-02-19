---
title: 'Lync Server 2013: командлеты управления клиентом'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4639a3e51ca3674cdb521f49ef607f6a50f81fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d0c0f-102">Командлеты управления клиентами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0c0f-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0c0f-103">_**Последнее изменение темы:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="d0c0f-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="d0c0f-104">Управление клиентами состоит в основном за определение того, какие клиентские приложения (например, Microsoft Lync 2013) могут выполнять вход в Lync Server 2013 и определять возможности, доступные этим клиентским приложениям после входа в систему.</span><span class="sxs-lookup"><span data-stu-id="d0c0f-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d0c0f-105">Дополнительные сведения о командлетах можно найти в блоге Lync&nbsp;Server Windows PowerShell по <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>адресу.</span><span class="sxs-lookup"><span data-stu-id="d0c0f-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="d0c0f-106">Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="d0c0f-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="d0c0f-107">Командлеты для управления клиентами</span><span class="sxs-lookup"><span data-stu-id="d0c0f-107">Client Management Cmdlets</span></span>

<span data-ttu-id="d0c0f-108">Большинство задач управления, применяемых к управлению клиентами, можно выполнить с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c0f-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d0c0f-109">Эти же задачи можно выполнить с помощью командлетов из командной консоли Lync Server или из скрипта.</span><span class="sxs-lookup"><span data-stu-id="d0c0f-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="d0c0f-110">Используя скрипты, можно автоматизировать определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="d0c0f-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="d0c0f-111">Далее представлен список командлетов, которые напрямую связаны с управлением клиентами:</span><span class="sxs-lookup"><span data-stu-id="d0c0f-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-113">[Granting — CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-114">[New — CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-115">[Remove — CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-116">[Set — CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d0c0f-117">[New — CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d0c0f-118">[Get — CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-119">[New — CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-120">[Remove — CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-121">[Set — CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d0c0f-122">[Get — CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-123">[Granting — CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-124">[New — CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-125">[Remove — CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-126">[Set — CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d0c0f-127">[Get — CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-128">[New — CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-129">[Remove — CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d0c0f-130">[Set — CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d0c0f-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

