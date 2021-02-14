---
title: Определение полного доменного имени сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Новый сервер сохраняемой беседы или пул серверов сохраняемой беседы создается с помощью мастера определения нового пула сохраняемой беседы. Выберите Пул из нескольких компьютеров или Пул из одного компьютера. Если вы выберете пул из одного компьютера, а затем потребуется пул из нескольких компьютеров, вам потребуется удалить пул из одного компьютера, а затем определить пул из нескольких компьютеров.
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818449"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="99d34-105">Определение полного доменного имени сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="99d34-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="99d34-106">Новый сервер сохраняемой беседы или пул серверов сохраняемой беседы создается с помощью мастера **определения нового пула сохраняемой беседы.**</span><span class="sxs-lookup"><span data-stu-id="99d34-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="99d34-107">Выберите **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="99d34-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="99d34-108">Если вы выберете пул из одного компьютера, а затем потребуется пул из нескольких компьютеров, вам потребуется удалить пул из одного компьютера, а затем определить пул из нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="99d34-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="99d34-109">Необходимо также определить **FQDN** пула для сервера сохраняемой беседы или пула серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="99d34-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="99d34-110">Полное доменное имя для пула из одного компьютера должно совпадать с полным доменным именем компьютера, включенного в этот пул.</span><span class="sxs-lookup"><span data-stu-id="99d34-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="99d34-111">Для пула из нескольких компьютеров в качестве полного доменного имени должно использоваться имя, выбранное для представления этого пула и определенное в записи хоста A (и AAAA при использовании IPv6-адреса) DNS.</span><span class="sxs-lookup"><span data-stu-id="99d34-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99d34-112">См. также</span><span class="sxs-lookup"><span data-stu-id="99d34-112">See also</span></span>

[<span data-ttu-id="99d34-113">Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="99d34-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="99d34-114">Добавление сервера сохраняемой беседы в топологию Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="99d34-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
