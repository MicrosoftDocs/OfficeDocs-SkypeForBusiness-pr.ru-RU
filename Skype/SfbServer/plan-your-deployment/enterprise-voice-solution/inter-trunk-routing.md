---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Сведения о том, как в Skype для бизнеса Server Enterprise поддерживается межмагистральная маршрутизация.
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802859"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="af377-103">Маршрутизация с межмагистральными узлами в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="af377-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="af377-104">Сведения о том, как в Skype для бизнеса Server Enterprise поддерживается межмагистральная маршрутизация.</span><span class="sxs-lookup"><span data-stu-id="af377-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="af377-105">Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="af377-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="af377-106">Это позволяет серверу Skype для бизнеса Server обеспечивать функции управления звонками для вызываемых систем телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="af377-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="af377-107">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="af377-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="af377-108">Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="af377-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="af377-109">На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="af377-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="af377-111">На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.</span><span class="sxs-lookup"><span data-stu-id="af377-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Схема соединений между системами IP-УАТС с помощью Lync Server](../../media/inter_trunk02.jpg)
  

