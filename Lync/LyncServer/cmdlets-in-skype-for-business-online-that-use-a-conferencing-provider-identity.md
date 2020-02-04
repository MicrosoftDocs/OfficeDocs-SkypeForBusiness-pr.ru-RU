---
title: Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 9dc5438a0fe246b1e988d60a0e6ce1ac3d3f6d67
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726719"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи

 


Чтобы получить сведения обо всех поставщиках голосовой конференц-связи, с которыми вы пропустили организацию, вы можете просто вызвать командлет [Get – ксаудиоконференЦингпровидер](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) без каких-либо параметров:

    Get-CsAudioConferencingProvider

Если вы хотите ограничить возвращаемые данные единственным поставщиком (в этом примере — службы голосовой связи Contoso поставщика), а затем использовать параметр Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Только один командлет Skype для бизнеса Online, принимающий идентификатор поставщика видеоконференций:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

