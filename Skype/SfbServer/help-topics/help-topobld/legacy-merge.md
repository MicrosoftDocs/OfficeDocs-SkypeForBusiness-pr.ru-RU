---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Внешнее полное доменное имя веб-конференций позволяет внешним пользователям присоединяться к локальным собраниям. Введите полное доменное имя внешнего интерфейса веб-конференций устаревшего пограничного сервера.
ms.openlocfilehash: 984d40f8797a974a5865cca37ba1057dc638d886
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218000"
---
# <a name="legacy-merge"></a><span data-ttu-id="79cc6-104">Объединение с устаревшей версией</span><span class="sxs-lookup"><span data-stu-id="79cc6-104">Legacy Merge</span></span>

<span data-ttu-id="79cc6-105">**Внешнее полное доменное имя веб-конференций** позволяет внешним пользователям присоединяться к локальным собраниям.</span><span class="sxs-lookup"><span data-stu-id="79cc6-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="79cc6-106">Введите полное доменное имя внешнего интерфейса веб-конференций устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="79cc6-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="79cc6-107">Внешний **порт для внешнего веб-конференций** **443** — это порт SIP, настроенный для клиентов конференц-связи по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="79cc6-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="79cc6-108">Если значение по умолчанию не было использовано, обновите значение **внешнего порта для внешнего веб-конференций** .</span><span class="sxs-lookup"><span data-stu-id="79cc6-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="79cc6-109">Установите флажок **этот пограничный пул используется для Федерации и общедоступной службы обмена мгновенными сообщениями** , если вы планируете использовать этот пограничный сервер для Федерации.</span><span class="sxs-lookup"><span data-stu-id="79cc6-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="79cc6-110">Если развернуто несколько пограничных серверов, то для федерации будет включен только один из них.</span><span class="sxs-lookup"><span data-stu-id="79cc6-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="79cc6-111">Если вы не установите этот флажок, и вы решите, что вы хотите включить федерацию, необходимо еще раз запустить мастер объединения построителя топологий, а также опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="79cc6-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="79cc6-112">Дополнительные сведения приведены в статье [Этап 4: объединение топологий](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="79cc6-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


