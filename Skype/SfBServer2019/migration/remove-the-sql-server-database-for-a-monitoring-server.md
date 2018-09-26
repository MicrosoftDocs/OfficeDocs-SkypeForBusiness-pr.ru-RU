---
title: Удаление базы данных SQL Server для сервера мониторинга
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После удаления сервера мониторинга, можно удалить базы данных SQL Server, которые размещены данных с сервера. Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.
ms.openlocfilehash: 1dc18d520afd67156443ddc2fc22dc838a2aa139
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027979"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="a1499-104">Удаление базы данных SQL Server для сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="a1499-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="a1499-105">После удаления сервера мониторинга, можно удалить базы данных SQL Server, которые размещены данных с сервера.</span><span class="sxs-lookup"><span data-stu-id="a1499-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="a1499-106">Используйте следующую процедуру для удаления определения построителя топологий и удалите файлы базы данных и журналов на сервер базы данных.</span><span class="sxs-lookup"><span data-stu-id="a1499-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="a1499-107">Чтобы удалить базу данных SQL Server, с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="a1499-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="a1499-108">На Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="a1499-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="a1499-109">В построителе топологий перейдите к **Общие компоненты** и **Хранилища SQL Server**, щелкните правой кнопкой мыши SQL Server экземпляр связанного с удаленным или измененным пулом сервера мониторинга и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a1499-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="a1499-110">Опубликуйте топологию и проверьте состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="a1499-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="a1499-111">Для удаления файлов базы данных от SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1499-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="a1499-112">Для удаления базы данных на сервере под управлением SQL Server, требуется быть членом группы системных администраторов SQL Server для сервера SQL Server, в котором удаляются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="a1499-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="a1499-113">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="a1499-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a1499-114">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a1499-114">At the command line, type the following:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="a1499-115">Где _ \<полное доменное имя\> _ — это полное доменное имя (FQDN) сервера базы данных и _ \<экземпляра\> _ — это дополнительный именованный экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="a1499-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="a1499-116">Если командлет **Uninstall-CsDataBase** запрос на подтверждение действия, прочтите сведения и нажмите клавишу Y (или ввод), чтобы продолжить работу, или нажмите клавишу N и нажмите ВВОД, чтобы остановить командлета (при наличии ошибок).</span><span class="sxs-lookup"><span data-stu-id="a1499-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

