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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="1fedc-102">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="1fedc-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="1fedc-103">В Skype для бизнеса Online существует несколько различных способов ссылки на индивидуальные удостоверения пользователей.</span><span class="sxs-lookup"><span data-stu-id="1fedc-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="1fedc-104">Используйте отображаемое имя доменных служб Active Directory пользователя.</span><span class="sxs-lookup"><span data-stu-id="1fedc-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="1fedc-105">Пример:</span><span class="sxs-lookup"><span data-stu-id="1fedc-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="1fedc-106">Используйте SIP адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="1fedc-106">Use the user’s SIP address.</span></span> <span data-ttu-id="1fedc-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="1fedc-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1fedc-108">Используйте имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="1fedc-108">Use the user’s UPN.</span></span> <span data-ttu-id="1fedc-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="1fedc-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="1fedc-110">Используйте различающееся имя доменных служб Active Directory пользователя.</span><span class="sxs-lookup"><span data-stu-id="1fedc-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="1fedc-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="1fedc-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="1fedc-112">Следующие командлеты принимают удостоверение пользователя:</span><span class="sxs-lookup"><span data-stu-id="1fedc-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="1fedc-113">[Disable — CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-114">[Enable — CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-115">[Get — CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-116">[Get — CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-117">[Get — CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-118">[Get — CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-119">[New — CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-120">[Remove — CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-121">[Remove — CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-122">[Set — CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-123">[Set — CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1fedc-124">[Set — CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="1fedc-125">Обратите внимание, что не требуется указывать удостоверение пользователя при вызове одного из командлетов **Get – CS** .</span><span class="sxs-lookup"><span data-stu-id="1fedc-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="1fedc-126">В этом случае командлеты возвращают все экземпляры указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="1fedc-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="1fedc-127">Например, эта команда возвращает сведения обо всех пользователях, которым был разрешен доступ к Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="1fedc-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="1fedc-128">Параметр Identity является обязательным только в том случае, если вы хотите вернуть сведения для определенного пользователя:</span><span class="sxs-lookup"><span data-stu-id="1fedc-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="1fedc-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1fedc-129">See Also</span></span>


[<span data-ttu-id="1fedc-130">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1fedc-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="1fedc-131">[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1fedc-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

