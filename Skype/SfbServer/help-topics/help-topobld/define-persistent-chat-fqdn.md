---
title: Определение полного доменного имени сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Создание нового сервера сохраняемого чата или пул серверов сохраняемого чата с помощью мастера определения нового пула сохраняемого чата. Выберите Пул из нескольких компьютеров или Пул из одного компьютера. Если выбран пул из одного компьютера, а позднее потребовался пул из нескольких компьютеров, необходимо удалить пул из одного компьютера и затем определить пул из нескольких компьютеров.
ms.openlocfilehash: 5dc548f791abe6aa0b697d69bc30ecf3af54d701
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503937"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="16b41-105">Определение полного доменного имени сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="16b41-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="16b41-106">Создание нового сервера сохраняемого чата или пул серверов сохраняемого чата с помощью мастера **Определения нового пула сохраняемого чата** .</span><span class="sxs-lookup"><span data-stu-id="16b41-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="16b41-107">Выберите **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="16b41-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="16b41-108">Если выбран пул из одного компьютера, а позднее потребовался пул из нескольких компьютеров, необходимо удалить пул из одного компьютера и затем определить пул из нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="16b41-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="16b41-109">Необходимо также определить **Полное доменное имя пула** для сервера сохраняемого чата или пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="16b41-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="16b41-110">Полное доменное имя пула из одного компьютера должно совпадать с полным доменным именем компьютера, включенного в этот пул.</span><span class="sxs-lookup"><span data-stu-id="16b41-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="16b41-111">Полное доменное имя пула из нескольких компьютеров должно совпадать с именем, выбранным для представления этого пула и указанным в записи узла A (и AAAA в случае применения протокола IPv6) в службе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="16b41-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16b41-112">См. также</span><span class="sxs-lookup"><span data-stu-id="16b41-112">See also</span></span>

[<span data-ttu-id="16b41-113">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="16b41-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="16b41-114">Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16b41-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)