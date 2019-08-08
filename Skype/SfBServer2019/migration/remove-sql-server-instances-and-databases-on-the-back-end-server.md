---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов, которые зависят от них, или после повторной настройки серверов для использования другой базы данных. Если вы выпустили текущий SQL-сервер или перенастройте текущий сервер таким образом, чтобы они выглядели устаревшими или недоступными, необходимо выполнить описанные в этой статье действия.
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244203"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="2fcb9-104">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="2fcb9-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="2fcb9-105">Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов, которые зависят от них, или после повторной настройки серверов для использования другой базы данных.</span><span class="sxs-lookup"><span data-stu-id="2fcb9-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="2fcb9-106">Если вы выпустили текущий SQL-сервер или перенастройте текущий сервер таким образом, чтобы они выглядели устаревшими или недоступными, необходимо выполнить описанные в этой статье действия.</span><span class="sxs-lookup"><span data-stu-id="2fcb9-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="2fcb9-107">Чтобы удалить базы данных или экземпляры сервера архивирования или сервера мониторинга, необходимо сначала удалить роль сервера.</span><span class="sxs-lookup"><span data-stu-id="2fcb9-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="2fcb9-108">Аналогичным образом для удаления экземпляров или баз данных в пуле переднего плана необходимо сначала удалить или перенастроить роль зависимого сервера.</span><span class="sxs-lookup"><span data-stu-id="2fcb9-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="2fcb9-109">Эти процедуры не различаются между выровненными базами данных и отдельными экземплярами серверов.</span><span class="sxs-lookup"><span data-stu-id="2fcb9-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="2fcb9-110">Расгруппировка баз данных не влияет на эти процедуры.</span><span class="sxs-lookup"><span data-stu-id="2fcb9-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2fcb9-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="2fcb9-111">In this section</span></span>

- [<span data-ttu-id="2fcb9-112">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="2fcb9-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="2fcb9-113">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="2fcb9-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="2fcb9-114">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="2fcb9-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

