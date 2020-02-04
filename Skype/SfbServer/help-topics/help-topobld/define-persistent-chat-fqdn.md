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
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Вы можете создать новый сервер сохраняемого чата или пул серверов сохраняемого чата с помощью мастера определения нового пула для сохраняемого чата. Выберите Пул из нескольких компьютеров или Пул из одного компьютера. Если выбран пул из одного компьютера, а позднее потребовался пул из нескольких компьютеров, необходимо удалить пул из одного компьютера и затем определить пул из нескольких компьютеров.
ms.openlocfilehash: 0a30073d4b4df28eadaa206778adeb59651b1a48
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684832"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="851a0-105">Определение полного доменного имени сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="851a0-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="851a0-106">Вы можете создать новый сервер сохраняемого чата или пул серверов сохраняемого чата с помощью мастера **определения нового пула для сохраняемого чата** .</span><span class="sxs-lookup"><span data-stu-id="851a0-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="851a0-107">Выберите **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="851a0-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="851a0-108">Если выбран пул из одного компьютера, а позднее потребовался пул из нескольких компьютеров, необходимо удалить пул из одного компьютера и затем определить пул из нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="851a0-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="851a0-109">Кроме того, необходимо определить **полное доменное имя пула** для сервера сохраняемого чата или для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="851a0-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="851a0-110">Полное доменное имя пула из одного компьютера должно совпадать с полным доменным именем компьютера, включенного в этот пул.</span><span class="sxs-lookup"><span data-stu-id="851a0-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="851a0-111">Полное доменное имя пула из нескольких компьютеров должно совпадать с именем, выбранным для представления этого пула и указанным в записи узла A (и AAAA в случае применения протокола IPv6) в службе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="851a0-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="851a0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="851a0-112">See also</span></span>

[<span data-ttu-id="851a0-113">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="851a0-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="851a0-114">Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="851a0-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
