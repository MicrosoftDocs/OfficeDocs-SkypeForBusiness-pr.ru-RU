---
title: Удаление пула переднего плана или сервера Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этом разделе приводится процедура удаления пула переднего сервера или сервера переднего сервера Standard Edition. При удалении пула переднего сервера в процессе удаления пула удаляется каждый сервер переднего сервера, который принадлежит к пулу. При удалите сервер переднего сервера Standard Edition, необходимо удалить определение SQL store из построитель топологий.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752281"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="3a6ef-105">Удаление пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3a6ef-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="3a6ef-106">В этой статье приводится процедура удаления пула переднего сервера или сервера переднего сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="3a6ef-107">При удалении пула переднего сервера в процессе удаления пула удаляется каждый сервер переднего сервера, который принадлежит к пулу.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="3a6ef-108">При удалите сервер переднего сервера Standard Edition, необходимо удалить определение SQL store из построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="3a6ef-109">Удаление пула интерфейсных серверов</span><span class="sxs-lookup"><span data-stu-id="3a6ef-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="3a6ef-110">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="3a6ef-111">Перейдите к устаревшему узлу.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="3a6ef-112">Раз **развернуть пулы** переднего входа Enterprise Edition, развернуть пул переднего концев, щелкните правой кнопкой мыши пул переднего конца, который нужно удалить, а затем нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="3a6ef-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="3a6ef-113">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите старый мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="3a6ef-114">Удаление интерфейсного сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3a6ef-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="3a6ef-115">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="3a6ef-116">Перейдите к устаревшему узлу установок.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="3a6ef-117">Разйдите серверы переднего сервера **Standard Edition,** щелкните правой кнопкой мыши сервер переднего сервера, который нужно удалить, и выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="3a6ef-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="3a6ef-118">Раз **SQL хранилища,** щелкните правой кнопкой мыши базу данных SQL Server, связанную с сервером переднего SQL Server Standard Edition, а затем нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="3a6ef-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3a6ef-119">Необходимо удалить определение баз данных с SQL Server сервера переднего SQL Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="3a6ef-120">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="3a6ef-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

