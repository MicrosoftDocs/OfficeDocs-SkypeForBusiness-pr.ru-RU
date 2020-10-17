---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя
description: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545655"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя

 


В Skype для бизнеса Online существует несколько различных способов ссылки на индивидуальные удостоверения пользователей.

  - Используйте отображаемое имя доменных служб Active Directory пользователя. Например:
    
        -Identity "Ken Myer"

  - Используйте SIP адрес пользователя. Например:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Используйте имя участника-пользователя. Например:
    
        -Identity " kenmyer@litwareinc.com"

  - Используйте различающееся имя доменных служб Active Directory пользователя. Например:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Следующие командлеты принимают удостоверение пользователя:

  - [Disable — CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable — CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get — CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get — CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get — CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get — CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New — CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [Remove — CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [Remove — CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set — CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Set — CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [Set — CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

Обратите внимание, что не требуется указывать удостоверение пользователя при вызове одного из командлетов **Get – CS** . В этом случае командлеты возвращают все экземпляры указанного элемента. Например, эта команда возвращает сведения обо всех пользователях, которым был разрешен доступ к Skype для бизнеса Online:

    Get-CsOnlineUser

Параметр Identity является обязательным только в том случае, если вы хотите вернуть сведения для определенного пользователя:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

