---
title: Развертывание панели мониторинга качества вызовов для Skype для бизнес-сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: Сводка. Сведения о процессе развертывания панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114115"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="f15b1-104">Развертывание панели мониторинга качества вызовов для Skype для бизнес-сервера</span><span class="sxs-lookup"><span data-stu-id="f15b1-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="f15b1-105">**Сводка:** Узнайте о процессе развертывания панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="f15b1-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="f15b1-106">Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f15b1-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="f15b1-107">Обзор развертывания</span><span class="sxs-lookup"><span data-stu-id="f15b1-107">Deployment Overview</span></span>

<span data-ttu-id="f15b1-108">Панель мониторинга качества вызовов (CQD) состоит из трех основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="f15b1-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="f15b1-109">**База данных** архива, в которой реплицированы и хранятся данные Качества работы (QoE).</span><span class="sxs-lookup"><span data-stu-id="f15b1-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="f15b1-110">**Cube,** где данные из базы данных архива QoE агрегируются для оптимизированного и быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="f15b1-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="f15b1-111">**Портал,** где пользователи могут легко запрашивать и визуализировать данные QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Компоненты CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="f15b1-113">Процесс настройки архива QoE включает создание базы данных архива QoE, развертывание процедуры хранения SQL Server, которая будет перемещать данные из базы данных исходных показателей QoE в базу данных архива QoE, а также настройка задания агента SQL Server для выполнения сохраненной процедуры на регулярной основе.</span><span class="sxs-lookup"><span data-stu-id="f15b1-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="f15b1-114">Развертывание Cube получает от пользователя сведения о расположении архива QoE, развертывает куб и настраивает SQL Server агента, который будет обновлять куб с регулярным интервалом.</span><span class="sxs-lookup"><span data-stu-id="f15b1-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="f15b1-115">Установка портала создает базу данных репозиториев, которая хранит сопоставление пользователей CQD с отчетами и запросами каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f15b1-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="f15b1-116">Затем создается веб-приложение IIS, которое является панелью мониторинга, на которой пользователи могут видеть заранее определенный набор отчетов, а также настраивать и создавать собственные запросы для визуализации данных из куба.</span><span class="sxs-lookup"><span data-stu-id="f15b1-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="f15b1-117">Установка портала создает два дополнительных веб-приложения, которые предоставляет пользователям API программный доступ к репозиторию и кубу.</span><span class="sxs-lookup"><span data-stu-id="f15b1-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="f15b1-118">(Эти API также используются внутренне панелью мониторинга.)</span><span class="sxs-lookup"><span data-stu-id="f15b1-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="f15b1-119">**Этап**</span><span class="sxs-lookup"><span data-stu-id="f15b1-119">**Phase**</span></span>|<span data-ttu-id="f15b1-120">**Действия**</span><span class="sxs-lookup"><span data-stu-id="f15b1-120">**Steps**</span></span>|<span data-ttu-id="f15b1-121">**Роли и членство в группе**</span><span class="sxs-lookup"><span data-stu-id="f15b1-121">**Roles and group membership**</span></span>|<span data-ttu-id="f15b1-122">**Документация**</span><span class="sxs-lookup"><span data-stu-id="f15b1-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f15b1-123">Установка необходимого оборудования и программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f15b1-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="f15b1-124">Определите конфигурацию CQD и выберите SQL Server, из которого выполняется установка.</span><span class="sxs-lookup"><span data-stu-id="f15b1-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="f15b1-125">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="f15b1-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="f15b1-126">Раздел "Требования предварительной установки" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f15b1-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="f15b1-127">Установка CQD.</span><span class="sxs-lookup"><span data-stu-id="f15b1-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="f15b1-128">Запустите MSI после документа развертывания.</span><span class="sxs-lookup"><span data-stu-id="f15b1-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="f15b1-129">Для выполнения установки учетная запись установки должна быть пользователем домена, который является членом группы локальных администраторов и имеет доступ к базе данных показателей QoE на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f15b1-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="f15b1-130">Разделы "Учетные записи и этапы развертывания" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f15b1-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="f15b1-131">Предоставление доступа к пользователю.</span><span class="sxs-lookup"><span data-stu-id="f15b1-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="f15b1-132">Для управления авторизацией пользователя на портале рекомендуется использовать авторизацию URL-адресов, которая была представлена в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="f15b1-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="f15b1-133">Дополнительные сведения см. в [сайте Understanding IIS 7.0 URL-адресов.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="f15b1-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="f15b1-134">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="f15b1-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="f15b1-135">Управление доступом пользователей к разделу Portal в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f15b1-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="f15b1-136">Необязательный. Предостанавлить сведения о сопоставлении подсетей.</span><span class="sxs-lookup"><span data-stu-id="f15b1-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="f15b1-137">Заполнять таблицы сопоставления сети и построения в базе данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="f15b1-138">Учетная запись с записью доступа к базе данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="f15b1-139">Раздел "Сведения о подсетях" в документации пользователя.</span><span class="sxs-lookup"><span data-stu-id="f15b1-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="f15b1-140">Развертывание панели мониторинга качества вызовов предполагает настройку инфраструктуры и установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f15b1-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="f15b1-141">В следующей процедуре описывается процесс.</span><span class="sxs-lookup"><span data-stu-id="f15b1-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="f15b1-142">Действия развертывания</span><span class="sxs-lookup"><span data-stu-id="f15b1-142">Deployment Steps</span></span>

1. <span data-ttu-id="f15b1-143">Скопируйте CallQualityDashboard.msi на машину, на которой должен быть установлен компонент базы данных архива CQD (это машина, SQL Server установлена).</span><span class="sxs-lookup"><span data-stu-id="f15b1-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="f15b1-144">Выполните MSI (Windows будет выполняться с привилегией администратора, делайте это).</span><span class="sxs-lookup"><span data-stu-id="f15b1-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="f15b1-145">Примите EULA.</span><span class="sxs-lookup"><span data-stu-id="f15b1-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="f15b1-146">Выберите папку назначения, в которой будут располагаться файлы, связанные с компонентами панели мониторинга качества вызовов, или принять расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f15b1-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="f15b1-147">Выберите все функции.</span><span class="sxs-lookup"><span data-stu-id="f15b1-147">Select all features.</span></span>
    
6. <span data-ttu-id="f15b1-148">На странице Конфигурация архива QoE предопос.</span><span class="sxs-lookup"><span data-stu-id="f15b1-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="f15b1-149">**Показатели QoE SQL Server:** SQL Server имени экземпляра, где расположенА DB показателей QoE (это будет источник данных).</span><span class="sxs-lookup"><span data-stu-id="f15b1-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="f15b1-150">**Имя архива QoE SQL Server:** Это поле только для чтения и закреплено за полностью квалифицированным доменным именем локальной машины.</span><span class="sxs-lookup"><span data-stu-id="f15b1-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="f15b1-151">Архивная DB может быть установлена только на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f15b1-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="f15b1-152">**QoE Archive SQL Server пример:** Локальное имя SQL Server для создания архивного DB.</span><span class="sxs-lookup"><span data-stu-id="f15b1-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="f15b1-153">Чтобы использовать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="f15b1-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="f15b1-154">Чтобы использовать экземпляр SQL Server имени, укажите имя экземпляра (например, имя после \" ").</span><span class="sxs-lookup"><span data-stu-id="f15b1-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="f15b1-155">**Архивная база данных QoE:** По умолчанию этот параметр имеет значение "Создание новой базы данных".</span><span class="sxs-lookup"><span data-stu-id="f15b1-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="f15b1-156">Так как обновление архива DB не поддерживается, единственным обстоятельством, при котором можно использовать параметр "Использование существующей базы данных", является то, что существующая база данных Архива имеет ту же схему, что и установленная сборка.</span><span class="sxs-lookup"><span data-stu-id="f15b1-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="f15b1-157">**Каталог файлов базы данных:** Путь к размещению файлов базы данных (.mdf и .ldf) для архивного DB.</span><span class="sxs-lookup"><span data-stu-id="f15b1-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="f15b1-158">Это должно быть на диске (HDD2 в рекомендуемой конфигурации оборудования) отдельно от ОС.</span><span class="sxs-lookup"><span data-stu-id="f15b1-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="f15b1-159">Обратите внимание, что так как имена файлов фиксируются в установке, чтобы избежать потенциального конфликта, рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="f15b1-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="f15b1-160">**Используйте несколько разделов:** По умолчанию задано значение "Несколько разделов", для чего требуется выпуск business Intelligence или корпоративный выпуск SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f15b1-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="f15b1-161">В стандартном выпуске выберите параметр "Один раздел".</span><span class="sxs-lookup"><span data-stu-id="f15b1-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="f15b1-162">Обратите внимание, что производительность обработки кубов может повлиять, если используется один раздел.</span><span class="sxs-lookup"><span data-stu-id="f15b1-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f15b1-163">Выбор параметра Use Multiple Partitions нельзя изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="f15b1-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="f15b1-164">Чтобы изменить его, необходимо сначала отменить функцию Cube, а затем переустановить ее с помощью параметра "Изменение" в панели управления.</span><span class="sxs-lookup"><span data-stu-id="f15b1-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="f15b1-165">**Каталог файлов разделов:** Путь к расположению разделов для базы данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="f15b1-166">Это должно быть на диске (HDD3 в рекомендуемой конфигурации оборудования) отдельно от диска ОС и SQL файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="f15b1-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="f15b1-167">Обратите внимание, что так как имена файлов фиксируются в установке, чтобы избежать потенциального конфликта, рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="f15b1-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="f15b1-168">**SQL агента — имя пользователя &amp; Пароль.** Имя и пароль учетной записи службы домена (в маске), которые будут использоваться для запуска шага "Архивные данные QoE" задания SQL Server Agent (который будет запускать сохраненную процедуру для получения данных из QoE Metrics DB в Archive DB, поэтому эта учетная запись должна иметь доступ к QoE Metrics DB, как указано в разделе Учетные записи.</span><span class="sxs-lookup"><span data-stu-id="f15b1-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="f15b1-169">Эта учетная запись также должна иметь вход в архив QoE SQL Server Экземпляр).</span><span class="sxs-lookup"><span data-stu-id="f15b1-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f15b1-170">Учетная запись SQL Server экземпляра, например NT SERVICE\MSSQLSERVER, должна иметь доступ и разрешение к каталогам, которые были даны выше для успешной установки.</span><span class="sxs-lookup"><span data-stu-id="f15b1-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="f15b1-171">Подробные сведения см. [в материале Настройка разрешений файловой системы для доступа к двигателям баз данных](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span><span class="sxs-lookup"><span data-stu-id="f15b1-171">For details, see [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span></span>
  
7. <span data-ttu-id="f15b1-172">Нажав кнопку далее, установщик выполнит необходимые проверки и сообщает, если возникнут какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="f15b1-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="f15b1-173">Когда все необходимые проверки проходят, установщик перейдите на страницу Конфигурация Куба.</span><span class="sxs-lookup"><span data-stu-id="f15b1-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f15b1-174">Если установщик показывает предупреждение о том, что служба агентов SQL Server для экземпляра QoE Archive SQL Server в настоящее время не запущена, установка может продолжиться, но после установки убедитесь, что служба SQL агент запущена и установите тип Запуска автоматическим, чтобы запланированное задание было запущено.</span><span class="sxs-lookup"><span data-stu-id="f15b1-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="f15b1-175">На странице Конфигурация Куба укайте следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="f15b1-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="f15b1-176">**Имя архива QoE SQL Server:** Это поле только для чтения и закреплено за полностью квалифицированным доменным именем локальной машины.</span><span class="sxs-lookup"><span data-stu-id="f15b1-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="f15b1-177">Куб можно установить только из машины с базой данных архива QoE (Примечание.</span><span class="sxs-lookup"><span data-stu-id="f15b1-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="f15b1-178">Куб может быть установлен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f15b1-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="f15b1-179">См. ниже)</span><span class="sxs-lookup"><span data-stu-id="f15b1-179">See below)</span></span>
    
   - <span data-ttu-id="f15b1-180">**QoE Archive SQL Server пример:** SQL Server имени экземпляра, где расположенА DB архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="f15b1-181">Чтобы указать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="f15b1-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="f15b1-182">Чтобы указать SQL Server экземпляра, введите имя экземпляра (например, имя после \" ").</span><span class="sxs-lookup"><span data-stu-id="f15b1-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="f15b1-183">Если для установки был выбран компонент архива QoE, это поле будет предварительно заполнено значением, предоставляемым на странице Конфигурация архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="f15b1-184">**Сервер анализа куба:** SQL Server службы анализа имя экземпляра для создания куба.</span><span class="sxs-lookup"><span data-stu-id="f15b1-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="f15b1-185">Это может быть другая машина, но пользователь установки должен быть членом администраторов сервера целевого SQL Server службы анализа.</span><span class="sxs-lookup"><span data-stu-id="f15b1-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="f15b1-186">Дополнительные сведения о настройке разрешений администратора сервера служб аналитики см. в дополнительных сведениях о разрешениях администратора grant [Server (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span><span class="sxs-lookup"><span data-stu-id="f15b1-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span></span>
  
   - <span data-ttu-id="f15b1-187">**Используйте несколько разделов:** По умолчанию задано значение "Несколько разделов", для чего требуется выпуск business Intelligence или корпоративный выпуск SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f15b1-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="f15b1-188">В стандартном выпуске выберите параметр "Один раздел".</span><span class="sxs-lookup"><span data-stu-id="f15b1-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="f15b1-189">Обратите внимание, что производительность обработки кубов может повлиять, если используется один раздел.</span><span class="sxs-lookup"><span data-stu-id="f15b1-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="f15b1-190">Выбор параметра Use Multiple Partitions нельзя изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="f15b1-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="f15b1-191">Чтобы изменить его, необходимо сначала отменить функцию Cube, а затем переустановить ее с помощью параметра "Изменение" в панели управления.</span><span class="sxs-lookup"><span data-stu-id="f15b1-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="f15b1-192">**Пользователь Cube — имя пользователя &amp; Пароль.** Имя и пароль учетной записи службы домена (в маске), которые будут запускать обработку куба.</span><span class="sxs-lookup"><span data-stu-id="f15b1-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="f15b1-193">Если для установки был выбран компонент архива QoE, это поле будет предварительно заполнено значением, предоставляемым на странице Конфигурация архива для пользователя задания агента SQL агента, но рекомендуется указать другую учетную запись службы домена, чтобы установка предоставила ему наименее необходимые привилегии.</span><span class="sxs-lookup"><span data-stu-id="f15b1-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="f15b1-194">При следующем нажатии на кнопку будет выполнен еще один раунд проверки и будет отчитаться о любой проблеме.</span><span class="sxs-lookup"><span data-stu-id="f15b1-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="f15b1-195">После успешного завершения проверки установщик перейдите на страницу Конфигурация портала.</span><span class="sxs-lookup"><span data-stu-id="f15b1-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="f15b1-196">На странице Конфигурация портала укайте следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="f15b1-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="f15b1-197">**Архив QoE SQL Server:** SQL Server, где расположена база данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="f15b1-198">Обратите внимание, что в отличие от страницы конфигурации архива QoE и страницы конфигурации Куба имя машины не фиксируется и должно быть предоставлено.</span><span class="sxs-lookup"><span data-stu-id="f15b1-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="f15b1-199">Если для установки был выбран компонент архива QoE, это поле будет предварительно заполнено значением, предоставляемым на странице Конфигурация архива QoE.</span><span class="sxs-lookup"><span data-stu-id="f15b1-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="f15b1-200">**Сервер анализа куба:** SQL Server службы анализа имя экземпляра, где расположен куб.</span><span class="sxs-lookup"><span data-stu-id="f15b1-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="f15b1-201">Если для установки был выбран компонент Cube, это поле будет предварительно заполнено значением, предоставляемым на странице Конфигурация Куба.</span><span class="sxs-lookup"><span data-stu-id="f15b1-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="f15b1-202">**Репозиторий SQL Server:** SQL Server имени экземпляра, в котором должна быть создана база данных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="f15b1-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="f15b1-203">Если имя SQL Server экземпляра, на котором расположена база данных архива QoE, было предоставлено ранее в установке (в других компонентах), это поле будет предварительно заполнено именем экземпляра QoE Archive DB SQL Server экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f15b1-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="f15b1-204">Это может быть любой SQL Server экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f15b1-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="f15b1-205">**База данных репозиториев:** По умолчанию установлен параметр "Создание новой базы данных".</span><span class="sxs-lookup"><span data-stu-id="f15b1-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="f15b1-206">Поскольку обновление хранилища DB не поддерживается, единственным обстоятельством, при котором можно использовать параметр "Использование существующей базы данных", является то, что существующая схема хранилища DB имеет ту же схему, что и установленная сборка.</span><span class="sxs-lookup"><span data-stu-id="f15b1-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="f15b1-207">**Пользователь пула приложений IIS — имя пользователя &amp; Пароль.** Учетная запись, которую должен выполнять пул приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="f15b1-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="f15b1-208">При выборе встроенных системных учетных записей поля "Имя пользователя" и "Пароль" будут серыми.</span><span class="sxs-lookup"><span data-stu-id="f15b1-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="f15b1-209">Эти поля будут включены только в том случае, если "Другое" выбрано из окна drop down, чтобы пользователь вошел в сведения учетной записи службы домена.</span><span class="sxs-lookup"><span data-stu-id="f15b1-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="f15b1-210">При нажатии следующего щелчка будет сделан заключительный этап проверки для обеспечения доступности экземпляров SQL Server с помощью предоставленных учетных данных и доступности IIS на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f15b1-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="f15b1-211">После успешного завершения проверки установщик приступит к установке.</span><span class="sxs-lookup"><span data-stu-id="f15b1-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="f15b1-212">После установки, скорее всего, SQL Server агент будет в процессе выполнения начальной нагрузки данных QoE и обработки куба.</span><span class="sxs-lookup"><span data-stu-id="f15b1-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="f15b1-213">В зависимости от количества данных в QoE на портале еще не будут доступны данные для просмотра.</span><span class="sxs-lookup"><span data-stu-id="f15b1-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="f15b1-214">Чтобы проверить состояние нагрузки данных и обработки куба, перейдите к  `http://<machinename>/CQD/#/Health` .</span><span class="sxs-lookup"><span data-stu-id="f15b1-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="f15b1-215">Обратите внимание, что URL-адрес для проверки состояния обработки куба загрузки является конфиденциальным.</span><span class="sxs-lookup"><span data-stu-id="f15b1-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="f15b1-216">Если вы вводите "здоровье", URL-адрес не будет работать.</span><span class="sxs-lookup"><span data-stu-id="f15b1-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="f15b1-217">Необходимо ввести "Здоровье" в конце URL-адреса со столицей H.</span><span class="sxs-lookup"><span data-stu-id="f15b1-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="f15b1-218">Подробные сообщения журнала будут показаны, если включен режим отлаживания.</span><span class="sxs-lookup"><span data-stu-id="f15b1-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="f15b1-219">Чтобы включить режим отлаживания, перейдите к **%SYSTEMDRIVE%\Program Files\Skype for Business 2015 CQD\QoEDataService\web.config** и обновив следующую строку, чтобы значение было заданная **значение True:**</span><span class="sxs-lookup"><span data-stu-id="f15b1-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="f15b1-220">Главная страница портала доступна через  `http://<machinename>/CQD` .</span><span class="sxs-lookup"><span data-stu-id="f15b1-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="f15b1-221">Управление доступом пользователей к порталу</span><span class="sxs-lookup"><span data-stu-id="f15b1-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="f15b1-222">Для управления авторизацией пользователя на портале рекомендуется использовать авторизацию URL-адресов, которая была представлена в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="f15b1-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="f15b1-223">Дополнительные сведения о безопасности IIS см. в ссылке [Understanding IIS 7.0 URL-адресов.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="f15b1-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="f15b1-224">Любой веб-сайт или веб-приложение наследует авторизацию URL-адресов по умолчанию, настроенную для всего IIS, которое обычно является "Разрешить всем пользователям".</span><span class="sxs-lookup"><span data-stu-id="f15b1-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="f15b1-225">Если доступ к порталу должен быть более строгим, администраторы могут предоставлять доступ только определенной группе пользователей, редактирует "Правила авторизации".</span><span class="sxs-lookup"><span data-stu-id="f15b1-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Развертывание правил по качеству вызовов и авторизации в IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="f15b1-227">Значок Правил авторизации не следует путать с ".NET Авторизация" в разделе ASP.NET, который является другим механизмом авторизации.</span><span class="sxs-lookup"><span data-stu-id="f15b1-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="f15b1-228">Сначала администраторы должны удалить унаследованные правила "Разрешить всем пользователям".</span><span class="sxs-lookup"><span data-stu-id="f15b1-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="f15b1-229">Это предотвращает доступ к порталу любым пользователям, не уполномоченным.</span><span class="sxs-lookup"><span data-stu-id="f15b1-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Развертывание CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="f15b1-231">Затем администраторам следует добавить новые правила разрешения и предоставить конкретным пользователям разрешение на доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="f15b1-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="f15b1-232">Для управления пользователями рекомендуется создать локальная группа CQDPortalUsers.</span><span class="sxs-lookup"><span data-stu-id="f15b1-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Развертывание панели мониторинга качества звонков](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="f15b1-234">Сведения о конфигурации хранятся в web.config, расположенном в физическом каталоге портала.</span><span class="sxs-lookup"><span data-stu-id="f15b1-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="f15b1-235">Следующий шаг — настройка панели мониторинга CQD.</span><span class="sxs-lookup"><span data-stu-id="f15b1-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="f15b1-236">После проверки подлинности iiS пользователям необходимо иметь разрешения на файл в каталоге CQD, чтобы получить доступ к контенту веб-портала.</span><span class="sxs-lookup"><span data-stu-id="f15b1-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="f15b1-237">Можно изменить acLs через вкладку безопасности свойств каталога CQD, чтобы добавить отдельных пользователей или групп; однако рекомендуемый подход заключается в том, чтобы оставить разрешения на файл нетронутыми.</span><span class="sxs-lookup"><span data-stu-id="f15b1-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="f15b1-238">Вместо этого измените параметр IIS, чтобы использовать рабочий процесс IIS для доступа к каталогу CQD независимо от того, какой пользователь является авторификацией.</span><span class="sxs-lookup"><span data-stu-id="f15b1-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f15b1-239">Важно изменить этот параметр только для приложения CQD, а не для двух приложений API: QoEDataService и QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="f15b1-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="f15b1-240">Настройка доступа к файлам для CQD (Панель мониторинга)</span><span class="sxs-lookup"><span data-stu-id="f15b1-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="f15b1-241">Откройте редактор конфигурации для CQD.</span><span class="sxs-lookup"><span data-stu-id="f15b1-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="f15b1-243">В разделе выберите **system.webServer/serverRuntime.**</span><span class="sxs-lookup"><span data-stu-id="f15b1-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="f15b1-245">Измените проверку подлинностиUserOverride на **UseWorkerProcessUser.**</span><span class="sxs-lookup"><span data-stu-id="f15b1-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов — редактор конфигурации](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="f15b1-247">Нажмите **Кнопку Применить** в правой части страницы.</span><span class="sxs-lookup"><span data-stu-id="f15b1-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="f15b1-248">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f15b1-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="f15b1-249">CQD не показывает данных после развертывания</span><span class="sxs-lookup"><span data-stu-id="f15b1-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="f15b1-250">Вы можете получить следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="f15b1-250">You may receive the following error:</span></span>

<span data-ttu-id="f15b1-251">*Мы не смогли выполнить запрос во время выполнения его на кубе. Чтобы изменить запрос и устранить все проблемы, используйте редактор запроса. Кроме того, убедитесь, что куб доступен.*</span><span class="sxs-lookup"><span data-stu-id="f15b1-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="f15b1-252">Это означает, что куб должен быть обработан в SQL Server службы анализа, прежде чем использоваться в CQD.</span><span class="sxs-lookup"><span data-stu-id="f15b1-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="f15b1-253">Это можно решить, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="f15b1-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="f15b1-254">Откройте SQL-студию управления и выберите **службы анализа**.</span><span class="sxs-lookup"><span data-stu-id="f15b1-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="f15b1-255">**Расширите объект QoECube,** выберите **метрику QoE**, щелкните правой кнопкой мыши и выберите **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="f15b1-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="f15b1-256">Если это возвращает пустой браузер, куб еще не был приступить.</span><span class="sxs-lookup"><span data-stu-id="f15b1-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="f15b1-257">Правой кнопкой **мыши QoE Metric** angain и выберите **Процесс**.</span><span class="sxs-lookup"><span data-stu-id="f15b1-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="f15b1-258">Когда обработка завершена, щелкните правой кнопкой мыши объект снова и выберите **Просмотр,** чтобы подтвердить, что на странице браузера теперь показаны данные.</span><span class="sxs-lookup"><span data-stu-id="f15b1-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="f15b1-259">У пользователей возникли проблемы с входом в систему, так как установщик не смог создать правильные параметры в IIS</span><span class="sxs-lookup"><span data-stu-id="f15b1-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="f15b1-260">В редких случаях установщику не удается создать правильные параметры в IIS.</span><span class="sxs-lookup"><span data-stu-id="f15b1-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="f15b1-261">Для входа в CQD пользователям требуется ручное изменение.</span><span class="sxs-lookup"><span data-stu-id="f15b1-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="f15b1-262">Если у пользователей возникли проблемы с входом в систему, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f15b1-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="f15b1-263">Откройте диспетчер IIS и перейдите на веб-сайт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f15b1-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="f15b1-265">Нажмите кнопку "Проверка подлинности".</span><span class="sxs-lookup"><span data-stu-id="f15b1-265">Click on "Authentication".</span></span> <span data-ttu-id="f15b1-266">Если параметры "Anonymous Authentication", "ASP.NET impersonation", "Form Authentication" и "Windows Authentication" не совпадают с настройками, показанными ниже, вручную измените их в соответствие с приведенными ниже настройками.</span><span class="sxs-lookup"><span data-stu-id="f15b1-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="f15b1-267">Все остальные механизмы проверки подлинности должны быть отключены.</span><span class="sxs-lookup"><span data-stu-id="f15b1-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="f15b1-269">Для "Проверки подлинности Windows" нажмите кнопку Расширенные параметры с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="f15b1-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="f15b1-271">Установите поле "Расширенная защита", чтобы принять и проверить поле "Включить проверку подлинности в режиме ядра".</span><span class="sxs-lookup"><span data-stu-id="f15b1-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="f15b1-273">Повторите следующие действия для каждой из записей "CQD", "QoEDataService" и "QoERepositoryService" ниже "Веб-сайт по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="f15b1-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="f15b1-274">Для привязки порта HTTP и HTTPS установщик создаст привязки портов для номеров портов по умолчанию (порт 80 для HTTP и порт 443 для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="f15b1-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="f15b1-275">Если на компьютере есть другой веб-сайт, использующий эти привязки, будет конфликт, и поведение IIS невозможно предсказать.</span><span class="sxs-lookup"><span data-stu-id="f15b1-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="f15b1-276">Лучший способ избежать этой проблемы — убедиться, что перед установкой CQD никакие другие веб-сайты не будут соеди-ными в порты 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="f15b1-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="f15b1-277">Чтобы включить SSL/TLS в IIS и заставить пользователей подключаться с помощью безопасного HTTPS вместо HTTP:</span><span class="sxs-lookup"><span data-stu-id="f15b1-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="f15b1-278">Настройка уровня безопасных розеток в IIS см. в рубрике Настройка уровня безопасных [розеток в IIS 7.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="f15b1-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).</span></span> <span data-ttu-id="f15b1-279">После этого  `http` замените `https` .</span><span class="sxs-lookup"><span data-stu-id="f15b1-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="f15b1-280">Инструкции по включению TLS в SQL Server подключениях см. в примере Как включить шифрование [SSL](https://support.microsoft.com/kb/316898/)для экземпляра SQL Server с помощью консоли управления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f15b1-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="f15b1-281">Сбой синхронизации Cube</span><span class="sxs-lookup"><span data-stu-id="f15b1-281">Cube Sync Fails</span></span>

<span data-ttu-id="f15b1-282">QoEMetrics может содержать некоторые недействительные записи, основанные на часах конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f15b1-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="f15b1-283">Если время перекоса превышает 60 лет, импорт куба будет неудачным.</span><span class="sxs-lookup"><span data-stu-id="f15b1-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="f15b1-284">Проверьте min и Max StartTime/EndTime с помощью приведенного ниже выбора.</span><span class="sxs-lookup"><span data-stu-id="f15b1-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="f15b1-285">И посмотрите и удалите записи в далеком прошлом и очень отдаленном будущем, их можно игнорировать, и они будут разрушать процессы синхронизации.</span><span class="sxs-lookup"><span data-stu-id="f15b1-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="f15b1-286">Выберите MIN (StartTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f15b1-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="f15b1-287">Выберите MAX (StartTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f15b1-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="f15b1-288">Выберите MIN (EndTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f15b1-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="f15b1-289">Выберите MAX (EndTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="f15b1-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="f15b1-290">Задачи после установки</span><span class="sxs-lookup"><span data-stu-id="f15b1-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="f15b1-291">Импорт зданий и сетей</span><span class="sxs-lookup"><span data-stu-id="f15b1-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="f15b1-292">После установки CQD выполните следующие задачи конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f15b1-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="f15b1-293">Определение типов здания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f15b1-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="f15b1-294">Определение типов владения зданиями (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f15b1-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="f15b1-295">Определение типов сети (настоятельно рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f15b1-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="f15b1-296">Импорт зданий (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f15b1-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="f15b1-297">Импортные подсети (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f15b1-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="f15b1-298">Определение типов зданий</span><span class="sxs-lookup"><span data-stu-id="f15b1-298">Define Building Types</span></span>

<span data-ttu-id="f15b1-299">Типы зданий используются для описания различных определений или типов зданий в организации.</span><span class="sxs-lookup"><span data-stu-id="f15b1-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f15b1-300">Этот шаг необязателен, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f15b1-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f15b1-301">Примеры</span><span class="sxs-lookup"><span data-stu-id="f15b1-301">Examples</span></span>
  
- <span data-ttu-id="f15b1-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="f15b1-302">Headquarters</span></span>
    
- <span data-ttu-id="f15b1-303">Remote Office</span><span class="sxs-lookup"><span data-stu-id="f15b1-303">Remote Office</span></span>
    
- <span data-ttu-id="f15b1-304">Расположение совместного предприятия</span><span class="sxs-lookup"><span data-stu-id="f15b1-304">Joint-venture location</span></span>
    
  <span data-ttu-id="f15b1-305">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="f15b1-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="f15b1-306">Необходимы параметры BuildingTypeId и BuildingTypeDesc.</span><span class="sxs-lookup"><span data-stu-id="f15b1-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="f15b1-307">Определение типов владельцев зданий</span><span class="sxs-lookup"><span data-stu-id="f15b1-307">Define Building Ownership Types</span></span>

<span data-ttu-id="f15b1-308">Типы собственности используются для различия между собственностью и арендованными активами.</span><span class="sxs-lookup"><span data-stu-id="f15b1-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f15b1-309">Этот шаг необязателен, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f15b1-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f15b1-310">Примеры</span><span class="sxs-lookup"><span data-stu-id="f15b1-310">Examples</span></span>
  
- <span data-ttu-id="f15b1-311">Contoso Leased non-RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="f15b1-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="f15b1-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="f15b1-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="f15b1-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="f15b1-313">Contoso Owned</span></span>
    
- <span data-ttu-id="f15b1-314">Дочерняя аренда</span><span class="sxs-lookup"><span data-stu-id="f15b1-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="f15b1-315">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="f15b1-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="f15b1-316">Необходимы параметры OwnershipTypeId и OwnershipTypeDesc.</span><span class="sxs-lookup"><span data-stu-id="f15b1-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="f15b1-317">Определение имен сети</span><span class="sxs-lookup"><span data-stu-id="f15b1-317">Define Network Names</span></span>

<span data-ttu-id="f15b1-318">Типы сетей используются для описания различных типов сетей в организации.</span><span class="sxs-lookup"><span data-stu-id="f15b1-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="f15b1-319">Это позволяет отфильтровать (или отфильтровать) определенные типы сетей.</span><span class="sxs-lookup"><span data-stu-id="f15b1-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f15b1-320">Настоятельно рекомендуется определять сетевые имена, но это необязательно.</span><span class="sxs-lookup"><span data-stu-id="f15b1-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="f15b1-321">Если вы решите не определять сетевые имена, убедитесь, что каждая запись CqdNetwork имеет buildingId 0.</span><span class="sxs-lookup"><span data-stu-id="f15b1-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="f15b1-322">Примеры</span><span class="sxs-lookup"><span data-stu-id="f15b1-322">Examples</span></span>
  
- <span data-ttu-id="f15b1-323">VPN</span><span class="sxs-lookup"><span data-stu-id="f15b1-323">VPN</span></span>
    
- <span data-ttu-id="f15b1-324">LAB</span><span class="sxs-lookup"><span data-stu-id="f15b1-324">LAB</span></span>
    
  <span data-ttu-id="f15b1-325">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="f15b1-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="f15b1-326">Параметры NetworkNameID и NetworkName необходимы, параметр NetworkType необязателен, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f15b1-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="f15b1-327">Импорт зданий</span><span class="sxs-lookup"><span data-stu-id="f15b1-327">Import Buildings</span></span>

<span data-ttu-id="f15b1-328">Импорт зданий позволяет получать сведения о конкретных сведениях (неудовлетворительные вызовы для каждого здания на WiFi/Wired и т.д.).</span><span class="sxs-lookup"><span data-stu-id="f15b1-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f15b1-329">Этот шаг необязателен, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f15b1-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="f15b1-330">Прежде чем импортировать новое здание, необходимо уже определить заранее заранее установленную модель BuildingKey.</span><span class="sxs-lookup"><span data-stu-id="f15b1-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="f15b1-331">Для этого выдайте команду SELECT MAX (BuildingKey) от CqdBuilding SQL для определения текущего значения и добавления 1 к результату.</span><span class="sxs-lookup"><span data-stu-id="f15b1-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="f15b1-332">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="f15b1-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="f15b1-333">Параметры BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId необходимы, остальные параметры необязательны.</span><span class="sxs-lookup"><span data-stu-id="f15b1-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="f15b1-334">Импортные подсети</span><span class="sxs-lookup"><span data-stu-id="f15b1-334">Import Subnets</span></span>

<span data-ttu-id="f15b1-335">Импорт зданий позволяет получать сведения о конкретных сведениях (неудовлетворительные вызовы для каждого здания на WiFi/Wired и т.д.).</span><span class="sxs-lookup"><span data-stu-id="f15b1-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f15b1-336">Этот шаг необязателен, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f15b1-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="f15b1-337">Импортировать подсети и соотнося их с зданиями, импортируемыми на последнем шаге.</span><span class="sxs-lookup"><span data-stu-id="f15b1-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="f15b1-338">Если вы решили не заполнять NetworkName, убедитесь, что каждая запись в этой таблице использует NetworkNameID 0.</span><span class="sxs-lookup"><span data-stu-id="f15b1-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="f15b1-339">Дополнительные сведения о синтаксисах SQL и параметрах панели мониторинга качества вызовов см. в странице Использование панели мониторинга качества вызовов для [Skype для бизнеса Server.](./use.md)</span><span class="sxs-lookup"><span data-stu-id="f15b1-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](./use.md).</span></span>
  
 <span data-ttu-id="f15b1-340">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="f15b1-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="f15b1-341">Параметры Network и UpdatedDate необходимы, остальные параметры необязательны.</span><span class="sxs-lookup"><span data-stu-id="f15b1-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="f15b1-342">Необязательный: BSSID</span><span class="sxs-lookup"><span data-stu-id="f15b1-342">Optional: BSSID</span></span>

<span data-ttu-id="f15b1-343">Заполнение данных BSSID дает дополнительную корреляцию потока WiFi по контроллеру или радио.</span><span class="sxs-lookup"><span data-stu-id="f15b1-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="f15b1-344">Это не только фильтрация с помощью создания или подсети.</span><span class="sxs-lookup"><span data-stu-id="f15b1-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="f15b1-345">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="f15b1-345">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="f15b1-346">**Сведения о CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="f15b1-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="f15b1-347">**Как показано в CQD**</span><span class="sxs-lookup"><span data-stu-id="f15b1-347">**As shown in CQD**</span></span>|<span data-ttu-id="f15b1-348">**Таблица CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="f15b1-348">**CQDBssid Table**</span></span>|<span data-ttu-id="f15b1-349">**Примеры входных данных**</span><span class="sxs-lookup"><span data-stu-id="f15b1-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f15b1-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="f15b1-350">Ap NName</span></span>  <br/> |<span data-ttu-id="f15b1-351">AP</span><span class="sxs-lookup"><span data-stu-id="f15b1-351">AP</span></span>  <br/> |<span data-ttu-id="f15b1-352">AP1</span><span class="sxs-lookup"><span data-stu-id="f15b1-352">AP1</span></span>  <br/> |
|<span data-ttu-id="f15b1-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="f15b1-353">BBssid</span></span>  <br/> |<span data-ttu-id="f15b1-354">BSS</span><span class="sxs-lookup"><span data-stu-id="f15b1-354">BSS</span></span>  <br/> |<span data-ttu-id="f15b1-355">00-00-00-00-00-00 (необходимо использовать делимитированный fformat)</span><span class="sxs-lookup"><span data-stu-id="f15b1-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="f15b1-356">Контроллер</span><span class="sxs-lookup"><span data-stu-id="f15b1-356">Controller</span></span>  <br/> |<span data-ttu-id="f15b1-357">Здание</span><span class="sxs-lookup"><span data-stu-id="f15b1-357">Building</span></span>  <br/> |<span data-ttu-id="f15b1-358">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="f15b1-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="f15b1-359">Device</span><span class="sxs-lookup"><span data-stu-id="f15b1-359">Device</span></span>  <br/> |<span data-ttu-id="f15b1-360">ess</span><span class="sxs-lookup"><span data-stu-id="f15b1-360">ess</span></span>  <br/> |<span data-ttu-id="f15b1-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="f15b1-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="f15b1-362">Радио</span><span class="sxs-lookup"><span data-stu-id="f15b1-362">Radio</span></span>  <br/> |<span data-ttu-id="f15b1-363">phy</span><span class="sxs-lookup"><span data-stu-id="f15b1-363">phy</span></span>  <br/> |<span data-ttu-id="f15b1-364">bgn</span><span class="sxs-lookup"><span data-stu-id="f15b1-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="f15b1-365">Обработка импортируемых данных</span><span class="sxs-lookup"><span data-stu-id="f15b1-365">Processing the imported data</span></span>

<span data-ttu-id="f15b1-366">По умолчанию после импорта данных здания или сети он будет применяться только к записям, созданным после этого момента.</span><span class="sxs-lookup"><span data-stu-id="f15b1-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="f15b1-367">Чтобы пометить все предыдущие записи с помощью этих новых данных, необходимо выполнить процедуру хранения CqdUpdateBuilding, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="f15b1-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="f15b1-368">Дайте ему дату первой записи (определите, что с помощью команды Select MIN (StartTime) от команды CqdPartitionedStreamView SQL), endDate завтрашнего дня, а затем NULL для последних двух значений.</span><span class="sxs-lookup"><span data-stu-id="f15b1-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="f15b1-369">После того как данные связаны с данными потока, куб SSIS должен перепроцесировать все записи.</span><span class="sxs-lookup"><span data-stu-id="f15b1-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="f15b1-370">Это также применяется при массовом добавлении данных BSSID/ISP.</span><span class="sxs-lookup"><span data-stu-id="f15b1-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="f15b1-371">Убедитесь, что выбран "Полный процесс".</span><span class="sxs-lookup"><span data-stu-id="f15b1-371">Ensure that "Process Full" is selected.</span></span>
