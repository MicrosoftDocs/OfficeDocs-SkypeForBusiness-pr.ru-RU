---
title: Связывание сервера переднего плана с AV MCU
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
ROBOTS: NOINDEX, NOFOLLOW
description: Видеоконференции/V-связь – это возможность голосовой и видеосвязи между пользователями в режиме реального времени (например, если у них есть соответствующие клиентские устройства, такие как гарнитуры для голосовой конференции и веб-камеры для видеоконференций). Если ваше развертывание поддерживает Конференции и вы разрешите как веб-конференции, так и конференции с помощью однорангового сервера, вы можете разгруппировать сервер конференций (A/V) с помощью сервер переднего плана, а также можно развернуть один или несколько изолированных серверов конференций (пула конференций). Если вы выбрали параметр для развертывания отдельного сервера конференц-связи A/V, необходимо определить его в построителе топологии.
ms.openlocfilehash: 92b93cdfaf4e0beb4c097d1119a7189c1cf8dfc4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702494"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="d5109-105">Связывание сервера переднего плана с AV MCU</span><span class="sxs-lookup"><span data-stu-id="d5109-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="d5109-106">Видеоконференции/V-связь – это возможность голосовой и видеосвязи между пользователями в режиме реального времени (например, если у них есть соответствующие клиентские устройства, такие как гарнитуры для голосовой конференции и веб-камеры для видеоконференций).</span><span class="sxs-lookup"><span data-stu-id="d5109-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="d5109-107">Если ваше развертывание поддерживает Конференции и вы разрешите как веб-конференции, так и конференции с помощью однорангового сервера, вы можете разгруппировать сервер конференций (A/V) с помощью сервер переднего плана, а также можно развернуть один или несколько изолированных серверов конференций (пула конференций).</span><span class="sxs-lookup"><span data-stu-id="d5109-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="d5109-108">Если вы выбрали параметр для развертывания отдельного сервера конференц-связи A/V, необходимо определить его в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="d5109-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="d5109-109">Все пулы на сайте и пулы нескольких центральных сайтов могут использовать один и тот же сервер конференц-связи, если использование не превышает возможности сервера конференц-связи A/V.</span><span class="sxs-lookup"><span data-stu-id="d5109-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

