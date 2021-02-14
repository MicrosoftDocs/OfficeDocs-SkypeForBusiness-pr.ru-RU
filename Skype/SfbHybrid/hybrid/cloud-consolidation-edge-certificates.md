---
title: Обновление пограничного сертификата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержатся подробные инструкции по обновлению сертификата edge в рамках консолидации облака для Teams и Skype для бизнеса.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888608"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="07b37-103">Обновление пограничного сертификата</span><span class="sxs-lookup"><span data-stu-id="07b37-103">Update the edge certificate</span></span>

<span data-ttu-id="07b37-104">Обновление сертификата границы — это ключевой шаг, обеспечивающий, чтобы среда с SipDomain1 в среде, в которой есть SipDomain1, присоединила облачную среду с SipDomain2 и обеспечивала правильную маршрутизацию в общей среде адресного пространства между двумя доменами SIP.</span><span class="sxs-lookup"><span data-stu-id="07b37-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="07b37-105">См. шаг 14 в консолидации [облачных звонков](cloud-consolidation.md) для Teams и Skype для бизнеса для контекста, в котором можно выполнить это шаг.</span><span class="sxs-lookup"><span data-stu-id="07b37-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="07b37-106">В наших примерах SipDomain1 — AcquiredCompany. <span> com и SipDomain2 — OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="07b37-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="07b37-107">Альтернативное имя субъекта (SAN) сертификата на всех серверах в локальной среде необходимо обновить, чтобы включить все домены SIP, которые существуют в чисто интерактивном клиенте (за исключением любых onmicrosoft). <span> com domains), в формате "sip. \< домен>".</span><span class="sxs-lookup"><span data-stu-id="07b37-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="07b37-108">В нашем примере это sip. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="07b37-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="07b37-109">Это крайне важно сделать перед переносом пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="07b37-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="07b37-110">**Шаги:**</span><span class="sxs-lookup"><span data-stu-id="07b37-110">**Steps:**</span></span>

1.  <span data-ttu-id="07b37-111">Получите новый сертификат внешней границы для края, который имеет все существующие записи, а также дополнительные записи в SAN для всех доменов SIP в облачной среде (за исключением доменов \*.onmicrosoft.com) в формате <DomainName> "sip.".</span><span class="sxs-lookup"><span data-stu-id="07b37-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="07b37-112">Установите сертификат локально на каждом сервере и назначьте его службе Skype Edge на каждой из этих служб.</span><span class="sxs-lookup"><span data-stu-id="07b37-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="07b37-113">Дополнительные сведения см. в разделе "Сертификаты внешнего интерфейса внешнего интерфейса" статьи "Развертывание службы [edge в Skype для бизнеса Server 2015".](https://technet.microsoft.com/library/dn951368.aspx)</span><span class="sxs-lookup"><span data-stu-id="07b37-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="07b37-114">Перезапустите по краям службу на каждом из этих серверов.</span><span class="sxs-lookup"><span data-stu-id="07b37-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="07b37-115">Это можно сделать для одного окна с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="07b37-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="07b37-116">См. также</span><span class="sxs-lookup"><span data-stu-id="07b37-116">See also</span></span>

[<span data-ttu-id="07b37-117">Консолидация облака для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="07b37-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)