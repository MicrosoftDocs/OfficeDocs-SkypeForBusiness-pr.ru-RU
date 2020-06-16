---
title: Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755131"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи

 


Чтобы получить сведения обо всех поставщиках аудио-конференций, с которыми ваша организация осуществляет контракт, можно просто вызвать командлет [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) без параметров:

    Get-CsAudioConferencingProvider

Если вы хотите ограничить возвращаемые данные одним поставщиком (в этом примере — службы аудиоустройства Contoso поставщика), используйте параметр Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Существует только один командлет Skype для бизнеса Online, принимающий идентификатор поставщика аудио-конференций:

  - [Get — CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

