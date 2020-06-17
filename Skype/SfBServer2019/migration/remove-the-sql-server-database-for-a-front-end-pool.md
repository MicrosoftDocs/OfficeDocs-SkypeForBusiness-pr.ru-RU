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
description: После удаления интерфейсного пула или повторной настройки пула для использования другой базы данных можно удалить базы данных SQL Server, на которых размещены данные пула. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753411"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="a7ef2-104">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="a7ef2-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="a7ef2-105">После удаления интерфейсного пула или повторной настройки пула для использования другой базы данных можно удалить базы данных SQL Server, на которых размещены данные пула.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="a7ef2-106">Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="a7ef2-107">Удаление базы данных SQL Server с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="a7ef2-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="a7ef2-108">На сервере переднего плана Skype для бизнеса Server 2019 откройте построитель топологий и скачайте существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="a7ef2-109">В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным интерфейсным пулом, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="a7ef2-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="a7ef2-111">Удаление баз данных пользователей и приложений из SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7ef2-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="a7ef2-112">Чтобы удалить базы данных на сервере SQL Server, необходимо быть членом группы администраторов SQL Server для сервера SQL Server, на котором удаляются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="a7ef2-113">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a7ef2-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a7ef2-114">Чтобы удалить базу данных для хранилища пользователей пула, введите:</span><span class="sxs-lookup"><span data-stu-id="a7ef2-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="a7ef2-115">Где _\<FQDN\>_ — полное доменное имя сервера базы данных, а _\<instance\>_ — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="a7ef2-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="a7ef2-116">Чтобы удалить базу данных для хранилища приложений пула, введите:</span><span class="sxs-lookup"><span data-stu-id="a7ef2-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="a7ef2-117">Где _\<FQDN\>_ — полное доменное имя сервера базы данных, а _\<instance\>_ — это именованный экземпляр базы данных (то есть, если он определен).</span><span class="sxs-lookup"><span data-stu-id="a7ef2-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="a7ef2-118">Когда командлет **uninstall-CsDataBase** запрашивает подтверждение действий, прочитайте информацию, а затем нажмите клавишу Y (или ввод), чтобы продолжить, или нажмите клавишу N, а затем ВВОД, чтобы остановить командлет (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="a7ef2-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

