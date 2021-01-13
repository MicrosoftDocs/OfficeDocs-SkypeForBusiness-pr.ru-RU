---
title: Добавление компьютера переднего плана
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Укажите полное доменное имя для каждого компьютера, который нужно добавить в качестве сервера переднего плана в этот пул. Добавив компьютер в список, вы можете обновить полное доменное имя или удалить его из пула в любое время до публикации топологии. После публикации топологии для изменения полного доменного имени потребуется сначала удалить сервер в построителе топологий, а затем добавить новый сервер в пул с новым полным доменным именем. Дополнительные сведения о добавлении пула переднего плана в топологию см. в разделе Define and Configure a Front End Pool руководства по развертыванию.
ms.openlocfilehash: 4582aa09527dbc2e663dd6986772b5e88f980a0f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800155"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="888f9-106">Добавление компьютера переднего плана</span><span class="sxs-lookup"><span data-stu-id="888f9-106">Add Front End Machine</span></span>

<span data-ttu-id="888f9-107">Укажите полное доменное имя для каждого компьютера, который нужно добавить в качестве сервера переднего плана в этот пул.</span><span class="sxs-lookup"><span data-stu-id="888f9-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="888f9-108">Добавив компьютер в список, вы можете обновить полное доменное имя или удалить его из пула в любое время до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="888f9-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="888f9-109">После публикации топологии для изменения полного доменного имени потребуется сначала удалить сервер в построителе топологий, а затем добавить новый сервер в пул с новым полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="888f9-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="888f9-110">Дополнительные сведения о добавлении пула переднего плана в топологию см. в разделе [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) руководства по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="888f9-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="888f9-111">Обратите внимание, что построитель топологий указывает, что в пуле может быть до 20 серверов переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="888f9-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="888f9-112">Максимальное поддерживаемые число серверов — 12.</span><span class="sxs-lookup"><span data-stu-id="888f9-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="888f9-113">В структуре может быть определено до 20 серверов с состоянием, из которых 12 могут быть активными и в сети одновременно.</span><span class="sxs-lookup"><span data-stu-id="888f9-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


