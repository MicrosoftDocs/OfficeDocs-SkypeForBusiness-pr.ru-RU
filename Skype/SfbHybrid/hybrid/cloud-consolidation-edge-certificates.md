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
description: В этом приложении содержатся подробные инструкции по обновлению пограничного сертификата в составе облачной консолидации для Teams и Skype для бизнеса.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888608"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="71af2-103">Обновление пограничного сертификата</span><span class="sxs-lookup"><span data-stu-id="71af2-103">Update the edge certificate</span></span>

<span data-ttu-id="71af2-104">Обновление пограничного сертификата это ключевой этап, позволяющий убедиться, что локальная среда с SipDomain1 может присоединиться к облачной среде с SipDomain2 и обеспечить правильную маршрутизацию в среде общего адресного пространства для двух доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="71af2-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="71af2-105">На этапе 14 в разделе [Консолидация в облаке для Teams и Skype для бизнеса](cloud-consolidation.md) в контексте, в котором вы можете выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="71af2-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="71af2-106">В нашем примере SipDomain1 — Аккуиредкомпани. <span>com и SipDomain2 — оригиналкомпани. <span>com.</span><span class="sxs-lookup"><span data-stu-id="71af2-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="71af2-107">Необходимо обновить альтернативное имя субъекта (SAN) сертификата на всех пограничных серверах в локальной среде, чтобы включить все домены SIP, существующие в чистом сетевом клиенте (за исключением всех протоколов onmicrosoft.<span> домены com) в виде "SIP. \<> домена ".</span><span class="sxs-lookup"><span data-stu-id="71af2-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="71af2-108">В нашем примере это SIP. Оригиналкомпани. <span>com.</span><span class="sxs-lookup"><span data-stu-id="71af2-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="71af2-109">Этот шаг очень важен перед переносом пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="71af2-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="71af2-110">**Образом**</span><span class="sxs-lookup"><span data-stu-id="71af2-110">**Steps:**</span></span>

1.  <span data-ttu-id="71af2-111">Получите новый внешний пограничный сертификат для пограничного сервера, у которого есть все существующие записи и дополнительные записи в сети SAN для всех доменов SIP в облачной среде (кроме доменов \*. onmicrosoft.com) в форме "SIP. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="71af2-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="71af2-112">Установите сертификат локально на каждом пограничном сервере и назначьте его службе пограничной службы Skype для каждой пограничной службы.</span><span class="sxs-lookup"><span data-stu-id="71af2-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="71af2-113">Подробное описание действий приведено в разделе "сертификаты внешнего интерфейса [пограничной службы" в службе развертывания пограничной службы в Skype для бизнеса Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="71af2-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="71af2-114">Перезапустите пограничную службу на всех пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="71af2-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="71af2-115">Это можно сделать для одного поля с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="71af2-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="71af2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="71af2-116">See also</span></span>

[<span data-ttu-id="71af2-117">Объединение в облако для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="71af2-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)