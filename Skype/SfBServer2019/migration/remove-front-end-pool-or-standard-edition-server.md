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
description: В этом разделе описывается процесс удаления интерфейсного пула или сервера переднего плана Standard Edition. При удалении пула переднего плана необходимо удалить каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула. При удалении сервера переднего плана Standard Edition необходимо удалить определение хранилища SQL из построителя топологий.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752281"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="bd67d-105">Удаление пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="bd67d-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="bd67d-106">В этой статье описывается процесс удаления интерфейсного пула или сервера переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bd67d-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="bd67d-107">При удалении пула переднего плана необходимо удалить каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула.</span><span class="sxs-lookup"><span data-stu-id="bd67d-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="bd67d-108">При удалении сервера переднего плана Standard Edition необходимо удалить определение хранилища SQL из построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="bd67d-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="bd67d-109">Удаление пула интерфейсных серверов</span><span class="sxs-lookup"><span data-stu-id="bd67d-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="bd67d-110">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="bd67d-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="bd67d-111">Перейдите к устаревшему узлу.</span><span class="sxs-lookup"><span data-stu-id="bd67d-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="bd67d-112">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши интерфейсный пул, который требуется удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bd67d-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="bd67d-113">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания прежних версий.</span><span class="sxs-lookup"><span data-stu-id="bd67d-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="bd67d-114">Удаление интерфейсного сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="bd67d-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="bd67d-115">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="bd67d-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="bd67d-116">Перейдите к узлу установки прежних версий.</span><span class="sxs-lookup"><span data-stu-id="bd67d-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="bd67d-117">Разверните узел **серверы Standard Edition Standard Edition**, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bd67d-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="bd67d-118">Разверните узел **хранилища SQL**, щелкните правой кнопкой мыши базу данных SQL Server, связанную с сервером переднего плана Standard Edition, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bd67d-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bd67d-119">Необходимо удалить определение размещенных баз данных SQL Server с сервера переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bd67d-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="bd67d-120">Опубликуйте топологию, проверьте состояние репликации, а затем запустите мастер развертывания по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="bd67d-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

