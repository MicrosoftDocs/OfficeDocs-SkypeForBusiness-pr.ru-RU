---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Внешнее полное доменное имя веб-конференций позволяет внешним пользователям присоединяться к локальным собраниям. Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференций, который является внешним для старого пограничного сервера.
ms.openlocfilehash: 96b69e53b0f7538412c6bad7cebbf8e964607b48
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300156"
---
# <a name="legacy-merge"></a><span data-ttu-id="1adef-104">Объединение с устаревшей версией</span><span class="sxs-lookup"><span data-stu-id="1adef-104">Legacy Merge</span></span>

<span data-ttu-id="1adef-105">**Внешнее полное доменное имя веб-конференций** позволяет внешним пользователям присоединяться к локальным собраниям.</span><span class="sxs-lookup"><span data-stu-id="1adef-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="1adef-106">Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференций, который является внешним для старого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1adef-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="1adef-107">Внешний **порт для внешней веб-конференции** **443** — это порт SIP, настроенный по умолчанию для клиентов конференций.</span><span class="sxs-lookup"><span data-stu-id="1adef-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="1adef-108">Если значение по умолчанию не использовалось, обновите значение **внешнего порта для внешней веб-конференции** .</span><span class="sxs-lookup"><span data-stu-id="1adef-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="1adef-109">Если вы планируете использовать этот пограничный сервер для интеграции, установите флажок **этот пул пограничного сервера используется для подключения к службам федерации и общедоступного обмена мгновенными сообщениями** .</span><span class="sxs-lookup"><span data-stu-id="1adef-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="1adef-110">Если вы развернули несколько пограничных серверов, для Федерации будут включены только один из них.</span><span class="sxs-lookup"><span data-stu-id="1adef-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="1adef-111">Если вы не установите этот флажок, и вы решите, что вы хотите включить федерацию, необходимо снова запустить мастер слияния построителя топологии и опубликовать свою топологию.</span><span class="sxs-lookup"><span data-stu-id="1adef-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="1adef-112">Подробности можно найти в разделе [Этап 4: объединение топологий](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="1adef-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


