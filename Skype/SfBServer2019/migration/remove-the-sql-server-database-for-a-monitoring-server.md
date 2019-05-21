---
title: Удаление базы данных SQL Server для сервера мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После удаления сервера мониторинга вы можете удалить базы данных SQL Server, на которых размещены данные сервера. Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.
ms.openlocfilehash: 2f4a6feb78adb9daa15cb8d59c2041740e45a19d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301085"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="42578-104">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="42578-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="42578-105">После удаления сервера мониторинга вы можете удалить базы данных SQL Server, на которых размещены данные сервера.</span><span class="sxs-lookup"><span data-stu-id="42578-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="42578-106">Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="42578-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="42578-107">Удаление базы данных SQL Server с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="42578-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="42578-108">На сервере клиентского доступа Skype для бизнеса Server 2019 откройте конфигуратор топологии.</span><span class="sxs-lookup"><span data-stu-id="42578-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="42578-109">В построителе топологии откройте раздел **Общие компоненты** , а затем — **хранилище SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="42578-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="42578-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="42578-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="42578-111">Удаление файлов базы данных из SQL Server</span><span class="sxs-lookup"><span data-stu-id="42578-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="42578-112">Для удаления баз данных на сервере SQL Server необходимо быть членом группы "Администраторы SQL Server" для сервера SQL Server, на котором нужно удалить файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="42578-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="42578-113">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42578-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="42578-114">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42578-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="42578-115">Где _ \<FQDN\> _ — полное доменное имя сервера базы данных, а _ \<экземпляр\> _ — это необязательный именованный экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="42578-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="42578-116">Когда командлет **uninstall-ксдатабасе** предложит вам подтвердить действия, прочтите информацию, а затем нажмите клавишу Y (или ввод), чтобы продолжить, или нажмите клавишу N, а затем ВВОД, если вы хотите остановить командлет (если есть ошибки).</span><span class="sxs-lookup"><span data-stu-id="42578-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

