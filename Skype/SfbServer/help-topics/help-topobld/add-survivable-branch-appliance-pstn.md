---
title: Добавление ТСОП для устройства обеспечения связи в филиалах
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: Чтобы определить шлюза телефонной сети (общего пользования PSTN) для обеспечения связи в филиалах в филиале, укажите следующие параметры.
ms.openlocfilehash: df05edb2ee682336cf46fd2fa8a6b7a7b4736696
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888817"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="7ce3a-103">Добавление ТСОП для устройства обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="7ce3a-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="7ce3a-104">Чтобы определить шлюза телефонной сети (общего пользования PSTN) для обеспечения связи в филиалах в филиале, укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="7ce3a-105">Полное доменное имя (FQDN) или IP-адрес для однорангового шлюза, что для обеспечения связи в филиалах или для обеспечения связи в филиалах связано с для маршрутизации входящих и исходящих звонков ТСОП.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ce3a-106">Если вы определяете устройство для обеспечения связи в филиалах, это шлюз, к которому необходимо подключить сервер-посредник внутри устройства для обеспечения связи в филиалах PSTN-соединение.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="7ce3a-p101">Порт прослушивания, который будет использоваться для передачи SIP-сообщений. По умолчанию используются порты TCP 5066 и TLS 5067 на шлюзе, офисной АТС или пограничном контроллере сеансов. На устройстве обеспечения связи на сайте филиала по умолчанию заданы порты 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="7ce3a-110">В целях безопасности настоятельно рекомендуется протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="7ce3a-111">При определении устройства для обеспечения связи в филиалах, обратитесь к документации поставщика для обеспечения связи в филиалах, чтобы убедиться, что ваше устройство для обеспечения связи в филиалах поддерживает протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ce3a-112">В целях безопасности настоятельно рекомендуется развернуть шлюз, который поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7ce3a-113">Если необходимо добавить шлюз в ТСОП, можно настроить его позже, однако полноценные функциональные возможности будут ограничены до полной настройки шлюза в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="7ce3a-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

