---
title: Командлеты в Skype для бизнеса Online, не использующие область или удостоверение
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3dfc2ee8cd812b597f363934475d1996f2e42a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727599"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="37e19-102">Командлеты в Skype для бизнеса Online, не использующие область или удостоверение</span><span class="sxs-lookup"><span data-stu-id="37e19-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="37e19-103">Командлеты, используемые при изменении списков разрешенных и заблокированных списков (списки, которые определяют, какие внешние организации могут взаимодействовать с ними) не используют ни область, ни удостоверение.</span><span class="sxs-lookup"><span data-stu-id="37e19-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="37e19-104">На самом деле командлет **New-кседжеалловаллкновндомаинс** не имеет никаких каких-либо параметров.</span><span class="sxs-lookup"><span data-stu-id="37e19-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="37e19-105">Ниже указаны командлеты, которые не используют ни область, ни удостоверение.</span><span class="sxs-lookup"><span data-stu-id="37e19-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="37e19-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="37e19-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="37e19-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="37e19-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="37e19-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="37e19-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="37e19-109">Обратите внимание, что вместе с командлетом New **-кседжеалловлист** и командлетом **New-кседжедомаинпаттерн** необходимо добавить параметр Domain.</span><span class="sxs-lookup"><span data-stu-id="37e19-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="37e19-110">Например:</span><span class="sxs-lookup"><span data-stu-id="37e19-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="37e19-111">См. также</span><span class="sxs-lookup"><span data-stu-id="37e19-111">See Also</span></span>


[<span data-ttu-id="37e19-112">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="37e19-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="37e19-113">[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="37e19-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

