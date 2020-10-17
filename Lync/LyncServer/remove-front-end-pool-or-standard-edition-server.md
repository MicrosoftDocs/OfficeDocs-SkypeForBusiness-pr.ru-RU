---
title: Удаление пула переднего плана или сервера Standard Edition
description: Удалите интерфейсный пул или сервер Standard Edition.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c878d56b073558f4f4b50f31b6742fd581c80241
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570245"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="639f0-103">Удаление пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="639f0-103">Remove Front End pool or Standard Edition server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="639f0-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="639f0-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="639f0-105">В этом разделе описывается процесс удаления интерфейсного пула или сервера переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="639f0-105">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="639f0-106">При удалении пула переднего плана необходимо удалить каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула.</span><span class="sxs-lookup"><span data-stu-id="639f0-106">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="639f0-107">При удалении сервера переднего плана Standard Edition необходимо удалить определение хранилища SQL из построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="639f0-107">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="639f0-108">Удаление пула интерфейсных серверов</span><span class="sxs-lookup"><span data-stu-id="639f0-108">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="639f0-109">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="639f0-109">Open Topology Builder.</span></span>

2.  <span data-ttu-id="639f0-110">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="639f0-110">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="639f0-111">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши интерфейсный пул, который требуется удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="639f0-111">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="639f0-112">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="639f0-112">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="639f0-113">Удаление интерфейсного сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="639f0-113">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="639f0-114">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="639f0-114">Open Topology Builder.</span></span>

2.  <span data-ttu-id="639f0-115">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="639f0-115">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="639f0-116">Разверните узел **серверы Standard Edition Standard Edition**, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="639f0-116">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="639f0-117">Разверните узел **хранилища SQL**, щелкните правой кнопкой мыши базу данных SQL Server, связанную с сервером переднего плана Standard Edition, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="639f0-117">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="639f0-118">Необходимо удалить определение размещенных баз данных SQL Server с сервера переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="639f0-118">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="639f0-119">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="639f0-119">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

