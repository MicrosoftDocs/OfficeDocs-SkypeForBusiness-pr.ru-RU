---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 94c29eb2aadefcb6a9f3ca9b5c11a49f7e41167a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728129"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя

 


В Skype для бизнеса Online есть несколько способов ссылки на индивидуальные удостоверения пользователей.

  - Введите отображаемое имя пользователя доменных служб Active Directory. Например:
    
        -Identity "Ken Myer"

  - Используйте SIP-адрес пользователя. Например:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Используйте имя участника-пользователя. Например:
    
        -Identity " kenmyer@litwareinc.com"

  - Используйте различающееся имя доменных служб Active Directory пользователя. Например:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Следующие командлеты допускают удостоверение пользователя:

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))

Обратите внимание, что при вызове одного из командлетов **Get-CS** вам не нужно указывать удостоверение пользователя. В этом случае командлеты возвращают все экземпляры указанного элемента. Например, эта команда возвращает сведения обо всех пользователях, которые были включены в Skype для бизнеса Online:

    Get-CsOnlineUser

Параметр Identity является обязательным только в том случае, если вы хотите вернуть сведения для определенного пользователя:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>См. также


[Удостоверения, области и клиенты в Skype для бизнеса Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

