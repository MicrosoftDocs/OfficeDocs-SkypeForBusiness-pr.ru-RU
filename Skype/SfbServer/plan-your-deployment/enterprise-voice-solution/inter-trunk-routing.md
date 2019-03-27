---
title: Маршрутизация промежуточных магистралей в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Узнайте, как Скайп для корпоративной голосовой связи Business Server поддерживает Маршрутизация промежуточных магистралей.
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892662"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="ccae1-103">Маршрутизация промежуточных магистралей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ccae1-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="ccae1-104">Узнайте, как Скайп для корпоративной голосовой связи Business Server поддерживает Маршрутизация промежуточных магистралей.</span><span class="sxs-lookup"><span data-stu-id="ccae1-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="ccae1-105">Скайп для Business Server обеспечивает управление базовой сеанса по поддержке межмагистральная маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="ccae1-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="ccae1-106">Это позволяет Скайп для Business Server для предоставления функциональных возможностей управления вызов к системам нижестоящие телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="ccae1-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="ccae1-107">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="ccae1-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="ccae1-108">Аналогично Скайп для Business Server можно соединение двух или более IP-УАТС, чтобы звонки можно поместить и полученных между телефонах УАТС из разных IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="ccae1-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="ccae1-109">На следующем рисунке показана Скайп для Business Server обеспечивает связь между шлюзом ТСОП и IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="ccae1-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="ccae1-111">На следующем рисунке изображена Скайп для соединения двух систем IP-УАТС Business Server.</span><span class="sxs-lookup"><span data-stu-id="ccae1-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Схема соединений между системами IP-УАТС с помощью Lync Server](../../media/inter_trunk02.jpg)
  

