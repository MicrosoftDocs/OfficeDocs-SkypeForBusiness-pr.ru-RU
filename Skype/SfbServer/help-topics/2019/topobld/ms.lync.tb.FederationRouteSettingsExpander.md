---
title: Расширитель настроек маршрута федерации
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы задать назначение федеративного маршрута сайта, сначала необходимо включена функция на пограничном сервере или пула пограничных серверов федерации. Если федерация не включен на пограничном сервере или в пуле, параметры назначение маршрута федерации для сайта не будет доступен для изменения.
ms.openlocfilehash: 989ebd13e4491e7b4c28bb936795f9532d7fe88f
ms.sourcegitcommit: 905ba61de9622dd485ff375fa75bb0d76bac0b55
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "22196043"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="96d3a-104">Расширитель настроек маршрута федерации</span><span class="sxs-lookup"><span data-stu-id="96d3a-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="96d3a-105">Чтобы задать назначение федеративного маршрута сайта, сначала необходимо включена функция на пограничном сервере или пула пограничных серверов федерации.</span><span class="sxs-lookup"><span data-stu-id="96d3a-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="96d3a-106">Если федерация не включен на пограничном сервере или в пуле, параметры назначение маршрута федерации для сайта не будет доступен для изменения.</span><span class="sxs-lookup"><span data-stu-id="96d3a-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="96d3a-107">Если параметр федерации на пограничном сервере или пуле был настроен, можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="96d3a-108">**Разрешить назначения маршрута федерации ко всем сайтам** Этот параметр повлияет на всех сайтах.</span><span class="sxs-lookup"><span data-stu-id="96d3a-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="96d3a-109">Убедитесь, что параметр, который настраивается на этом сайте подходит для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="96d3a-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="96d3a-110">**Включить SIP-федерацию** Установите этот флажок, чтобы включить маршрут федерации SIP и затем выберите пул директоров или пограничный в качестве маршрута федерации.</span><span class="sxs-lookup"><span data-stu-id="96d3a-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="96d3a-111">**Включить поддержку федерации XMPP** Установите этот флажок, чтобы включить маршрут федерации XMPP и затем выберите пул директоров или пограничный в качестве маршрута федерации.</span><span class="sxs-lookup"><span data-stu-id="96d3a-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
> [!NOTE]
> <span data-ttu-id="96d3a-112">XMPP шлюзов и прокси-серверы, доступные в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="96d3a-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="96d3a-113">Для получения дополнительных сведений в разделе [федерации XMPP миграции](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="96d3a-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

