---
title: Маршрутка между магистралью в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами посредством поддержки маршрутной маршрутации между межуголковой инфраструктурой. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814129"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="f75e7-103">Маршрутка между магистралью в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f75e7-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="f75e7-104">Skype для бизнеса Server обеспечивает базовое управление сеансами посредством поддержки маршрутной маршрутации между межуголковой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="f75e7-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="f75e7-105">Эта возможность позволяет Skype для бизнеса Server предоставлять функции управления звонками в последующих системах телефонии.</span><span class="sxs-lookup"><span data-stu-id="f75e7-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="f75e7-106">Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="f75e7-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="f75e7-107">Аналогичным образом, Skype для бизнеса Server может подключить две или несколько систем IP-УАКС, чтобы можно было делать и делать вызовы между телефонами УАПС из разных систем IP-УАКС.</span><span class="sxs-lookup"><span data-stu-id="f75e7-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="f75e7-108">На следующем рисунке показано, как Skype для бизнеса Server обеспечивает взаимодействие между шлюзом STN и IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f75e7-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Взаимодействие между шлюзом PSTN и IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="f75e7-110">На следующем рисунке показано, как Skype для бизнеса Server подключает две системы IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f75e7-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype для бизнеса Server, подключающий две системы IP-PGX](../../media/two-ip-pbx-systems.jpg)

