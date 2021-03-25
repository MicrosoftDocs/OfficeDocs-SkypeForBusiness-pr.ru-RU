---
title: Добавление компьютера переднего плана
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Укажите полное доменное имя для каждого компьютера, который нужно добавить в качестве сервера переднего плана в этот пул. Добавив компьютер в список, вы можете обновить полное доменное имя или удалить его из пула в любое время до публикации топологии. После публикации топологии для изменения полного доменного имени потребуется сначала удалить сервер в построителе топологий, а затем добавить новый сервер в пул с новым полным доменным именем. Дополнительные сведения о добавлении пула переднего плана в топологию см. в разделе Define and Configure a Front End Pool руководства по развертыванию.
ms.openlocfilehash: f962c41de50bad710edb80422911cb0c3f59943e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118688"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="9e9a2-106">Добавление компьютера переднего плана</span><span class="sxs-lookup"><span data-stu-id="9e9a2-106">Add Front End Machine</span></span>

<span data-ttu-id="9e9a2-107">Укажите полное доменное имя для каждого компьютера, который нужно добавить в качестве сервера переднего плана в этот пул.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="9e9a2-108">Добавив компьютер в список, вы можете обновить полное доменное имя или удалить его из пула в любое время до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="9e9a2-109">После публикации топологии для изменения полного доменного имени потребуется сначала удалить сервер в построителе топологий, а затем добавить новый сервер в пул с новым полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="9e9a2-110">Дополнительные сведения о добавлении пула переднего плана в топологию см. в разделе [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) руководства по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e9a2-111">Обратите внимание, что topology Builder указывает, что в пуле может быть до 20 серверов переднего конца.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="9e9a2-112">Максимальное число поддерживаемых серверов — 12.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="9e9a2-113">В ткани может быть до 20 серверов statefull, из которых 12 одновременно могут быть активными и интерактивными.</span><span class="sxs-lookup"><span data-stu-id="9e9a2-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>