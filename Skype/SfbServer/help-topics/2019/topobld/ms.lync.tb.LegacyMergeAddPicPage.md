---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Внешнее FQDN веб-службы позволяет внешним пользователям присоединяться к собраниям в локальной сети. Введите полное доменное имя внешнего интерфейса веб-аудиоконференции устаревшего сервера.
ms.openlocfilehash: bd259179ea61e20efec2fca81bddd40b0c53f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805709"
---
# <a name="legacy-merge"></a><span data-ttu-id="7bf07-104">Объединение с устаревшей версией</span><span class="sxs-lookup"><span data-stu-id="7bf07-104">Legacy Merge</span></span>

<span data-ttu-id="7bf07-105">Внешнее **FQDN** веб-службы позволяет внешним пользователям присоединяться к собраниям в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="7bf07-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="7bf07-106">Введите полное доменное имя внешнего интерфейса веб-аудиоконференции устаревшего сервера.</span><span class="sxs-lookup"><span data-stu-id="7bf07-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="7bf07-107">Внешний  порт веб-службы, **443,** является портом SIP по умолчанию, настроенным для клиентов.</span><span class="sxs-lookup"><span data-stu-id="7bf07-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="7bf07-108">Если значение по умолчанию не использовалось, обновите значение внешнего порта для внешних **веб-служб.**</span><span class="sxs-lookup"><span data-stu-id="7bf07-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="7bf07-109">Выберите этот **пул, который используется** для федерации и для подключения к общедоступным службе im, если вы планируете использовать этот сервер для федерации.</span><span class="sxs-lookup"><span data-stu-id="7bf07-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="7bf07-110">Если развернуто несколько пограничных серверов, то для федерации будет включен только один из них.</span><span class="sxs-lookup"><span data-stu-id="7bf07-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="7bf07-111">Если этот ящик не будет задан, и позднее вы решите включить федерацию, необходимо снова запустить мастер объединения построитель топологий, а также опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="7bf07-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="7bf07-112">Подробные сведения [см. в этапе 4. Объединение тополий.](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)</span><span class="sxs-lookup"><span data-stu-id="7bf07-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


