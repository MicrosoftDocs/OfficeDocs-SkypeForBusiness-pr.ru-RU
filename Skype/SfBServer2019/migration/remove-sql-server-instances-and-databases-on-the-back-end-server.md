---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления зависимых от них серверов или после повторной настройки серверов для использования другой базы данных. Необходимо выполнить процедуру, описанную в этом разделе, при отмене текущего сервера SQL Server или перенастройке текущего сервера таким образом, чтобы она отображала устаревшие или недоступные базы данных.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752161"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="a5659-104">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="a5659-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="a5659-105">Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления зависимых от них серверов или после повторной настройки серверов для использования другой базы данных.</span><span class="sxs-lookup"><span data-stu-id="a5659-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="a5659-106">Необходимо выполнить процедуру, описанную в этом разделе, при отмене текущего сервера SQL Server или перенастройке текущего сервера таким образом, чтобы она отображала устаревшие или недоступные базы данных.</span><span class="sxs-lookup"><span data-stu-id="a5659-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="a5659-107">Чтобы удалить базы данных или экземпляры сервера архивирования или сервера мониторинга, сначала необходимо удалить роль сервера.</span><span class="sxs-lookup"><span data-stu-id="a5659-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="a5659-108">Аналогичным образом, чтобы удалить экземпляры или базы данных для интерфейсного пула, необходимо сначала удалить или перенастроить роль зависимого сервера.</span><span class="sxs-lookup"><span data-stu-id="a5659-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="a5659-109">Эти процедуры одинаково подходят для баз данных с выровненным размещением и отдельных экземпляров, относящихся к серверам.</span><span class="sxs-lookup"><span data-stu-id="a5659-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="a5659-110">Выровненное размещение баз данных не влияет на выполнение этих процедур.</span><span class="sxs-lookup"><span data-stu-id="a5659-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a5659-111">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="a5659-111">In this section</span></span>

- [<span data-ttu-id="a5659-112">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="a5659-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="a5659-113">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="a5659-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="a5659-114">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="a5659-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

