---
title: Добавление ТСОП для устройства обеспечения связи в филиалах
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Чтобы определить шлюз общественной коммутируемой телефонной сети (PSTN) для работающего устройства филиала на сайте филиала, укажите следующее:'
ms.openlocfilehash: 3a146a5bf9b879681b0d490a1d03198853c72305
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303668"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="a584e-103">Добавление ТСОП для устройства обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="a584e-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="a584e-104">Чтобы определить шлюз общественной коммутируемой телефонной сети (PSTN) для работающего устройства филиала на сайте филиала, укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="a584e-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="a584e-105">Полное доменное имя (FQDN) или IP-адрес узла шлюза, связанный с устройством, которое может быть бесперебойно или находится на нем, связано с маршрутизацией входящих и исходящих звонков по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="a584e-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a584e-106">Если вы определяете бесперебойно работающее устройство ветвления, это шлюз, на который сервер-посредник может находиться в работающем устройстве филиала, подключается к сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="a584e-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="a584e-p101">Порт прослушивания, который будет использоваться для передачи SIP-сообщений. По умолчанию используются порты TCP 5066 и TLS 5067 на шлюзе, офисной АТС или пограничном контроллере сеансов. На устройстве обеспечения связи на сайте филиала по умолчанию заданы порты 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="a584e-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="a584e-110">В целях безопасности настоятельно рекомендуется протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="a584e-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="a584e-111">Если вы определяете работающее устройство филиала, ознакомьтесь с соответствующей документацией поставщика филиала, чтобы убедиться в том, что устройство, поддерживающее бесперебойную ветвь, поддерживает протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="a584e-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a584e-112">В целях безопасности настоятельно рекомендуется развернуть шлюз, который поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="a584e-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a584e-113">Если необходимо добавить шлюз в ТСОП, можно настроить его позже, однако полноценные функциональные возможности будут ограничены до полной настройки шлюза в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a584e-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

