---
title: Создание базы данных
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Topology Builder предоставляет способ установки баз данных для хранилища SQL Server. При установке баз данных с помощью построителя топологий приложение считывает данные из топологии и затем устанавливает необходимых баз данных на указанном компьютере с SQL Server или кластера SQL Server. С помощью построителя топологий можно устанавливать базы данных только таким способом. Если требуется установить определенную базу данных на определенном компьютере или необходимо установить выровненных баз данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет Install-CsDatabase вместо этого.
ms.openlocfilehash: 648dca60cd89cc9eeec7f4787b6464f716fdcee6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371522"
---
# <a name="create-database"></a><span data-ttu-id="f5d94-106">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="f5d94-106">Create Database</span></span>
 
<span data-ttu-id="f5d94-107">Topology Builder предоставляет способ установки баз данных для хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f5d94-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="f5d94-108">При установке баз данных с помощью построителя топологий приложение считывает данные из топологии и затем устанавливает необходимых баз данных на указанном компьютере с SQL Server или кластера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f5d94-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="f5d94-109">С помощью построителя топологий можно устанавливать базы данных только таким способом.</span><span class="sxs-lookup"><span data-stu-id="f5d94-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="f5d94-110">Если требуется установить определенную базу данных на определенном компьютере или необходимо установить выровненных баз данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f5d94-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="f5d94-111">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="f5d94-111">Creating a Database</span></span>

1. <span data-ttu-id="f5d94-112">Нажмите кнопку Скайп для узла Business Server и нажмите кнопку **Установка базы данных**.</span><span class="sxs-lookup"><span data-stu-id="f5d94-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="f5d94-113">В диалоговом окне **Установка баз данных** на странице **Создание базы данных** выберите полное доменное имя (FQDN) хранилища SQL Server, где будут создаваться новые базы данных.</span><span class="sxs-lookup"><span data-stu-id="f5d94-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="f5d94-p103">Нажмите кнопку **Дополнительно**. В диалоговом окне **Выбор расположения файла базы данных** выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="f5d94-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="f5d94-p104">**Автоматически определять местоположение файла базы данных**. Если выбран этот режим, место хранения журналов базы данных и файлов данных выбирается по алгоритму, встроенному в построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="f5d94-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="f5d94-118">**Использовать параметры по умолчанию экземпляра SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f5d94-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="f5d94-119">Если выбран этот режим, при определении места хранения журналов базы данных и файлов данных не применяется встроенный алгоритм.</span><span class="sxs-lookup"><span data-stu-id="f5d94-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="f5d94-120">Вместо этого файлы журналов и данных хранятся в указанных папках указанного путем в SQL Server по умолчанию (эти пути должен быть настроен в расширенного администратором сервера SQL Server).</span><span class="sxs-lookup"><span data-stu-id="f5d94-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="f5d94-121">Файлы данных хранятся в папке файлов данных SQL Server по умолчанию, а файлы журналов — в папке файлов журналов SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5d94-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="f5d94-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5d94-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="f5d94-123">На странице **Создание базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f5d94-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="f5d94-124">На странице **Создание базы данных завершено** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f5d94-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

