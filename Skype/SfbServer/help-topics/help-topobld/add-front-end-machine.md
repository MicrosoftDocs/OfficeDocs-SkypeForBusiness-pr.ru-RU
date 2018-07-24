---
title: Добавление компьютера переднего плана
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Укажите полное доменное имя (FQDN) каждого компьютера, который требуется добавить в качестве сервера переднего плана в этом пуле. До публикации топологии можно в любой момент обновить полное доменное имя добавленного к списку компьютера или удалить его из пула. После публикации топологии для изменения полного доменного ИМЕНИ необходимо удаление сервера в построителе топологий, а затем добавляя новый сервер к пулу с новой полным доменным ИМЕНЕМ. Дополнительные сведения о добавлении пула переднего плана в топологию Просмотрите определение и настройка пула переднего плана в документации по развертыванию.
ms.openlocfilehash: ff12350f2c8ce7527fa619145fd03956191df936
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974891"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="ad3da-106">Добавление компьютера переднего плана</span><span class="sxs-lookup"><span data-stu-id="ad3da-106">Add Front End Machine</span></span>
 
<span data-ttu-id="ad3da-107">Укажите полное доменное имя (FQDN) каждого компьютера, который требуется добавить в качестве сервера переднего плана в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="ad3da-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="ad3da-108">До публикации топологии можно в любой момент обновить полное доменное имя добавленного к списку компьютера или удалить его из пула.</span><span class="sxs-lookup"><span data-stu-id="ad3da-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="ad3da-109">После публикации топологии для изменения полного доменного ИМЕНИ необходимо удаление сервера в построителе топологий, а затем добавляя новый сервер к пулу с новой полным доменным ИМЕНЕМ.</span><span class="sxs-lookup"><span data-stu-id="ad3da-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="ad3da-110">Дополнительные сведения о добавлении пула переднего плана в топологию в документации по развертыванию показано [Определение и настройка пула переднего плана](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ad3da-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ad3da-111">Обратите внимание на то, что Topology Builder указывает, что может иметь до 20 серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="ad3da-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="ad3da-112">Максимальное поддерживаемое число серверов — 12.</span><span class="sxs-lookup"><span data-stu-id="ad3da-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="ad3da-113">Может иметь до 20 statefull серверов, определенных в структуре, из которых 12 может быть активной и online в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="ad3da-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span> 
  

