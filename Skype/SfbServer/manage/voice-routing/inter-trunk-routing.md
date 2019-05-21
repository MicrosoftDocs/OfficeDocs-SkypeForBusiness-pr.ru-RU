---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274970"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="06653-103">Маршрутизация с межмагистральными узлами в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="06653-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="06653-104">Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="06653-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="06653-105">Эта возможность позволяет Skype для бизнеса Server обеспечивать функции управления звонками для более нижестоящих систем телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="06653-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="06653-106">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="06653-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="06653-107">Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="06653-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="06653-108">На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="06653-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Связь между шлюзом PSTN и IP-УАТС](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="06653-110">На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.</span><span class="sxs-lookup"><span data-stu-id="06653-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype для бизнеса Server, соединяющий две системы IP-ПГКС](../../media/two-ip-pbx-systems.jpg)

