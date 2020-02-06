---
title: Удаление базы данных SQL Server для пула переднего плана
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После удаления пула переднего плана или повторной настройки пула для использования другой базы данных вы можете удалить базы данных SQL Server, на которых размещены данные пула. Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.
ms.openlocfilehash: 8644760f9f3a18f737fcccd80e20eb091efe2f4b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812857"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="f5d7d-104">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="f5d7d-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="f5d7d-105">После удаления пула переднего плана или повторной настройки пула для использования другой базы данных вы можете удалить базы данных SQL Server, на которых размещены данные пула.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="f5d7d-106">Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="f5d7d-107">Удаление базы данных SQL Server с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="f5d7d-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="f5d7d-108">На сервере переднего плана Skype для бизнеса Server 2019 откройте "Построитель топологии" и скачайте существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="f5d7d-109">В построителе топологии выберите **Общие компоненты** , а затем — **хранилище SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным пулом переднего плана, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="f5d7d-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="f5d7d-111">Удаление баз данных пользователей и приложений из SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5d7d-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="f5d7d-112">Для удаления баз данных на сервере SQL Server необходимо быть членом группы "Администраторы SQL Server" для сервера SQL Server, на котором нужно удалить файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="f5d7d-113">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f5d7d-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="f5d7d-114">Чтобы удалить базу данных из хранилища пользователей пула, введите:</span><span class="sxs-lookup"><span data-stu-id="f5d7d-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="f5d7d-115">Где _ \<FQDN\> _ — полное доменное имя сервера базы данных, а _ \<экземпляр\> _ — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="f5d7d-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="f5d7d-116">Чтобы удалить базу данных из хранилища приложений пула, введите:</span><span class="sxs-lookup"><span data-stu-id="f5d7d-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="f5d7d-117">Где _ \<FQDN\> _ — полное доменное имя сервера базы данных, _ \<а\> экземпляр_ — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="f5d7d-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="f5d7d-118">Когда командлет **uninstall-ксдатабасе** предложит вам подтвердить действия, прочтите информацию, а затем нажмите клавишу Y (или ввод), чтобы продолжить, или нажмите клавишу N, а затем ВВОД, если вы хотите остановить командлет (если есть ошибки).</span><span class="sxs-lookup"><span data-stu-id="f5d7d-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

