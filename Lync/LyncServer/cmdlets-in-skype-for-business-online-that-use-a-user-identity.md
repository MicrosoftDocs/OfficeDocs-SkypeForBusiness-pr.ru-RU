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
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001264"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя

 


В Skype для бизнеса Online существует несколько различных способов ссылки на индивидуальные удостоверения пользователей.

  - Используйте отображаемое имя доменных служб Active Directory пользователя. Пример:
    
        -Identity "Ken Myer"

  - Используйте SIP адрес пользователя. Пример:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Используйте имя участника-пользователя. Пример:
    
        -Identity " kenmyer@litwareinc.com"

  - Используйте различающееся имя доменных служб Active Directory пользователя. Пример:
    
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

