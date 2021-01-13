---
title: Маршрутка между магистралью в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Узнайте, как Skype для бизнеса Server Корпоративная голосовая связь маршрутику между магистралью.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825605"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="f982a-103">Маршрутка между магистралью в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f982a-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="f982a-104">Узнайте, как Skype для бизнеса Server Корпоративная голосовая связь маршрутику между магистралью.</span><span class="sxs-lookup"><span data-stu-id="f982a-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="f982a-105">Skype для бизнеса Server обеспечивает базовое управление сеансами посредством поддержки маршрутной маршрутации между межуголковой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="f982a-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="f982a-106">Это позволяет Skype для бизнеса Server предоставлять функции управления звонками для нижестоовых телефонных систем.</span><span class="sxs-lookup"><span data-stu-id="f982a-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="f982a-107">Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="f982a-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="f982a-108">Аналогичным образом, Skype для бизнеса Server может подключить две или несколько систем IP-УАКС, чтобы можно было размещать и получить вызовы между телефонами УАПС из разных систем IP-УАКС.</span><span class="sxs-lookup"><span data-stu-id="f982a-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="f982a-109">На следующем рисунке показано, как Skype для бизнеса Server обеспечивает взаимодействие между шлюзом STN и IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f982a-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Схема Lync Server, соединяющего шлюз PSTN/IP-PBX](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="f982a-111">На следующем рисунке показано, как Skype для бизнеса Server подключает две системы IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f982a-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Схема взаимодействия Lync Server с системами IP-PAX](../../media/inter_trunk02.jpg)
  

