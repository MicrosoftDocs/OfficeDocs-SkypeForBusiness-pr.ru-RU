---
title: Расширитель параметров хранилища SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Чтобы изменить свойства базы данных SQL Server, необходимо изменить SQL Server базы данных. Вы не можете использовать диалоговое окно Изменение свойств для выполнения таких задач, как перемещение базы данных сервера архивации с одного компьютера на другой. Кроме того, нельзя использовать диалоговое окно "Изменение свойств" для изменения экземпляра SQL Server, в котором размещено центральное хранилище управления.
ms.openlocfilehash: d6601349afcc458fc4ba8c3f4feb8810a9c71c42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818099"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="182e0-105">Расширитель параметров хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="182e0-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="182e0-106">Чтобы изменить свойства базы данных SQL Server, необходимо изменить SQL Server базы данных.</span><span class="sxs-lookup"><span data-stu-id="182e0-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="182e0-107">Вы не можете использовать диалоговое окно **Изменение свойств** для выполнения таких задач, как перемещение базы данных сервера архивации с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="182e0-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="182e0-108">Кроме того, нельзя использовать диалоговое **окно** "Изменение свойств" для изменения экземпляра SQL Server, в котором размещено центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="182e0-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="182e0-109">Изменение свойств базы данных SQL Server данных</span><span class="sxs-lookup"><span data-stu-id="182e0-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="182e0-110">Чтобы изменить экземпляр SQL Server, используемый любой базой данных, кроме центрального хранения управления, выполните следующую процедуру в построителье топологий:</span><span class="sxs-lookup"><span data-stu-id="182e0-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="182e0-111">Изменение экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="182e0-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="182e0-112">Выберите соответствующую базу данных в узле **Хранилища SQL**, а затем щелкните элемент **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="182e0-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="182e0-113">В диалоговом окне **Изменение свойств** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="182e0-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="182e0-114">Чтобы использовать экземпляр SQL Server по умолчанию, выберите **"Экземпляр** по умолчанию" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="182e0-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="182e0-115">Чтобы использовать именованный экземпляр базы данных, выберите элемент **Именованный экземпляр**, введите имя экземпляра в текстовом поле и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="182e0-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="182e0-116">Следует ввести только имя экземпляра (например, ArchivingInstance), а не весь SQL Server пути.</span><span class="sxs-lookup"><span data-stu-id="182e0-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="182e0-117">При работе в диалоговом **окне** "Изменение свойств" построитель топологий не будет проверять, является ли введенный экземпляр базы данных допустимым экземпляром.</span><span class="sxs-lookup"><span data-stu-id="182e0-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="182e0-118">Например, если случайно ввести Имя экземпляраArchivingInstanec и нажать кнопку "ОК", построитель топологий примет этот недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="182e0-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="182e0-119">Прежде чем опубликовать эту топологию, необходимо исправить эту ошибку: если SQL Server экземпляра не удается найти, построитель топологий не создаст этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="182e0-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

