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
ms.openlocfilehash: ad366315bbc4acf5afb417262da92a5683a084df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001734"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Командлеты в Skype для бизнеса Online, не использующие область или удостоверение

 


Командлеты, используемые при изменении списков разрешенных и заблокированных списков (списков, которые определяют, какие внешние организации могут связываться с пользователями) не используют область или удостоверение. На самом деле командлет **New – кседжеалловаллкновндомаинс** не имеет никаких параметров. Командлеты, которые не используют область или удостоверение,:

  - [New — Кседжеалловаллкновндомаинс](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [New — Кседжеалловлист](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [New — Кседжедомаинпаттерн](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

Обратите внимание, что с помощью командлета **New – кседжеалловлист** и командлета **New кседжедомаинпаттерн** необходимо включить параметр Domain. Пример:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

