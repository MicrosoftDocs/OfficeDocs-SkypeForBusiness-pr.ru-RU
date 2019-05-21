---
title: Расширитель настроек маршрута федерации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Для задания назначения маршрута Федерации сайта необходимо сначала включить федерацию на пограничном сервере или в пуле пограничного сервера. Если на пограничном сервере или в пуле не включена Федерация, параметры назначения маршрутов Федерации для сайта не будут доступны для изменения.
ms.openlocfilehash: 6e68bc7cb2f5a9f04e208dc2f27ce7724aa7e793
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292726"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="627e0-104">Расширитель настроек маршрута федерации</span><span class="sxs-lookup"><span data-stu-id="627e0-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="627e0-105">Для задания назначения маршрута Федерации сайта необходимо сначала включить федерацию на пограничном сервере или в пуле пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="627e0-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="627e0-106">Если на пограничном сервере или в пуле не включена Федерация, параметры назначения маршрутов Федерации для сайта не будут доступны для изменения.</span><span class="sxs-lookup"><span data-stu-id="627e0-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="627e0-107">Если параметр Федерации на пограничном сервере или в пуле настроен, вы можете настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="627e0-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="627e0-108">**Разрешение заданий на маршруте Федерации для всех сайтов** Этот параметр будет применяться ко всем сайтам.</span><span class="sxs-lookup"><span data-stu-id="627e0-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="627e0-109">Убедитесь, что параметр, который вы настраиваете на этом сайте, подходит для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="627e0-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="627e0-110">**Включить федерацию SIP** Выберите этот параметр, чтобы включить маршрут Федерации SIP, а затем выберите режиссер или Граничный пул в качестве маршрута Федерации.</span><span class="sxs-lookup"><span data-stu-id="627e0-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="627e0-111">**Включить федерацию КСМПП** Выберите этот параметр, чтобы включить маршрут Федерации КСМПП, а затем выберите режиссер или Граничный пул в качестве маршрута Федерации.</span><span class="sxs-lookup"><span data-stu-id="627e0-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="627e0-112">Шлюзы и прокси-серверы КСМПП доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="627e0-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="627e0-113">Более подробную информацию вы видите в разделе [перевод КСМПП Федерации](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="627e0-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

