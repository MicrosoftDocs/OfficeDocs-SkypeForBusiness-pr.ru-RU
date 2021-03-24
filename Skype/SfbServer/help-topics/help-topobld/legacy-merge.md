---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Внешний FQDN веб-конференций позволяет внешним пользователям присоединяться к локальному собранию. Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференции устаревшего edge Server.
ms.openlocfilehash: a6afcf9192a084839895c69f5db454e2f105309c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106705"
---
# <a name="legacy-merge"></a><span data-ttu-id="14248-104">Объединение с устаревшей версией</span><span class="sxs-lookup"><span data-stu-id="14248-104">Legacy Merge</span></span>

<span data-ttu-id="14248-105">Внешний **FQDN** веб-конференций позволяет внешним пользователям присоединяться к локальному собранию.</span><span class="sxs-lookup"><span data-stu-id="14248-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="14248-106">Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференции устаревшего edge Server.</span><span class="sxs-lookup"><span data-stu-id="14248-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="14248-107">Внешний **порт** внешнего порта веб-конференции **443** — это порт протокола инициации сеанса протокола управления передачей по умолчанию (TCP), настроенный для клиентов-конференциаторов.</span><span class="sxs-lookup"><span data-stu-id="14248-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="14248-108">Если значение по умолчанию не использовалось, обнови внешнее значение **порта Внешние** веб-конференциалы.</span><span class="sxs-lookup"><span data-stu-id="14248-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="14248-109">Выберите пул **This Edge, используемый для** проверки подключений федерации и общего чата, если вы планируете использовать этот edge Server для федерации.</span><span class="sxs-lookup"><span data-stu-id="14248-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="14248-110">Если развернуто несколько пограничных серверов, то для федерации будет включен только один из них.</span><span class="sxs-lookup"><span data-stu-id="14248-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="14248-111">Если вы не проверяете это поле и решите позже включить федерацию, необходимо снова запустить мастер слияния строителей топологии, а также опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="14248-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="14248-112">Подробные сведения [см. в материале Phase 4: Merge Topologies.](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)</span><span class="sxs-lookup"><span data-stu-id="14248-112">For details, see [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).</span></span>