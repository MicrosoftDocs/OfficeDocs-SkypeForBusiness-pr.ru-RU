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
description: 'В предыдущих версиях предоставлялся XMPP-шлюз, который можно было развернуть как отдельную роль сервера для федерации с развертываниями XMPP. Функции XMPP больше не доступны & в Skype для бизнеса Server 2019. Если вы хотите продолжить работу с функциями XMPP, их можно использовать в среде сосуществования с устаревшей версией (Skype для бизнеса Server 2015 или Lync Server 2013). Функциональные возможности XMPP устанавливаются в двух частях: в качестве прокси-сервера XMPP, который выполняется на устаревшем сервере, и шлюза XMPP, который работает на устаревшем сервере переднего сервера.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752651"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="b1162-106">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="b1162-106">Migrating XMPP federation</span></span>

<span data-ttu-id="b1162-107">В предыдущих версиях предоставлялся XMPP-шлюз, который можно было развернуть как отдельную роль сервера для федерации с развертываниями XMPP.</span><span class="sxs-lookup"><span data-stu-id="b1162-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="b1162-108">Функции XMPP больше недоступны и не являются доступными в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1162-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1162-109">Если вы хотите продолжить работу с функциями XMPP, это можно сделать в среде сосуществования с устаревшей версией (Skype для бизнеса Server 2015 или Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="b1162-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="b1162-110">Функциональные возможности XMPP устанавливаются в двух частях: в качестве прокси-сервера XMPP, который выполняется на устаревшем сервере, и шлюза XMPP, который работает на устаревшем сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="b1162-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="b1162-111">С точки зрения миграции пользователи, желающие воспользоваться функцией XMPP, должны оставаться на устаревшем сервере и не должны быть перемещены в пул Skype для бизнеса Server 2019, но продолжают использовать устаревший шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="b1162-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="b1162-112">Это возможно, только если федераированный XMPP-партнер настроен в Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1162-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="b1162-113">Не следует переходить с устаревшего сервера на Skype для бизнеса Server 2019, если вы хотите продолжить работу с функциями XMPP.</span><span class="sxs-lookup"><span data-stu-id="b1162-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="b1162-114">Однако может быть сосуществование устаревшего сервера (с прокси-сервером XMPP) и skype для бизнеса 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="b1162-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

