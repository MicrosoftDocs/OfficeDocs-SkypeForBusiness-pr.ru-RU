---
title: Добавление компьютера переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Укажите полное доменное имя (FQDN) каждого компьютера, который вы хотите добавить в качестве сервера переднего плана в этом пуле. До публикации топологии можно в любой момент обновить полное доменное имя добавленного к списку компьютера или удалить его из пула. После публикации топологии изменение полного доменного имени требует удаления сервера в построителе топологии и добавления нового сервера в пул с новым полным доменным именем. Дополнительные сведения о добавлении пула переднего плана в топологию можно найти в разделе Определение и Настройка пула переднего плана в документации по развертыванию.
ms.openlocfilehash: 7c97a0f1d1b22bd79e1ac234ba419a919b9067b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820871"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="c5693-106">Добавление компьютера переднего плана</span><span class="sxs-lookup"><span data-stu-id="c5693-106">Add Front End Machine</span></span>

<span data-ttu-id="c5693-107">Укажите полное доменное имя (FQDN) каждого компьютера, который вы хотите добавить в качестве сервера переднего плана в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="c5693-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="c5693-108">До публикации топологии можно в любой момент обновить полное доменное имя добавленного к списку компьютера или удалить его из пула.</span><span class="sxs-lookup"><span data-stu-id="c5693-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="c5693-109">После публикации топологии изменение полного доменного имени требует удаления сервера в построителе топологии и добавления нового сервера в пул с новым полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="c5693-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="c5693-110">Дополнительные сведения о добавлении пула переднего плана в топологию можно найти в разделе [Определение и Настройка пула переднего плана](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c5693-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5693-111">Обратите внимание, что построитель топологии показывает, что в пуле может быть до 20 серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c5693-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="c5693-112">Максимально допустимое число серверов — 12.</span><span class="sxs-lookup"><span data-stu-id="c5693-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="c5693-113">Вы можете использовать до 20 серверов статефулл, определенных в структуре, в которых 12 может быть активен и в сети в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="c5693-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


