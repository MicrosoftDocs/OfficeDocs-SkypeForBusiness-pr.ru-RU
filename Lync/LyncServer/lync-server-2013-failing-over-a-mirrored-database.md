---
title: 'Lync Server 2013: отработка отказа для зеркальной базы данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853dfdd6786b4e30513cb57be219edff8d8c1b9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530976"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="a5027-102">Отработка отказа для зеркальной базы данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5027-102">Failing over a mirrored database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5027-103">_**Последнее изменение темы:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="a5027-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="a5027-p101">Если вы настроили для серверной базы данных синхронизированное зеркальное отображение с ресурсом-свидетелем, отработка отказа выполняется автоматически. Если вы настроили синхронизированное зеркальное отображение без ресурса-свидетеля, то чтобы обеспечить отработку отказа, можно воспользоваться следующими процедурами. С их помощью можно также выполнить отработку отказа баз данных вручную в том случае, если ресурс-свидетель настроен.</span><span class="sxs-lookup"><span data-stu-id="a5027-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="a5027-107">Отработка отказа серверной базы данных</span><span class="sxs-lookup"><span data-stu-id="a5027-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="a5027-108">Перед отработкой отказа определите, какая база данных является основной, а какая — зеркальной, выполнив следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="a5027-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="a5027-109">Если центральное хранилище управления размещено в этом пуле, введите следующий командлет, чтобы определить, какой экземпляр является субъектом и зеркалом для центрального хранилища управления:</span><span class="sxs-lookup"><span data-stu-id="a5027-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="a5027-110">Выполните отработку отказа базы данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5027-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="a5027-111">Если произошел отказ основной базы данных и необходимо переключиться на зеркальную, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a5027-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="a5027-112">Если произошел отказ зеркальной базы данных и необходимо переключиться на основную, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a5027-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="a5027-113">Если в пуле размещается Центральный сервер управления, выполните отработку отказа центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="a5027-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="a5027-114">Если произошел отказ основной базы данных и необходимо переключиться на зеркальную, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a5027-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="a5027-115">Если произошел отказ зеркальной базы данных и необходимо переключиться на основную, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a5027-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

