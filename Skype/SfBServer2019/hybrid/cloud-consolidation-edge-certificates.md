---
title: Обновление сертификатов пограничного сервера
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении включает в себя подробные шаги для обновления сертификатов пограничного сервера как часть облака консолидации для групп и Скайп для бизнеса.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247704"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="c23e9-103">Обновление сертификатов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c23e9-103">Update the edge certificate</span></span>

<span data-ttu-id="c23e9-104">Обновление сертификатов пограничного сервера — это ключевые шаг, чтобы проверка того, что на prem среде с SipDomain1 присоединиться к облачной среде с SipDomain2 и обеспечить правильную маршрутизацию в среде общее адресное пространство между этими двумя доменами SIP.</span><span class="sxs-lookup"><span data-stu-id="c23e9-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="c23e9-105">В разделе шаг 14 в [облаке консолидации для групп и Скайп для бизнеса](cloud-consolidation.md) для контекста, в котором может выполнить это действие.</span><span class="sxs-lookup"><span data-stu-id="c23e9-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="c23e9-106">В нашем примере SipDomain1 — AcquiredCompany. <span>com и SipDomain2 — это OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="c23e9-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="c23e9-107">Альтернативное имя субъекта (SAN) сертификата на все пограничные серверы в локальной среде необходимо обновить для включения всех доменов SIP, существующих в чисто интерактивного клиента (за исключением любой onmicrosoft.<span> домены COM), в форме «sip. \<домена >».</span><span class="sxs-lookup"><span data-stu-id="c23e9-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="c23e9-108">В нашем примере это sip. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="c23e9-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="c23e9-109">Этот шаг крайне важна для выполнения до миграции пользователей в облаке.</span><span class="sxs-lookup"><span data-stu-id="c23e9-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="c23e9-110">**Действия:**</span><span class="sxs-lookup"><span data-stu-id="c23e9-110">**Steps:**</span></span>

1.  <span data-ttu-id="c23e9-111">Получить новый сертификат для внешнего пограничного сервера для пограничного сервера, который содержит все существующие записи, а также дополнительные записи в сети хранения данных для всех доменов SIP в облачной среде (за исключением \*. onmicrosoft.com домены) в виде «sip. <DomainName>«.</span><span class="sxs-lookup"><span data-stu-id="c23e9-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="c23e9-112">Установите сертификат локально на каждом пограничном сервере и назначьте его Скайп Пограничная служба на каждом из службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="c23e9-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="c23e9-113">Подробное описание шагов в разделе «Внешний пограничный сервер интерфейса сертификаты» в [Развертывание службы пограничного сервера в Скайп для Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="c23e9-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="c23e9-114">Перезапуск службы пограничного сервера на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="c23e9-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="c23e9-115">Это можно сделать для одного поля с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c23e9-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="c23e9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c23e9-116">See also</span></span>

[<span data-ttu-id="c23e9-117">Консолидация облако для групп и Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c23e9-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)