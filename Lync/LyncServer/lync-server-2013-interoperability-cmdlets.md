---
title: 'Lync Server 2013: командлеты взаимодействия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability cmdlets
ms:assetid: 18444a0b-7b66-4540-a262-775ea10b3b7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204714(v=OCS.15)
ms:contentKeyID: 48183527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9509fe93e1efbde72896cead2f06ab907bbe46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498456"
---
# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8c98e-102">Командлеты взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c98e-102">Interoperability cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c98e-103">_**Последнее изменение темы:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="8c98e-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="8c98e-104">Командлеты взаимодействия используются для настройки межсерверной проверки подлинности и авторизации между сервером Microsoft Lync Server 2013 и другими серверными продуктами, такими как Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c98e-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="8c98e-105">Проверка подлинности "сервер-сервер" и авторизация обеспечивают простой и удобный обмен данными и общий доступ к данным для этих серверов.</span><span class="sxs-lookup"><span data-stu-id="8c98e-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="8c98e-106">Командлеты взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8c98e-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="8c98e-107">Ниже приведен список командлетов, которые относятся непосредственно к настройке и управлению взаимодействием между Microsoft Lync Server 2013 и другими серверными продуктами:</span><span class="sxs-lookup"><span data-stu-id="8c98e-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="8c98e-108">**Командлеты взаимодействия**</span><span class="sxs-lookup"><span data-stu-id="8c98e-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="8c98e-109">[Get — CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-110">[Set — CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8c98e-111">[Get — CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-111">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-112">[New — CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-112">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-113">[Remove — CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-114">[Set — CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="8c98e-115">[Get — CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-115">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-116">[New — CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-116">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-117">[Remove — CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="8c98e-118">[Set — CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c98e-118">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

