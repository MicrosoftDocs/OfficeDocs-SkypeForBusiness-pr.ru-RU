---
title: Маршрутизация промежуточных магистралей в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Скайп для Business Server обеспечивает управление базовой сеанса по поддержке межмагистральная маршрутизации. '
ms.openlocfilehash: a1486d24c0681df44085db754fda380d653c636b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920515"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="d5dfe-103">Маршрутизация промежуточных магистралей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d5dfe-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="d5dfe-104">Скайп для Business Server обеспечивает управление базовой сеанса по поддержке межмагистральная маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="d5dfe-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="d5dfe-105">Эта возможность позволяет Скайп для Business Server для предоставления функциональных возможностей управления вызов к системам нижестоящие телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d5dfe-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="d5dfe-106">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="d5dfe-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="d5dfe-107">Аналогично Скайп для Business Server можно соединение двух или более IP-УАТС, чтобы звонки можно поместить и полученных между телефонах УАТС из разных IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="d5dfe-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="d5dfe-108">На следующем рисунке показана Скайп для Business Server обеспечивает связь между шлюзом ТСОП и IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="d5dfe-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Связь между шлюзом ТСОП и IP-УАТС](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="d5dfe-110">На следующем рисунке изображена Скайп для соединения двух систем IP-УАТС Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5dfe-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Скайп для соединения двух систем IP-адрес PGX Business Server](../../media/two-ip-pbx-systems.jpg)

