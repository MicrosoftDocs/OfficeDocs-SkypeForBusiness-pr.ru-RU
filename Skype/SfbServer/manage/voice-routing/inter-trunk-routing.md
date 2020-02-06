---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816969"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="a4d3f-103">Маршрутизация с межмагистральными узлами в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a4d3f-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="a4d3f-104">Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="a4d3f-105">Эта возможность позволяет Skype для бизнеса Server обеспечивать функции управления звонками для более нижестоящих систем телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="a4d3f-106">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="a4d3f-107">Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="a4d3f-108">На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Связь между шлюзом PSTN и IP-УАТС](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="a4d3f-110">На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype для бизнеса Server, соединяющий две системы IP-ПГКС](../../media/two-ip-pbx-systems.jpg)

