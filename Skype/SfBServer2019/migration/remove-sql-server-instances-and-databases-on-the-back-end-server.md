---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных. Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898742"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="aa973-104">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="aa973-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="aa973-105">Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных.</span><span class="sxs-lookup"><span data-stu-id="aa973-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="aa973-106">Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.</span><span class="sxs-lookup"><span data-stu-id="aa973-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="aa973-107">Чтобы удалить базы данных или экземпляры для архивации сервера или сервера мониторинга, сначала необходимо удалить роли сервера.</span><span class="sxs-lookup"><span data-stu-id="aa973-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="aa973-108">Аналогично удаление экземпляров и баз данных для пула переднего плана, необходимо сначала удалить или повторно настройте зависимые серверной роли.</span><span class="sxs-lookup"><span data-stu-id="aa973-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="aa973-109">Эти процедуры сделать нет различий между выровненные базы данных или отдельных экземпляров для серверов.</span><span class="sxs-lookup"><span data-stu-id="aa973-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="aa973-110">Процедуры не влияет на выровненное размещение баз данных.</span><span class="sxs-lookup"><span data-stu-id="aa973-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="aa973-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="aa973-111">In this section</span></span>

- [<span data-ttu-id="aa973-112">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="aa973-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="aa973-113">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="aa973-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="aa973-114">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="aa973-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

