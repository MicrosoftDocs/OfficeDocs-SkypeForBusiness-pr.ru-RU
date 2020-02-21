---
title: Удаление внешнего интерфейса пула или сервера Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47aa2edebe202f6ed21d1b802d899faea563feba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="d3fba-102">Удаление внешнего интерфейса пула или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d3fba-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3fba-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d3fba-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d3fba-104">В этом разделе описывается процесс удаления интерфейсного пула или сервера переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d3fba-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="d3fba-105">При удалении пула переднего плана необходимо удалить каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула.</span><span class="sxs-lookup"><span data-stu-id="d3fba-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="d3fba-106">При удалении сервера переднего плана Standard Edition необходимо удалить определение хранилища SQL из построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="d3fba-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="d3fba-107">Удаление пула интерфейсных серверов</span><span class="sxs-lookup"><span data-stu-id="d3fba-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="d3fba-108">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="d3fba-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="d3fba-109">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d3fba-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="d3fba-110">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши интерфейсный пул, который требуется удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d3fba-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="d3fba-111">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3fba-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="d3fba-112">Удаление интерфейсного сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d3fba-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="d3fba-113">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="d3fba-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="d3fba-114">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d3fba-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="d3fba-115">Разверните узел **серверы Standard Edition Standard Edition**, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d3fba-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="d3fba-116">Разверните узел **хранилища SQL**, щелкните правой кнопкой мыши базу данных SQL Server, связанную с сервером переднего плана Standard Edition, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d3fba-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3fba-117">Необходимо удалить определение размещенных баз данных SQL Server с сервера переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d3fba-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="d3fba-118">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3fba-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

