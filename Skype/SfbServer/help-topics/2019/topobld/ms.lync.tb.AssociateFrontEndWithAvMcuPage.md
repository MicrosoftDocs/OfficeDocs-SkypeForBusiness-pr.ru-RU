---
title: Связывание сервера переднего плана с AV MCU
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
ROBOTS: NOINDEX, NOFOLLOW
description: A аудио- и видеоконференций позволяет передачи аудио- и видеосвязи между пользователей (то есть, если у них соответствующих клиентских устройств, например гарнитуры для звуковых конференций и веб-камер для видеоконференций). Если ваше развертывание поддерживает конференц-связи и включить веб-конференций и A аудио- и видеоконференций, можно совместно расположить A / V Server конференц-связи с сервером переднего плана), или вы можете развернуть один или несколько изолированный A / видео конференций (A / пула аудио-и видеоконференциями) . Если выбран параметр для развертывания изолированного A / V Server конференц-связи, необходимо определить его в построителе топологий.
ms.openlocfilehash: 27484924ee08a413de831e2d33edd20c9c17d763
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069612"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="d9852-105">Связывание сервера переднего плана с AV MCU</span><span class="sxs-lookup"><span data-stu-id="d9852-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="d9852-106">A аудио- и видеоконференций позволяет передачи аудио- и видеосвязи между пользователей (то есть, если у них соответствующих клиентских устройств, например гарнитуры для звуковых конференций и веб-камер для видеоконференций).</span><span class="sxs-lookup"><span data-stu-id="d9852-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="d9852-107">Если ваше развертывание поддерживает конференц-связи и включить веб-конференций и A аудио- и видеоконференций, можно совместно расположить A / V Server конференц-связи с сервером переднего плана), или вы можете развернуть один или несколько изолированный A / видео конференций (A / пула аудио-и видеоконференциями) .</span><span class="sxs-lookup"><span data-stu-id="d9852-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="d9852-108">Если выбран параметр для развертывания изолированного A / V Server конференц-связи, необходимо определить его в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="d9852-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="d9852-109">Все пулы сайта и пулы нескольких центральных сайтов могут использовать же A / V Server конференц-связи, если использование не превышает объем A / V Server конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d9852-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

