---
title: Создание базы данных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Построитель топологии предоставляет способ установки баз данных в хранилище SQL Server. При установке баз данных с помощью Topology Builder приложение считывает данные из топологии и затем устанавливает необходимые базы данных на указанном компьютере SQL Server или кластере SQL Server. С помощью построителя топологий можно устанавливать базы данных только таким способом. Если вам нужно установить определенную базу данных на определенном компьютере или если необходимо установить размещенную базу данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет Install-Ксдатабасе.
ms.openlocfilehash: a4248827b7eba83534b0fdc2dc82dcaa3487e2d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305964"
---
# <a name="create-database"></a><span data-ttu-id="6f6c6-106">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="6f6c6-106">Create Database</span></span>
 
<span data-ttu-id="6f6c6-107">Построитель топологии предоставляет способ установки баз данных в хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="6f6c6-108">При установке баз данных с помощью Topology Builder приложение считывает данные из топологии и затем устанавливает необходимые базы данных на указанном компьютере SQL Server или кластере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="6f6c6-109">С помощью построителя топологий можно устанавливать базы данных только таким способом.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="6f6c6-110">Если вам нужно установить определенную базу данных на определенном компьютере или если необходимо установить размещенную базу данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет [Install-ксдатабасе](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6f6c6-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="6f6c6-111">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="6f6c6-111">Creating a Database</span></span>

1. <span data-ttu-id="6f6c6-112">Щелкните узел 2015 в Skype для бизнеса Server и выберите пункт **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="6f6c6-113">В диалоговом окне **Установка баз** данных на странице **Создание базы данных** выберите полное доменное имя (FQDN) хранилища SQL Server, в котором нужно создать новые базы данных.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="6f6c6-p103">Нажмите кнопку **Дополнительно**. В диалоговом окне **Выбор расположения файла базы данных** выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="6f6c6-p104">**Автоматически определять местоположение файла базы данных**. Если выбран этот режим, место хранения журналов базы данных и файлов данных выбирается по алгоритму, встроенному в построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="6f6c6-118">**Использовать параметры по умолчанию экземпляра SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="6f6c6-119">Если выбран этот режим, при определении места хранения журналов базы данных и файлов данных не применяется встроенный алгоритм.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="6f6c6-120">Файлы журнала и данных хранятся в расположениях, указанных в пути по умолчанию SQL Server (эти пути должны настраиваться администратором SQL Server).</span><span class="sxs-lookup"><span data-stu-id="6f6c6-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="6f6c6-121">Файлы данных хранятся в папке файлов данных SQL Server по умолчанию, а файлы журналов — в папке файлов журналов SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="6f6c6-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="6f6c6-123">На странице **Создание базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="6f6c6-124">На странице **Создание базы данных завершено** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6f6c6-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

