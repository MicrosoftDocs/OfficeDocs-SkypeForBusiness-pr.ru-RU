---
title: Создание базы данных
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Построитель топологий предоставляет способ установки баз данных в SQL Server хранилище. При установке баз данных с помощью построитель топологий приложение считыет сведения из топологии, а затем устанавливает необходимые базы данных на указанном компьютере SQL Server или SQL Server кластере. Это единственный тип установки базы данных, доступный в построителе топологий. Если требуется установить определенную базу данных на определенном компьютере или если необходимо установить совмещаемую базу данных, необходимо использовать Windows PowerShell командной строки и командлет Install-CsDatabase командлета.
ms.openlocfilehash: 0ba463ed2995aae2a31890633b7a959cf889837c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833089"
---
# <a name="create-database"></a><span data-ttu-id="8b069-106">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="8b069-106">Create Database</span></span>
 
<span data-ttu-id="8b069-107">Построитель топологий предоставляет способ установки баз данных в SQL Server хранилище.</span><span class="sxs-lookup"><span data-stu-id="8b069-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="8b069-108">При установке баз данных с помощью построитель топологий приложение считыет сведения из топологии, а затем устанавливает необходимые базы данных на указанном компьютере SQL Server или SQL Server кластере.</span><span class="sxs-lookup"><span data-stu-id="8b069-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="8b069-109">Это единственный тип установки базы данных, доступный в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="8b069-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="8b069-110">Если требуется установить определенную базу данных на определенном компьютере или установить совмещаемую базу данных, необходимо использовать интерфейс командной строки Windows PowerShell и командлет [Install-CsDatabase.](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8b069-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="8b069-111">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="8b069-111">Creating a Database</span></span>

1. <span data-ttu-id="8b069-112">Щелкните узел Skype для бизнеса Server 2015 и выберите **"Установить базу данных".**</span><span class="sxs-lookup"><span data-stu-id="8b069-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="8b069-113">В  диалоговом окне "Установка баз данных" на странице "Создание базы данных" выберите полное доменное имя (FQDN) SQL Server хранения, в котором будут созданы новые базы данных. </span><span class="sxs-lookup"><span data-stu-id="8b069-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="8b069-p103">Щелкните пункт **Дополнительно**. В диалоговом окне **Выбор расположения файла базы данных** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="8b069-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="8b069-p104">**Автоматически определять местоположение файла базы данных**. Если выбрать этот параметр, построитель топологий использует встроенный алгоритм для выбора размещения хранилища журналов и файлов данных базы данных.</span><span class="sxs-lookup"><span data-stu-id="8b069-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="8b069-118">**Использовать параметры по умолчанию экземпляра SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8b069-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="8b069-119">Если выбрать этот параметр, встроенный алгоритм не используется для выбора мест хранения для журналов баз данных и файлов данных.</span><span class="sxs-lookup"><span data-stu-id="8b069-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="8b069-120">Вместо этого файлы журналов и данных хранятся в расположениях, указанных в пути SQL Server по умолчанию (эти пути должны быть предварительно настроены администратором SQL Server администратора).</span><span class="sxs-lookup"><span data-stu-id="8b069-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="8b069-121">Файлы данных будут храниться в папке файлов данных SQL Server по умолчанию, в то время как файлы журналов сохраняются в папке файлов журналов SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b069-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="8b069-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b069-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="8b069-123">На странице **Создание базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b069-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="8b069-124">На странице **Создание базы данных завершено** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8b069-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

