---
title: Удаление пула переднего плана или сервера Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описано, как удалить интерфейс переднего плана или сервер стандартного выпуска Standard Edition. При удалении пула переднего плана удаляется каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула. При удалении стандартного внешнего сервера выпусков необходимо удалить определение хранилища SQL из построителя топологии.
ms.openlocfilehash: 57679fb248c9281b79c12be98b7fd5246c9afd38
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244269"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="0078d-105">Удаление пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0078d-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="0078d-106">В этой статье описывается процесс удаления переднего плана или пользовательского интерфейса Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0078d-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="0078d-107">При удалении пула переднего плана удаляется каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула.</span><span class="sxs-lookup"><span data-stu-id="0078d-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="0078d-108">При удалении стандартного внешнего сервера выпусков необходимо удалить определение хранилища SQL из построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="0078d-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="0078d-109">Удаление пула серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="0078d-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="0078d-110">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="0078d-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0078d-111">Перейдите к устаревшему узлу.</span><span class="sxs-lookup"><span data-stu-id="0078d-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="0078d-112">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши пул переднего плана, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0078d-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="0078d-113">Опубликуйте топологию, проверьте состояние репликации, а затем запустите мастер развертывания устаревшего по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="0078d-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="0078d-114">Удаление стандартного внешнего сервера выпуска</span><span class="sxs-lookup"><span data-stu-id="0078d-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="0078d-115">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="0078d-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0078d-116">Перейдите к узлу устаревшие установки.</span><span class="sxs-lookup"><span data-stu-id="0078d-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="0078d-117">Разверните узел **стандартные базовые серверы**выпусков, щелкните правой кнопкой мыши сервер переднего плана, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0078d-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="0078d-118">Разверните **хранилища SQL**, щелкните правой кнопкой мыши базу данных SQL Server, связанную со стандартным сервером переднего плана выпуска, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0078d-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0078d-119">Необходимо удалить определение размещенных баз данных SQL Server на стандартном внешнем сервере выпуска.</span><span class="sxs-lookup"><span data-stu-id="0078d-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="0078d-120">Опубликуйте топологию, проверьте состояние репликации, а затем запустите мастер развертывания по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="0078d-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

