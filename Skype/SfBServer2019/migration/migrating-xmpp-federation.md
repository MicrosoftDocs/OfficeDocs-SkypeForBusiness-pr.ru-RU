---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Предыдущие версии предоставляли шлюз расширенных сообщений и протоколов присутствия (КСМПП), который можно развернуть как отдельную роль сервера, чтобы включить федерацию с КСМПП развертываниями. Функция КСМПП больше не доступна _Амп_ нерекомендуемой в Skype для бизнеса Server 2019. Если вы хотите продолжить работу с функциями КСМПП, которые могут быть доступны в среде коекситенце с устаревшей версией (Skype для бизнеса Server 2015 или Lync Server 2013). Функции КСМПП устанавливаются в двух частях: в качестве прокси-сервера КСМПП, который работает на пограничном пограничного сервера, и шлюз КСМПП, который работает на устаревшем серверном интерфейсе.'
ms.openlocfilehash: fd2b51af84133e28e9a4de035333b1a282d71d38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298192"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="3a19f-106">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="3a19f-106">Migrating XMPP federation</span></span>

<span data-ttu-id="3a19f-107">Предыдущие версии предоставляли шлюз расширенных сообщений и протоколов присутствия (КСМПП), который можно развернуть как отдельную роль сервера, чтобы включить федерацию с КСМПП развертываниями.</span><span class="sxs-lookup"><span data-stu-id="3a19f-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="3a19f-108">Функция КСМПП больше не доступна и признана устаревшей в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3a19f-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="3a19f-109">Если вы хотите продолжить работу с функцией КСМПП, это можно сделать в среде сосуществования с устаревшей версией (Skype для бизнеса Server 2015 или Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="3a19f-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="3a19f-110">Функции КСМПП устанавливаются в двух частях: в качестве прокси-сервера КСМПП, который работает на пограничном пограничного сервера, и шлюз КСМПП, который работает на устаревшем серверном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="3a19f-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="3a19f-111">С точки зрения миграции пользователи, которые хотят получить доступ к функции КСМПП, должны оставаться на устаревшем сервере и не должны переноситься в пул Skype для бизнеса Server 2019, но продолжать использовать устаревший шлюз КСМПП.</span><span class="sxs-lookup"><span data-stu-id="3a19f-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="3a19f-112">Это возможно только в том случае, если для федеративного партнера КСМПП задано значение в Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a19f-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="3a19f-113">Если вы хотите продолжить работу КСМПП, не следует переносить старый сервер пограничного сервера в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3a19f-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="3a19f-114">Тем не менее, вы можете сосуществование устаревшего пограничного сервера (с прокси КСМПП) и пограничного сервера Skype для бизнеса 2019.</span><span class="sxs-lookup"><span data-stu-id="3a19f-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

