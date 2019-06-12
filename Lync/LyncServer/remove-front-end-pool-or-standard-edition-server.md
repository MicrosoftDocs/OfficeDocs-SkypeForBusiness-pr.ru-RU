---
title: Удаление пула переднего плана или сервера Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="8bfac-102">Удаление пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8bfac-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bfac-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="8bfac-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="8bfac-104">В этой статье описано, как удалить интерфейс переднего плана или сервер стандартного выпуска Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8bfac-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="8bfac-105">При удалении пула переднего плана удаляется каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула.</span><span class="sxs-lookup"><span data-stu-id="8bfac-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="8bfac-106">При удалении стандартного внешнего сервера выпусков необходимо удалить определение хранилища SQL из построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="8bfac-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="8bfac-107">Удаление пула серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="8bfac-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="8bfac-108">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="8bfac-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="8bfac-109">Перейдите на узел Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8bfac-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="8bfac-110">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши пул переднего плана, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8bfac-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="8bfac-111">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bfac-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="8bfac-112">Удаление стандартного внешнего сервера выпуска</span><span class="sxs-lookup"><span data-stu-id="8bfac-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="8bfac-113">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="8bfac-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="8bfac-114">Перейдите на узел Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8bfac-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="8bfac-115">Разверните узел **стандартные базовые серверы**выпусков, щелкните правой кнопкой мыши сервер переднего плана, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8bfac-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="8bfac-116">Разверните **хранилища SQL**, щелкните правой кнопкой мыши базу данных SQL Server, связанную со стандартным сервером переднего плана выпуска, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8bfac-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8bfac-117">Необходимо удалить определение размещенных баз данных SQL Server на стандартном внешнем сервере выпуска.</span><span class="sxs-lookup"><span data-stu-id="8bfac-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="8bfac-118">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bfac-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

