---
title: Командлеты в Skype для бизнеса Online, не использующие область или удостоверение
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841092"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Командлеты в Skype для бизнеса Online, не использующие область или удостоверение

 


Командлеты, используемые при изменении списков разрешенных и заблокированных списков (списки, которые определяют, какие внешние организации могут взаимодействовать с ними) не используют ни область, ни удостоверение. На самом деле командлет **New-кседжеалловаллкновндомаинс** не имеет никаких каких-либо параметров. Ниже указаны командлеты, которые не используют ни область, ни удостоверение.

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))

Обратите внимание, что вместе с командлетом New **-кседжеалловлист** и командлетом **New-кседжедомаинпаттерн** необходимо добавить параметр Domain. Например:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

