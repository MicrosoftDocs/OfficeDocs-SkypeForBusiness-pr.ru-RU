---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Полное доменное имя внешних веб-конференций позволяет внешним пользователям присоединяться к собраниям в локальной. Введите полное доменное имя (FQDN) веб-конференций внешнего интерфейса из устаревшего пограничного сервера.
ms.openlocfilehash: 3e426af0b08660eaef619d4fd9cec9da2ca11b32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919754"
---
# <a name="legacy-merge"></a><span data-ttu-id="8520f-104">Объединение с устаревшей версией</span><span class="sxs-lookup"><span data-stu-id="8520f-104">Legacy Merge</span></span>

<span data-ttu-id="8520f-105">**Полное доменное имя внешних веб-конференций** позволяет внешним пользователям присоединяться к собраниям в локальной.</span><span class="sxs-lookup"><span data-stu-id="8520f-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="8520f-106">Введите полное доменное имя (FQDN) веб-конференций внешнего интерфейса из устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8520f-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="8520f-107">Значение **внешнего веб-конференций внешний порт** **443** — номер порта протокол TCP (Transmission Control) Session Initiation Protocol (SIP) по умолчанию, настроенных для клиентов, конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="8520f-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="8520f-108">Если значение по умолчанию не используется, обновите значение **внешнего порта внешних веб-конференций** .</span><span class="sxs-lookup"><span data-stu-id="8520f-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="8520f-109">Установите флажок **этот пограничный пул используется для федерации и общедоступной службы обмена Мгновенными сообщениями** , если вы планируете использовать этот пограничный сервер федерации.</span><span class="sxs-lookup"><span data-stu-id="8520f-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="8520f-110">Если имеется несколько пограничных серверов, развернутых только один из них будет включена поддержка федерации.</span><span class="sxs-lookup"><span data-stu-id="8520f-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="8520f-111">Если не установить этот флажок, а позднее вы решите, что необходимо включить федерацию, вам необходимо снова запустить мастер объединения построителя топологий, а также для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="8520f-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="8520f-112">Дополнительные сведения см [Этап 4: объединение топологий](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="8520f-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


