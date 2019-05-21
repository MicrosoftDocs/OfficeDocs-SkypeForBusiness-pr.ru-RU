---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Сведения о том, как в Skype для бизнеса Server Enterprise поддерживается межмагистральная маршрутизация.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276833"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="f91c7-103">Маршрутизация с межмагистральными узлами в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f91c7-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="f91c7-104">Сведения о том, как в Skype для бизнеса Server Enterprise поддерживается межмагистральная маршрутизация.</span><span class="sxs-lookup"><span data-stu-id="f91c7-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="f91c7-105">Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="f91c7-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="f91c7-106">Это позволяет серверу Skype для бизнеса Server обеспечивать функции управления звонками для вызываемых систем телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="f91c7-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="f91c7-107">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="f91c7-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="f91c7-108">Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="f91c7-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="f91c7-109">На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f91c7-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="f91c7-111">На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.</span><span class="sxs-lookup"><span data-stu-id="f91c7-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Схема соединений между системами IP-УАТС с помощью Lync Server](../../media/inter_trunk02.jpg)
  

