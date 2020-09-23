---
title: Сопоставление сервера переднего плана с AV MCU
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
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
description: Аудио- и видеоконференции позволяют пользователям использовать аудио- и видеосвязь в режиме реального времени (пользователи должны иметь соответствующие клиентские устройства, такие как гарнитуры для аудиоконференций и веб-камеры для видеоконференций). Если в развертывании поддерживаются конференции и включены как веб-конференции, так и аудио- и видеоконференции, можно совместить сервер аудио- и видеоконференций и интерфейсный сервер или развернуть один или несколько отдельных серверов аудио- и видеоконференций (пул аудио- и видеоконференций). Если вы выбрали вариант развертывания автономного сервера аудио-и видеоконференций, необходимо определить его в построителе топологий.
ms.openlocfilehash: a36a2963456c840a842a02285ed39d4de29b3177
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217770"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="b5142-105">Сопоставление сервера переднего плана с AV MCU</span><span class="sxs-lookup"><span data-stu-id="b5142-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="b5142-106">Аудио- и видеоконференции позволяют пользователям использовать аудио- и видеосвязь в режиме реального времени (пользователи должны иметь соответствующие клиентские устройства, такие как гарнитуры для аудиоконференций и веб-камеры для видеоконференций).</span><span class="sxs-lookup"><span data-stu-id="b5142-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="b5142-107">Если в развертывании поддерживаются конференции и включены как веб-конференции, так и аудио- и видеоконференции, можно совместить сервер аудио- и видеоконференций и интерфейсный сервер или развернуть один или несколько отдельных серверов аудио- и видеоконференций (пул аудио- и видеоконференций).</span><span class="sxs-lookup"><span data-stu-id="b5142-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="b5142-108">Если вы выбрали вариант развертывания автономного сервера аудио-и видеоконференций, необходимо определить его в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b5142-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="b5142-109">Все пулы на сайте и пулы нескольких центральных сайтов могут использовать один и тот же сервер аудио-и видеоконференций, если использование не превышает емкости сервера аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="b5142-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

