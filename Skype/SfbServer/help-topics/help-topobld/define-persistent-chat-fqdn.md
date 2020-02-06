---
title: Определение полного доменного имени сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Вы можете создать новый сервер сохраняемого чата или пул серверов сохраняемого чата с помощью мастера определения нового пула для сохраняемого чата. Выберите Пул из нескольких компьютеров или Пул из одного компьютера. Если выбран пул из одного компьютера, а позднее потребовался пул из нескольких компьютеров, необходимо удалить пул из одного компьютера и затем определить пул из нескольких компьютеров.
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820201"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="855b2-105">Определение полного доменного имени сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="855b2-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="855b2-106">Вы можете создать новый сервер сохраняемого чата или пул серверов сохраняемого чата с помощью мастера **определения нового пула для сохраняемого чата** .</span><span class="sxs-lookup"><span data-stu-id="855b2-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="855b2-107">Выберите **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="855b2-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="855b2-108">Если выбран пул из одного компьютера, а позднее потребовался пул из нескольких компьютеров, необходимо удалить пул из одного компьютера и затем определить пул из нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="855b2-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="855b2-109">Кроме того, необходимо определить **полное доменное имя пула** для сервера сохраняемого чата или для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="855b2-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="855b2-110">Полное доменное имя пула из одного компьютера должно совпадать с полным доменным именем компьютера, включенного в этот пул.</span><span class="sxs-lookup"><span data-stu-id="855b2-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="855b2-111">Полное доменное имя пула из нескольких компьютеров должно совпадать с именем, выбранным для представления этого пула и указанным в записи узла A (и AAAA в случае применения протокола IPv6) в службе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="855b2-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="855b2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="855b2-112">See also</span></span>

[<span data-ttu-id="855b2-113">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="855b2-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="855b2-114">Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="855b2-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
