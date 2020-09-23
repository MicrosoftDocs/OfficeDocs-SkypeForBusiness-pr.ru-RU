---
title: Создание базы данных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Построитель топологий предоставляет способ установки баз данных в хранилище SQL Server. При установке баз данных с помощью построителя топологий приложение считывает данные из топологии и затем устанавливает необходимые базы данных на указанном компьютере SQL Server или в кластере SQL Server. Это единственный тип установки базы данных, доступный в построителе топологий. Если необходимо установить определенную базу данных на определенном компьютере или при необходимости установить размещенную базу данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет Install – CsDatabase.
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219510"
---
# <a name="create-database"></a><span data-ttu-id="c6f57-106">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="c6f57-106">Create Database</span></span>
 
<span data-ttu-id="c6f57-107">Построитель топологий предоставляет способ установки баз данных в хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6f57-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="c6f57-108">При установке баз данных с помощью построителя топологий приложение считывает данные из топологии и затем устанавливает необходимые базы данных на указанном компьютере SQL Server или в кластере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6f57-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="c6f57-109">Это единственный тип установки базы данных, доступный в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="c6f57-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="c6f57-110">Если необходимо установить определенную базу данных на определенном компьютере или при необходимости установить размещенную базу данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет [Install – CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c6f57-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="c6f57-111">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="c6f57-111">Creating a Database</span></span>

1. <span data-ttu-id="c6f57-112">Выберите узел Skype для бизнеса Server 2015 и нажмите кнопку **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="c6f57-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="c6f57-113">В диалоговом окне **Установка баз данных** на странице **Создание базы данных** выберите полное доменное имя хранилища SQL Server, в котором будут создаваться новые базы данных.</span><span class="sxs-lookup"><span data-stu-id="c6f57-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="c6f57-p103">Щелкните пункт **Дополнительно**. В диалоговом окне **Выбор расположения файла базы данных** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="c6f57-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="c6f57-p104">**Автоматически определять местоположение файла базы данных**. Если выбрать этот параметр, построитель топологий использует встроенный алгоритм для выбора размещения хранилища журналов и файлов данных базы данных.</span><span class="sxs-lookup"><span data-stu-id="c6f57-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="c6f57-118">**Использовать параметры по умолчанию экземпляра SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c6f57-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="c6f57-119">Если выбрать этот параметр, встроенный алгоритм не используется для выбора мест хранения для журналов баз данных и файлов данных.</span><span class="sxs-lookup"><span data-stu-id="c6f57-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="c6f57-120">Файлы журнала и данных хранятся в расположениях, заданных путем параметров SQL Server по умолчанию (эти пути должны быть настроены администратором SQL Server дополнительно).</span><span class="sxs-lookup"><span data-stu-id="c6f57-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="c6f57-121">Файлы данных будут храниться в папке файлов данных SQL Server по умолчанию, в то время как файлы журналов сохраняются в папке файлов журналов SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c6f57-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="c6f57-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6f57-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="c6f57-123">На странице **Создание базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c6f57-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="c6f57-124">На странице **Создание базы данных завершено** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c6f57-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

