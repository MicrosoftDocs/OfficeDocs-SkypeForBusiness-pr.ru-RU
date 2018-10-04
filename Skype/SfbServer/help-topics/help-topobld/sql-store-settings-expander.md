---
title: Расширитель параметров хранилища SQL
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Чтобы изменить свойства базы данных SQL Server, необходимо изменить экземпляр базы данных SQL Server. Диалоговое окно Изменение свойств нельзя использовать для выполнения задач, таких как база данных сервера архивации перемещается с одного компьютера на другой. Кроме того нельзя использовать диалоговое окно Изменение свойств для изменения экземпляра SQL Server, в котором размещается центральное хранилище управления.
ms.openlocfilehash: 7b2c442208afc0cd5d18b6171a0829ecae3e7ab1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373992"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="8825c-105">Расширитель параметров хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="8825c-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="8825c-106">Чтобы изменить свойства базы данных SQL Server, необходимо изменить экземпляр базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8825c-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="8825c-107">Диалоговое окно **Изменение свойств** нельзя использовать для выполнения задач, таких как база данных сервера архивации перемещается с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="8825c-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="8825c-108">Кроме того нельзя использовать диалоговое окно **Изменение свойств** для изменения экземпляра SQL Server, в котором размещается центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="8825c-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="8825c-109">Изменение свойств базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="8825c-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="8825c-110">Чтобы изменить экземпляр SQL Server, используемый любой базы данных, отличный от центрального хранилища управления, выполните следующую процедуру в построителе топологии:</span><span class="sxs-lookup"><span data-stu-id="8825c-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="8825c-111">Изменение экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="8825c-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="8825c-112">Выберите нужную базу данных в узле **хранит SQL** и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="8825c-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="8825c-113">В диалоговом окне **Изменение свойств** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8825c-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="8825c-114">Чтобы использовать экземпляр SQL Server по умолчанию, выберите **Экземпляр по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8825c-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="8825c-115">Чтобы использовать именованный экземпляр базы данных, выберите **Именованный экземпляр**, введите имя экземпляра в текстовом поле и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8825c-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="8825c-116">Необходимо ввести только имя экземпляра (например, ArchivingInstance), а не всю путь SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8825c-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="8825c-117">При работе в диалоговом окне **Изменение свойств** Topology Builder будет не убедитесь, что экземпляр базы данных, который был введен допустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8825c-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="8825c-118">Например если вы случайно typeArchivingInstanec как имя экземпляра и затем нажмите **кнопку ОК**, Topology Builder будет принимать этот недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8825c-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="8825c-119">Перед публикацией данной топологии необходимо исправить этой ошибки: Если не удается найти экземпляр SQL Server, Topology Builder не создаст этот экземпляр для вас.</span><span class="sxs-lookup"><span data-stu-id="8825c-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

