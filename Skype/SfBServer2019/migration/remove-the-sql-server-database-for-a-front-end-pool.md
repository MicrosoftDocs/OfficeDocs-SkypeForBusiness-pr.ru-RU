---
title: Удаление базы данных SQL Server для пула переднего плана
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
description: После удаления пула переднего уровня или перенастройки пула для использования другой базы данных можно удалить SQL Server баз данных, в которые были велись данные пула. Чтобы удалить определения из построитель топологий, а затем удалить базы данных и файлы журналов с сервера баз данных, используйте следующие процедуры.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753411"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="ceb76-104">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="ceb76-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="ceb76-105">После удаления пула переднего уровня или перенастройки пула для использования другой базы данных можно удалить SQL Server баз данных, в которые были велись данные пула.</span><span class="sxs-lookup"><span data-stu-id="ceb76-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="ceb76-106">Чтобы удалить определения из построитель топологий, а затем удалить базы данных и файлы журналов с сервера баз данных, используйте следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="ceb76-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="ceb76-107">Удаление базы данных SQL Server с помощью построщика топологий</span><span class="sxs-lookup"><span data-stu-id="ceb76-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="ceb76-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span><span class="sxs-lookup"><span data-stu-id="ceb76-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="ceb76-109">В построите топологию перейдите к общим компонентам и SQL Server **Хранилища,** щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным пулом переднего SQL Server, а затем нажмите кнопку  "Удалить". </span><span class="sxs-lookup"><span data-stu-id="ceb76-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="ceb76-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="ceb76-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="ceb76-111">Удаление баз данных пользователей и приложений с SQL сервера</span><span class="sxs-lookup"><span data-stu-id="ceb76-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="ceb76-112">Чтобы удалить базы данных на сервере SQL, необходимо быть членом группы SQL Server sysadmins для сервера SQL, на котором удаляются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="ceb76-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="ceb76-113">Откройте Skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ceb76-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ceb76-114">Чтобы удалить базу данных для хранилища пользователей пула, введите:</span><span class="sxs-lookup"><span data-stu-id="ceb76-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="ceb76-115">Где находится полное доменное имя сервера базы данных и именуется экземпляр базы данных  _\<FQDN\>_  _\<instance\>_ (то есть, если он был определен).</span><span class="sxs-lookup"><span data-stu-id="ceb76-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="ceb76-116">Чтобы удалить базу данных для хранилища приложений пула, введите:</span><span class="sxs-lookup"><span data-stu-id="ceb76-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="ceb76-117">Где находится имя FQDN сервера базы данных и именоваемого экземпляра базы данных  _\<FQDN\>_  _\<instance\>_ (то есть, если он был определен).</span><span class="sxs-lookup"><span data-stu-id="ceb76-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="ceb76-118">Когда  вам будет предложено подтвердить действия, ознакомьтесь с информацией, нажмите Y (или ВВОД), чтобы продолжить, или нажмите кнопку N, а затем введите, если вы хотите остановить его (если есть ошибки).</span><span class="sxs-lookup"><span data-stu-id="ceb76-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

