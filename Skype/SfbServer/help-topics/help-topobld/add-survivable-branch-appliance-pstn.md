---
title: Добавление ТСОП для устройства обеспечения связи в филиалах
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: Чтобы определить шлюз в телефонную сеть общего пользования (ТСОП) для устройства обеспечения связи в филиале, укажите следующие параметры.
ms.openlocfilehash: a911e94306999645b9f631f1e9b37d405bd1d155
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828609"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="adeac-103">Добавление ТСОП для устройства обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="adeac-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="adeac-104">Чтобы определить шлюз в телефонную сеть общего пользования (ТСОП) для устройства обеспечения связи в филиале, укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="adeac-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="adeac-105">Полное доменное имя или IP-адрес шлюза, с которым сопоставлено устройство или сервер обеспечения связи на филиалах, для маршрутизации входящих и исходящих вызовов ТСОП.</span><span class="sxs-lookup"><span data-stu-id="adeac-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="adeac-106">При определении устройства обеспечения связи на филиалах здесь указывается шлюз, к которому подключается сервер-посредник в устройстве обеспечения связи для выхода в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="adeac-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="adeac-p101">Порт прослушивания, который будет использоваться для передачи SIP-сообщений. По умолчанию используются порты TCP 5066 и TLS 5067 на шлюзе, офисной АТС или пограничном контроллере сеансов. На устройстве обеспечения связи на сайте филиала по умолчанию заданы порты 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="adeac-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="adeac-p102">В целях безопасности настоятельно рекомендуем использовать TLS. Если необходимо определить устройство обеспечения связи на филиалах, обратитесь к документации производителей этих устройств, чтобы убедиться в поддержке протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="adeac-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="adeac-112">В целях безопасности настоятельно рекомендуется развернуть шлюз, который поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="adeac-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="adeac-113">Если необходимо добавить шлюз в ТСОП, можно настроить его позже, однако полноценные функциональные возможности будут ограничены до полной настройки шлюза в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="adeac-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

