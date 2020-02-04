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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="cee07-102">Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="cee07-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="cee07-103">Чтобы получить сведения обо всех поставщиках голосовой конференц-связи, с которыми вы пропустили организацию, вы можете просто вызвать командлет [Get – ксаудиоконференЦингпровидер](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) без каких-либо параметров:</span><span class="sxs-lookup"><span data-stu-id="cee07-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="cee07-104">Если вы хотите ограничить возвращаемые данные единственным поставщиком (в этом примере — службы голосовой связи Contoso поставщика), а затем использовать параметр Identity:</span><span class="sxs-lookup"><span data-stu-id="cee07-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="cee07-105">Только один командлет Skype для бизнеса Online, принимающий идентификатор поставщика видеоконференций:</span><span class="sxs-lookup"><span data-stu-id="cee07-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="cee07-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cee07-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="cee07-107">См. также</span><span class="sxs-lookup"><span data-stu-id="cee07-107">See Also</span></span>


[<span data-ttu-id="cee07-108">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cee07-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="cee07-109">[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cee07-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

