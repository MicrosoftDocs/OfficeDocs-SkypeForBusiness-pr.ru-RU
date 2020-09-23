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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Новый сервер сохраняемого чата или пул серверов сохраняемого чата создаются с помощью мастера определения нового пула сохраняемого чата. Выберите Пул из нескольких компьютеров или Пул из одного компьютера. Если выбран один пул компьютеров, а в дальнейшем потребуется пул из нескольких компьютеров, необходимо удалить пул из одного компьютера, а затем определить пул с несколькими компьютерами.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217558"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="2e0b7-105">Определение полного доменного имени сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="2e0b7-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="2e0b7-106">Новый сервер сохраняемого чата или пул серверов сохраняемого чата создаются с помощью мастера **определения нового пула сохраняемого чата** .</span><span class="sxs-lookup"><span data-stu-id="2e0b7-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="2e0b7-107">Выберите **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="2e0b7-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="2e0b7-108">Если выбран один пул компьютеров, а в дальнейшем потребуется пул из нескольких компьютеров, необходимо удалить пул из одного компьютера, а затем определить пул с несколькими компьютерами.</span><span class="sxs-lookup"><span data-stu-id="2e0b7-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="2e0b7-109">Необходимо также определить **полное доменное имя пула** для сервера сохраняемого чата или пула сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="2e0b7-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="2e0b7-110">Полное доменное имя для пула из одного компьютера должно совпадать с полным доменным именем компьютера, включенного в этот пул.</span><span class="sxs-lookup"><span data-stu-id="2e0b7-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="2e0b7-111">Для пула из нескольких компьютеров в качестве полного доменного имени должно использоваться имя, выбранное для представления этого пула и определенное в записи хоста A (и AAAA при использовании IPv6-адреса) DNS.</span><span class="sxs-lookup"><span data-stu-id="2e0b7-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e0b7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2e0b7-112">See also</span></span>

[<span data-ttu-id="2e0b7-113">Планирование сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e0b7-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="2e0b7-114">Добавление сервера сохраняемого чата к топологии Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e0b7-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
