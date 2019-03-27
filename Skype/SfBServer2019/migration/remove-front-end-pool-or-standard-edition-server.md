---
title: Удаление пула переднего плана или сервера Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этом разделе описывается процесс удаления пула переднего плана или сервера Standard Edition переднего плана. При удалении пула переднего плана, удалите каждого сервера переднего плана, к которому относится к пулу как часть процесса удаления пула. При удалении Standard Edition Front End Server, необходимо удалить определение хранилища SQL в построителе топологий.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872719"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="59f52-105">Удаление пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="59f52-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="59f52-106">В этой статье описывается процесс удаления пула переднего плана или сервера Standard Edition переднего плана.</span><span class="sxs-lookup"><span data-stu-id="59f52-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="59f52-107">При удалении пула переднего плана, удалите каждого сервера переднего плана, к которому относится к пулу как часть процесса удаления пула.</span><span class="sxs-lookup"><span data-stu-id="59f52-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="59f52-108">При удалении Standard Edition Front End Server, необходимо удалить определение хранилища SQL в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="59f52-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="59f52-109">Для удаления пула серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="59f52-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="59f52-110">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="59f52-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="59f52-111">Перейдите к узлу прежних версий.</span><span class="sxs-lookup"><span data-stu-id="59f52-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="59f52-112">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши пул переднего плана, который требуется удалить и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="59f52-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="59f52-113">Опубликуйте топологию, проверьте состояние репликации и запустите мастер развертывания прежних версий.</span><span class="sxs-lookup"><span data-stu-id="59f52-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="59f52-114">Удаление сервера переднего плана Standard Edition</span><span class="sxs-lookup"><span data-stu-id="59f52-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="59f52-115">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="59f52-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="59f52-116">Перейдите к узлу устанавливает прежних версий.</span><span class="sxs-lookup"><span data-stu-id="59f52-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="59f52-117">Разверните узел **серверы Standard Edition Front End**, щелкните правой кнопкой мыши сервер переднего плана, который требуется удалить и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="59f52-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="59f52-118">Разверните узел **сохраняет SQL**, щелкните правой кнопкой мыши базу данных SQL Server, который связан с сервером переднего плана выпуска Standard и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="59f52-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59f52-119">Необходимо удалить определение выровненных баз данных SQL Server с Standard Edition сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="59f52-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="59f52-120">Опубликуйте топологию, проверьте состояние репликации и запустите мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="59f52-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

