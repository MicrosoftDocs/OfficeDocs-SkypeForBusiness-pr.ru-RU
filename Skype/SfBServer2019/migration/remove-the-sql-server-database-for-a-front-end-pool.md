---
title: Удаление базы данных SQL Server для пула переднего плана
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После удаления пула переднего плана или перенастройте пул для использования в другую базу данных, можно удалить базы данных SQL Server, которые размещены данных пула. Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.
ms.openlocfilehash: 65fd0367051e32aa081fa13859632504e1331669
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028609"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="26339-104">Удаление базы данных SQL Server для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="26339-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="26339-105">После удаления пула переднего плана или перенастройте пул для использования в другую базу данных, можно удалить базы данных SQL Server, которые размещены данных пула.</span><span class="sxs-lookup"><span data-stu-id="26339-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="26339-106">Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.</span><span class="sxs-lookup"><span data-stu-id="26339-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="26339-107">Чтобы удалить базу данных SQL Server, с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="26339-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="26339-108">Из Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий и загрузите текущую топологию.</span><span class="sxs-lookup"><span data-stu-id="26339-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="26339-109">В построителе топологий перейдите к **Общие компоненты** и **Хранилища SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанного с удаленным или измененным пулом пула переднего плана и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="26339-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="26339-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="26339-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="26339-111">Для удаления пользователя и приложения базы данных от SQL server</span><span class="sxs-lookup"><span data-stu-id="26339-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="26339-112">Для удаления базы данных на SQL server, требуется быть членом группы системных администраторов SQL Server для SQL server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="26339-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="26339-113">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="26339-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="26339-114">Чтобы удалить базу данных для хранилища пользователей пула, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="26339-114">To remove the database for the pool user store, type:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="26339-115">Где _ \<полное доменное имя\> _ — это полное доменное имя (FQDN) сервера базы данных и _ \<экземпляра\> _ — это именованный экземпляр базы данных (то есть, если один был определен).</span><span class="sxs-lookup"><span data-stu-id="26339-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="26339-116">Чтобы удалить базу данных для хранилища приложений пула, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="26339-116">To remove the database for the pool application store, type:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="26339-117">Где _ \<полное доменное имя\> _ — это полное доменное имя сервера базы данных и _ \<экземпляра\> _ — это именованный экземпляр базы данных (то есть, если один был определен).</span><span class="sxs-lookup"><span data-stu-id="26339-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="26339-118">Если командлет **Uninstall-CsDataBase** запрос на подтверждение действия, прочтите сведения и нажмите клавишу Y (или ввод), чтобы продолжить работу, или нажмите клавишу N и нажмите ВВОД, чтобы остановить командлета (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="26339-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

