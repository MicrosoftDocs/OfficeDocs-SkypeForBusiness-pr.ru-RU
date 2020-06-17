---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Предыдущие версии предоставил шлюз XMPP (Extensible Messaging and Presence Protocol), который можно развернуть в виде отдельной роли сервера, чтобы разрешить федерацию с развертываниями XMPP. Функции XMPP больше недоступны & нерекомендуемым в Skype для бизнеса Server 2019. Если вы хотите продолжить работу с XMPP, который может быть доступен в среде коекситенце с устаревшей версией (Skype для бизнеса Server 2015 или Lync Server 2013). Функции XMPP устанавливаются в виде прокси-сервера XMPP, работающего на пограничном пограничном сервере, и шлюза XMPP, работающего на сервере переднего плана прежних версий.
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752651"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="bb8cc-106">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="bb8cc-106">Migrating XMPP federation</span></span>

<span data-ttu-id="bb8cc-107">Предыдущие версии предоставил шлюз XMPP (Extensible Messaging and Presence Protocol), который можно развернуть в виде отдельной роли сервера, чтобы разрешить федерацию с развертываниями XMPP.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="bb8cc-108">Функции XMPP больше недоступны и не рекомендуются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="bb8cc-109">Если вы хотите продолжить работу с XMPP, вы можете сделать это в среде сосуществования с устаревшей версией (Skype для бизнеса Server 2015 или Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="bb8cc-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="bb8cc-110">Функции XMPP устанавливаются в виде прокси-сервера XMPP, работающего на пограничном пограничном сервере, и шлюза XMPP, работающего на сервере переднего плана прежних версий.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="bb8cc-111">С точки зрения миграции пользователи, которые хотят получить доступ к функции XMPP, останутся на устаревшем сервере и не должны быть перемещены в пул Skype для бизнеса Server 2019, но продолжают использовать устаревший шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="bb8cc-112">Это возможно только в том случае, если федеративный партнер XMPP настроен в Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="bb8cc-113">Не следует переносить устаревший пограничный сервер в Skype для бизнеса Server 2019, если вы хотите продолжить работу с XMPP.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="bb8cc-114">Тем не менее, можно сосуществование устаревшего пограничного сервера (с прокси-сервером XMPP) и сервера пограничного сервера Skype для бизнеса 2019.</span><span class="sxs-lookup"><span data-stu-id="bb8cc-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

