---
title: Удаление экземпляров SQL Server и баз данных на фоновый сервер
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных. Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027881"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="86688-104">Удаление экземпляров SQL Server и баз данных на фоновый сервер</span><span class="sxs-lookup"><span data-stu-id="86688-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="86688-105">Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных.</span><span class="sxs-lookup"><span data-stu-id="86688-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="86688-106">Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.</span><span class="sxs-lookup"><span data-stu-id="86688-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="86688-107">Чтобы удалить базы данных или экземпляры для архивации сервера или сервера мониторинга, сначала необходимо удалить роли сервера.</span><span class="sxs-lookup"><span data-stu-id="86688-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="86688-108">Аналогично удаление экземпляров и баз данных для пула переднего плана, необходимо сначала удалить или повторно настройте зависимые серверной роли.</span><span class="sxs-lookup"><span data-stu-id="86688-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="86688-109">Эти процедуры сделать нет различий между выровненные базы данных или отдельных экземпляров для серверов.</span><span class="sxs-lookup"><span data-stu-id="86688-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="86688-110">Процедуры не влияет на выровненное размещение баз данных.</span><span class="sxs-lookup"><span data-stu-id="86688-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="86688-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="86688-111">In this section</span></span>

- [<span data-ttu-id="86688-112">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="86688-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="86688-113">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="86688-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="86688-114">Удаление базы данных SQL Server для сервера архивации</span><span class="sxs-lookup"><span data-stu-id="86688-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

