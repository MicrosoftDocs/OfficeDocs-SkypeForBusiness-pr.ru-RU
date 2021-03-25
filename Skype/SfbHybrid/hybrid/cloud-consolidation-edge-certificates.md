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
description: В этом приложении содержатся подробные действия по обновлению краевого сертификата в рамках консолидации облаков для Teams и Skype для бизнеса.
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120348"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="a2f75-103">Обновление пограничного сертификата</span><span class="sxs-lookup"><span data-stu-id="a2f75-103">Update the edge certificate</span></span>

<span data-ttu-id="a2f75-104">Обновление краевого сертификата — это ключевой шаг к обеспечению того, чтобы предварительная среда с SipDomain1 присоединялась к облачной среде с SipDomain2 и обеспечивала надлежащую маршрутизацию в общей среде адресного пространства в двух доменах SIP.</span><span class="sxs-lookup"><span data-stu-id="a2f75-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="a2f75-105">См. шаг 14 в [области консолидации облачных](cloud-consolidation.md) технологий для Teams и Skype для бизнеса для контекста, в котором можно выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="a2f75-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="a2f75-106">В наших примерах SipDomain1 является AcquiredCompany. <span> com и SipDomain2 — это OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="a2f75-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="a2f75-107">Альтернативное имя субъекта (SAN) сертификата на всех краевом сервере в локальной среде должно быть обновлено, чтобы включить все домены SIP, которые существуют в чистом онлайн-клиенте (за исключением любых onmicrosoft). <span> com доменов), в форме "sip. \<domain> ".</span><span class="sxs-lookup"><span data-stu-id="a2f75-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="a2f75-108">В нашем примере это глоток. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="a2f75-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="a2f75-109">Этот шаг необходимо сделать перед переносом пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="a2f75-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="a2f75-110">**Шаги:**</span><span class="sxs-lookup"><span data-stu-id="a2f75-110">**Steps:**</span></span>

1.  <span data-ttu-id="a2f75-111">Получение нового сертификата External Edge для края, который имеет все существующие записи, а также дополнительные записи в SAN для всех доменов SIP в облачной среде (за исключением доменов \*.onmicrosoft.com) в форме "sIP". <DomainName></span><span class="sxs-lookup"><span data-stu-id="a2f75-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="a2f75-112">Установите сертификат локально на каждом краевом сервере и назначьте его службе Skype Edge на каждой из служб края.</span><span class="sxs-lookup"><span data-stu-id="a2f75-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="a2f75-113">Подробные действия см. в разделе "Сертификаты интерфейса внешних границ" в Службе развертывания edge [в Skype для бизнеса Server 2015.](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)</span><span class="sxs-lookup"><span data-stu-id="a2f75-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="a2f75-114">Перезапустите службу Edge на каждом из серверов края.</span><span class="sxs-lookup"><span data-stu-id="a2f75-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="a2f75-115">Это можно сделать для одного окна со следующими командами PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2f75-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="a2f75-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a2f75-116">See also</span></span>

[<span data-ttu-id="a2f75-117">Консолидация облаков для команд и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2f75-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)