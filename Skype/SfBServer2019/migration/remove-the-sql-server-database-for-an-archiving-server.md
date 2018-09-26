---
title: Удаление базы данных SQL Server для сервера архивации
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После удаления сервера архивирование, вы можете удалить базы данных SQL Server, которые размещены данных пула. Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.
ms.openlocfilehash: c82f718cf86de653f6c1340d38e21e96cbaa150d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027965"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="d368c-104">Удаление базы данных SQL Server для сервера архивации</span><span class="sxs-lookup"><span data-stu-id="d368c-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="d368c-105">После удаления сервера архивирование, вы можете удалить базы данных SQL Server, которые размещены данных пула.</span><span class="sxs-lookup"><span data-stu-id="d368c-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="d368c-106">Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.</span><span class="sxs-lookup"><span data-stu-id="d368c-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="d368c-107">Чтобы удалить базу данных SQL Server, с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="d368c-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="d368c-108">На Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="d368c-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d368c-109">В построителе топологий перейдите к **Общие компоненты** и **Хранилища SQL Server**, щелкните правой кнопкой мыши SQL Server экземпляр связанного с удаленным или измененным пулом сервера архивации и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d368c-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="d368c-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="d368c-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="d368c-111">Для удаления файлов базы данных от SQL Server</span><span class="sxs-lookup"><span data-stu-id="d368c-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="d368c-112">Для удаления базы данных на SQL Server, требуется быть членом группы системных администраторов SQL Server для SQL Server, на котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="d368c-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="d368c-113">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="d368c-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="d368c-114">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d368c-114">At the command line, type the following:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="d368c-115">Где _ \<полное доменное имя\> _ — это полное доменное имя (FQDN) сервера базы данных и _ \<экземпляра\> _ — это именованный экземпляр базы данных (то есть, если один был определен).</span><span class="sxs-lookup"><span data-stu-id="d368c-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="d368c-116">Если командлет **Uninstall-CsDataBase** запрос на подтверждение действия, прочтите сведения и нажмите клавишу Y (или ввод), чтобы продолжить работу, или нажмите клавишу N и нажмите ВВОД, чтобы остановить командлета (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="d368c-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

