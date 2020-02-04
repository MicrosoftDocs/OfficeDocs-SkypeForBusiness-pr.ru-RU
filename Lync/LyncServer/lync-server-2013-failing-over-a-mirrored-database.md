---
title: 'Lync Server 2013: отработка отказа с использованием зеркальной базы данных'
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
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="8cd43-102">Отработка отказа с использованием зеркальной базы данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cd43-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cd43-103">_**Тема последнего изменения:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="8cd43-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="8cd43-104">Если вы настроили серверную базу данных для использования синхронизированного отражения с следящим сервером, переход на другой ресурс выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="8cd43-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="8cd43-105">Если вы настроили синхронизацию зеркального отображения без следящего сервера, вы можете использовать следующие процедуры для перемещения по резервной копии и восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="8cd43-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="8cd43-106">Вы также можете использовать эти процедуры для перемещения по резервной конфигурации вручную и восстановления баз данных, даже если вы настроили следящий сервер.</span><span class="sxs-lookup"><span data-stu-id="8cd43-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="8cd43-107">Переключение на серверную базу данных</span><span class="sxs-lookup"><span data-stu-id="8cd43-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="8cd43-108">Прежде чем переходить, определите, какая серверная база данных является участником и что является зеркалом, введя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="8cd43-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="8cd43-109">Если хранилище Central Management размещено в этом пуле, введите следующий командлет, чтобы определить, какой из них является основным и зеркалом для центрального хранилища.</span><span class="sxs-lookup"><span data-stu-id="8cd43-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="8cd43-110">Выполнение отработки отказа базы данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8cd43-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="8cd43-111">Если основной сервер завершился сбоем и вы перейдете на зеркало, введите:</span><span class="sxs-lookup"><span data-stu-id="8cd43-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="8cd43-112">Если зеркало завершилось сбоем и вы перейдете на основной, введите:</span><span class="sxs-lookup"><span data-stu-id="8cd43-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="8cd43-113">Если в пуле размещается Центральный сервер управления, выполните отработку отказа центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="8cd43-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="8cd43-114">Если основной сервер завершился сбоем и вы перейдете на зеркало, введите:</span><span class="sxs-lookup"><span data-stu-id="8cd43-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="8cd43-115">Если зеркало завершилось сбоем и вы перейдете на основной, введите:</span><span class="sxs-lookup"><span data-stu-id="8cd43-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

