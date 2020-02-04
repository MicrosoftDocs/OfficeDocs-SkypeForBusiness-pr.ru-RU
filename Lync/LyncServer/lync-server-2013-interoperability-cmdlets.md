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
ms.openlocfilehash: 4fba07f35836e6b8ac5025b887c69bea283846b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4f336-102">Командлеты взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f336-102">Interoperability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f336-103">_**Тема последнего изменения:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="4f336-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="4f336-104">Командлеты взаимодействия используются для настройки проверки подлинности серверов и авторизации сервера Microsoft Lync Server 2013 и других серверных продуктов, таких как Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f336-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="4f336-105">Проверка подлинности серверов и авторизация сервера позволяет этим серверам легко обмениваться данными и обмениваться ими.</span><span class="sxs-lookup"><span data-stu-id="4f336-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="4f336-106">Командлеты взаимодействия</span><span class="sxs-lookup"><span data-stu-id="4f336-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="4f336-107">Ниже приведен список командлетов, которые непосредственно связаны с настройкой и управлением взаимодействием между Microsoft Lync Server 2013 и другими серверными продуктами.</span><span class="sxs-lookup"><span data-stu-id="4f336-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="4f336-108">**Командлеты взаимодействия**</span><span class="sxs-lookup"><span data-stu-id="4f336-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="4f336-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4f336-111">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-111">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-112">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-112">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-113">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-113">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-114">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-114">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4f336-115">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-115">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-116">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-116">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="4f336-118">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f336-118">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

