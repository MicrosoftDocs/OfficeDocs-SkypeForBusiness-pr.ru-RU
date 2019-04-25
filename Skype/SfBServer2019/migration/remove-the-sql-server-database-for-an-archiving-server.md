---
title: Удаление базы данных SQL Server для сервера архивирования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После удаления сервера архивирование, вы можете удалить базы данных SQL Server, которые размещены данных пула. Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231394"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="39420-104">Удаление базы данных SQL Server для сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="39420-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="39420-105">После удаления сервера архивирование, вы можете удалить базы данных SQL Server, которые размещены данных пула.</span><span class="sxs-lookup"><span data-stu-id="39420-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="39420-106">Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.</span><span class="sxs-lookup"><span data-stu-id="39420-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="39420-107">Чтобы удалить базу данных SQL Server, с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="39420-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="39420-108">На Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="39420-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="39420-109">В построителе топологий перейдите к **Общие компоненты** и **Хранилища SQL Server**, щелкните правой кнопкой мыши SQL Server экземпляр связанного с удаленным или измененным пулом сервера архивации и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="39420-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="39420-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="39420-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="39420-111">Для удаления файлов базы данных от SQL Server</span><span class="sxs-lookup"><span data-stu-id="39420-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="39420-112">Для удаления базы данных на SQL Server, требуется быть членом группы системных администраторов SQL Server для SQL Server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="39420-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="39420-113">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="39420-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="39420-114">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39420-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="39420-115">Где _ \<полное доменное имя\> _ — это полное доменное имя (FQDN) сервера базы данных и _ \<экземпляра\> _ — это именованный экземпляр базы данных (то есть, если один был определен).</span><span class="sxs-lookup"><span data-stu-id="39420-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="39420-116">Если командлет **Uninstall-CsDataBase** запрос на подтверждение действия, прочтите сведения и нажмите клавишу Y (или ввод), чтобы продолжить работу, или нажмите клавишу N и нажмите ВВОД, чтобы остановить командлета (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="39420-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

