---
title: Командлеты в Skype для бизнеса Online, не использующие область или удостоверение
description: Командлеты в Skype для бизнеса Online, которые не используют область или удостоверение.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d893c4cf9203c8657dfbdfd7fb2bf46dbdfe4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545725"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="e2b58-103">Командлеты в Skype для бизнеса Online, не использующие область или удостоверение</span><span class="sxs-lookup"><span data-stu-id="e2b58-103">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="e2b58-104">Командлеты, используемые при изменении списков разрешенных и заблокированных списков (списков, которые определяют, какие внешние организации могут связываться с пользователями) не используют область или удостоверение.</span><span class="sxs-lookup"><span data-stu-id="e2b58-104">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="e2b58-105">На самом деле командлет **New – кседжеалловаллкновндомаинс** не имеет никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="e2b58-105">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="e2b58-106">Командлеты, которые не используют область или удостоверение,:</span><span class="sxs-lookup"><span data-stu-id="e2b58-106">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="e2b58-107">[New — Кседжеалловаллкновндомаинс](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e2b58-107">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e2b58-108">[New — Кседжеалловлист](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e2b58-108">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e2b58-109">[New — Кседжедомаинпаттерн](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e2b58-109">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="e2b58-110">Обратите внимание, что с помощью командлета **New – кседжеалловлист** и командлета **New кседжедомаинпаттерн** необходимо включить параметр Domain.</span><span class="sxs-lookup"><span data-stu-id="e2b58-110">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="e2b58-111">Например:</span><span class="sxs-lookup"><span data-stu-id="e2b58-111">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="e2b58-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e2b58-112">See Also</span></span>


[<span data-ttu-id="e2b58-113">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e2b58-113">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e2b58-114">[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e2b58-114">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

