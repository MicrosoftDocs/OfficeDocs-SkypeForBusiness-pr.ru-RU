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
description: Базы данных и Microsoft SQL Server удаляются после удаления серверов, которые от них зависят, или после перенастройки серверов для использования другой базы данных. Процедуру, которая выполняется в этом разделе, необходимо выполнить при выходе из эксплуатации текущего SQL Server или перенастройке текущего сервера таким образом, чтобы он преобразовывает базы данных в устаревшие или недоступные.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752161"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="25388-104">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="25388-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="25388-105">Базы данных и Microsoft SQL Server удаляются после удаления серверов, которые от них зависят, или после перенастройки серверов для использования другой базы данных.</span><span class="sxs-lookup"><span data-stu-id="25388-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="25388-106">Процедуру, которая выполняется в этом разделе, необходимо выполнить при выходе из эксплуатации текущего SQL Server или перенастройке текущего сервера таким образом, чтобы он преобразовывает базы данных в устаревшие или недоступные.</span><span class="sxs-lookup"><span data-stu-id="25388-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="25388-107">Чтобы удалить базы данных или экземпляры сервера архива или сервера мониторинга, необходимо сначала удалить роль сервера.</span><span class="sxs-lookup"><span data-stu-id="25388-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="25388-108">Аналогичным образом, чтобы удалить экземпляры или базы данных для пула переднего плана, необходимо сначала удалить или перенастроить зависимую роль сервера.</span><span class="sxs-lookup"><span data-stu-id="25388-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="25388-109">Эти процедуры одинаково подходят для баз данных с выровненным размещением и отдельных экземпляров, относящихся к серверам.</span><span class="sxs-lookup"><span data-stu-id="25388-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="25388-110">Выровненное размещение баз данных не влияет на выполнение этих процедур.</span><span class="sxs-lookup"><span data-stu-id="25388-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="25388-111">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="25388-111">In this section</span></span>

- [<span data-ttu-id="25388-112">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="25388-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="25388-113">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="25388-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="25388-114">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="25388-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

