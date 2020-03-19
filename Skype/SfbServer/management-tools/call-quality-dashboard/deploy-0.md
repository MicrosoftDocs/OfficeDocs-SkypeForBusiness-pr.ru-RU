---
title: Развертывание панели мониторинга качества звонков для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: Сводка. сведения о процессе развертывания для панели мониторинга качества звонков. Панель мониторинга качества вызовов — это средство Skype для бизнеса Server.
ms.openlocfilehash: 5879c4a99eec8471763e0fccc3a4886be660dbb6
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "42840163"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="60461-104">Развертывание панели мониторинга качества звонков для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="60461-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="60461-105">**Сводка:** Сведения о процессе развертывания для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="60461-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="60461-106">Панель мониторинга качества вызовов — это средство Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="60461-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="60461-107">Обзор развертывания</span><span class="sxs-lookup"><span data-stu-id="60461-107">Deployment Overview</span></span>

<span data-ttu-id="60461-108">Панель мониторинга качества звонков (CQD) состоит из трех основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="60461-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="60461-109">**Архивная база данных**, в которой реплицируются и хранятся данные качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="60461-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="60461-110">**Куб**, где данные из архивной базы данных QoE объединяются для оптимизации и быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="60461-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="60461-111">**Портал**, где пользователи могут легко запрашивать и визуализировать данные QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Компоненты CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="60461-113">Процесс установки для архива QoE включает создание архивной базы данных QoE, развертывание хранимой процедуры SQL Server, которая переместит данные из исходной базы данных метрик QoE в архивную базу данных QoE и настройку задания агента SQL Server для выполнения хранимых для процедуры с регулярным интервалом.</span><span class="sxs-lookup"><span data-stu-id="60461-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="60461-114">Развертывание Куба получает сведения от пользователя, на котором размещается Архив QoE, развертывает куб и устанавливает регулярное задание агента SQL Server, которое будет обновлять куб через заданные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="60461-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="60461-115">Установка портала создает базу данных репозитория, в которой хранится сопоставление пользователей CQD с отчетами и запросами каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="60461-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="60461-116">Затем настраивается веб-приложение IIS, представляющее собой панель мониторинга, в которой пользователи могут просматривать заранее определенный набор отчетов, а также настраивать и создавать собственные запросы для отображения данных из куба.</span><span class="sxs-lookup"><span data-stu-id="60461-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="60461-117">При установке портала создаются два дополнительных веб-приложения, которые предоставляют API для программного доступа к репозиторию и Кубу.</span><span class="sxs-lookup"><span data-stu-id="60461-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="60461-118">(Эти API также используются внутри панели мониторинга).</span><span class="sxs-lookup"><span data-stu-id="60461-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="60461-119">**Этап**</span><span class="sxs-lookup"><span data-stu-id="60461-119">**Phase**</span></span>|<span data-ttu-id="60461-120">**Действия**</span><span class="sxs-lookup"><span data-stu-id="60461-120">**Steps**</span></span>|<span data-ttu-id="60461-121">**Роли и членство в группах**</span><span class="sxs-lookup"><span data-stu-id="60461-121">**Roles and group membership**</span></span>|<span data-ttu-id="60461-122">**Документация**</span><span class="sxs-lookup"><span data-stu-id="60461-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="60461-123">Установите необходимое оборудование и программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="60461-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="60461-124">Решите конфигурацию CQD и выберите сервер SQL Server, с которого будет выполняться установка.</span><span class="sxs-lookup"><span data-stu-id="60461-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="60461-125">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="60461-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="60461-126">Раздел "Предварительная установка требований" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="60461-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="60461-127">Установите CQD.</span><span class="sxs-lookup"><span data-stu-id="60461-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="60461-128">Запустите MSI, следуя документу о развертывании.</span><span class="sxs-lookup"><span data-stu-id="60461-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="60461-129">Чтобы выполнить установку, учетная запись установки должна быть пользователем домена, который является членом локальной группы администраторов и иметь доступ на чтение к базе данных метрик QoE на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="60461-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="60461-130">Разделы, посвященные учетным записям и этапам развертывания, в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="60461-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="60461-131">Предоставление пользователю доступа.</span><span class="sxs-lookup"><span data-stu-id="60461-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="60461-132">Для управления авторизацией пользователей на портале рекомендуется использовать авторизацию URL-адресов, которая появилась в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="60461-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="60461-133">Дополнительные сведения см. в статье [Общие сведения об авторизации URL-адресов IIS 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="60461-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="60461-134">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="60461-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="60461-135">Управление доступом пользователей к разделу портал в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="60461-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="60461-136">Необязательно: предоставление сведений о сопоставлении подсети.</span><span class="sxs-lookup"><span data-stu-id="60461-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="60461-137">Заполнение сети и создание таблиц сопоставлений в архивной базе данных QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="60461-138">Учетная запись, доступная для записи в архивную базу данных QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="60461-139">Раздел "предоставление сведений о подсети" в пользовательской документации.</span><span class="sxs-lookup"><span data-stu-id="60461-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="60461-140">Развертывание панели мониторинга качества звонков включает настройку инфраструктуры и установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="60461-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="60461-141">В следующей процедуре описывается процесс.</span><span class="sxs-lookup"><span data-stu-id="60461-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="60461-142">Действия по развертыванию</span><span class="sxs-lookup"><span data-stu-id="60461-142">Deployment Steps</span></span>

1. <span data-ttu-id="60461-143">Скопируйте Каллкуалитидашбоард. msi на компьютер с установленным компонентом архивной базы данных CQD (это компьютер, на котором установлен SQL Server).</span><span class="sxs-lookup"><span data-stu-id="60461-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="60461-144">Выполните MSI (Windows выведет запрос на запуск с правами администратора).</span><span class="sxs-lookup"><span data-stu-id="60461-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="60461-145">Примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="60461-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="60461-146">Выберите папку назначения, в которой будут размещаться файлы, связанные с компонентами панели мониторинга качества звонков, или оставьте расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60461-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="60461-147">Выберите все компоненты.</span><span class="sxs-lookup"><span data-stu-id="60461-147">Select all features.</span></span>
    
6. <span data-ttu-id="60461-148">На странице Конфигурация архива QoE введите следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="60461-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="60461-149">**QoE метрики SQL Server:** Имя экземпляра SQL Server, где расположена база данных метрик QoE (это будет источник данных).</span><span class="sxs-lookup"><span data-stu-id="60461-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="60461-150">**Имя архива SQL Server QoE:** Это поле предназначено только для чтения и исправлено до полного доменного имени локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="60461-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="60461-151">Архивная база данных может быть установлена только на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="60461-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="60461-152">**QoE архивный экземпляр SQL Server:** Имя локального экземпляра SQL Server, в котором будет создана архивная база данных.</span><span class="sxs-lookup"><span data-stu-id="60461-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="60461-153">Чтобы использовать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="60461-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="60461-154">Чтобы использовать именованный экземпляр SQL Server, укажите имя экземпляра (например, имя после "\").</span><span class="sxs-lookup"><span data-stu-id="60461-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="60461-155">**Архивная база данных QoE:** По умолчанию этот параметр имеет значение "создать новую базу данных".</span><span class="sxs-lookup"><span data-stu-id="60461-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="60461-156">Так как архивная база данных не поддерживается, единственные ситуации, в которых можно использовать параметр "использовать существующую базу данных", могут быть только в том случае, если существующая архивная база данных имеет ту же схему, что и сборка, которую необходимо установить.</span><span class="sxs-lookup"><span data-stu-id="60461-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="60461-157">**Каталог файлов базы данных:** Путь к месту размещения файлов базы данных (MDF и LDF) для архивной базы данных.</span><span class="sxs-lookup"><span data-stu-id="60461-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="60461-158">Это должно быть на диске (HDD2 в разделе Рекомендуемая конфигурация оборудования), отдельном от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="60461-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="60461-159">Обратите внимание, что поскольку имена файлов фиксируются в установке, чтобы избежать потенциальных конфликтов, рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="60461-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="60461-160">**Использование нескольких разделов:** По умолчанию задано значение "несколько разделов", для которого требуется выпуск SQL Server бизнес-аналитики Edition или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="60461-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="60461-161">В качестве выпуска Standard Edition выберите параметр "один раздел".</span><span class="sxs-lookup"><span data-stu-id="60461-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="60461-162">Обратите внимание на то, что производительность обработки куба может быть снижена при использовании одного раздела.</span><span class="sxs-lookup"><span data-stu-id="60461-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="60461-163">Параметр выбор для нескольких разделов невозможно изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="60461-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="60461-164">Чтобы изменить его, необходимо сначала удалить компонент Куба, а затем переустановить его с помощью параметра "Изменить" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="60461-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="60461-165">**Каталог файлов разделов:** Путь, по которому следует поместить разделы для архивной базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="60461-166">Это должно быть на диске (HDD3 в разделе Рекомендуемая конфигурация оборудования) отдельно от диска ОС и файлов журнала базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="60461-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="60461-167">Обратите внимание, что поскольку имена файлов фиксируются в установке, чтобы избежать потенциальных конфликтов, рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="60461-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="60461-168">**Задание агента SQL user — &amp; пароль пользователя:** Имя и пароль учетной записи службы домена (маскировка), которые будут использоваться для выполнения этапа "QoE Archive Data" задания агента SQL Server (которое запускает хранимую процедуру для получения данных из базы данных QoE метрик в архивную базу данных, поэтому эта учетная запись должна иметь доступ на чтение к базе данных QoE метрик, как указано в разделе Accounts.</span><span class="sxs-lookup"><span data-stu-id="60461-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="60461-169">Эта учетная запись также должна иметь имя входа в архивном экземпляре SQL Server QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="60461-170">Учетная запись, под которой выполняется экземпляр SQL Server, например NT СЕРВИЦЕ\МССКЛСЕРВЕР, должна иметь доступ к каталогам, указанным выше, для успешного завершения установки.</span><span class="sxs-lookup"><span data-stu-id="60461-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="60461-171">Дополнительные сведения см. в статье [Настройка разрешений файловой системы для доступа к ядру СУБД](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60461-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="60461-172">После нажатия кнопки Далее Установщик выполняет Предварительные проверки и сообщает о наличии проблем.</span><span class="sxs-lookup"><span data-stu-id="60461-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="60461-173">После выполнения всех предварительных проверок установщик перейдет на страницу конфигурации куба.</span><span class="sxs-lookup"><span data-stu-id="60461-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="60461-174">Если в установщике отображается предупреждение о том, что служба агента SQL Server для архивного экземпляра SQL Server в настоящее время не работает, установка может быть продолжена, но после установки убедитесь, что служба агента SQL Server запущена, и установите для параметра Тип запуска значение Автоматическое выполнение запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="60461-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="60461-175">На странице Конфигурация куба укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="60461-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="60461-176">**Имя архива SQL Server QoE:** Это поле предназначено только для чтения и исправлено до полного доменного имени локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="60461-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="60461-177">Куб можно установить только с компьютера, на котором имеется архивная база данных QoE (Примечание.</span><span class="sxs-lookup"><span data-stu-id="60461-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="60461-178">Сам куб можно установить на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="60461-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="60461-179">См. ниже)</span><span class="sxs-lookup"><span data-stu-id="60461-179">See below)</span></span>
    
   - <span data-ttu-id="60461-180">**QoE архивный экземпляр SQL Server:** Имя экземпляра SQL Server, где расположена архивная база данных QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="60461-181">Чтобы указать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="60461-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="60461-182">Чтобы указать именованный экземпляр SQL Server, введите имя экземпляра (например, имя после "\").</span><span class="sxs-lookup"><span data-stu-id="60461-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="60461-183">Если для установки выбран компонент архива QoE, это поле будет предварительно заполнено значением, указанным на странице Конфигурация архива QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="60461-184">**Сервер анализа Куба:** Имя экземпляра службы SQL Server Analysis Service для места создания куба.</span><span class="sxs-lookup"><span data-stu-id="60461-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="60461-185">Это может быть другой компьютер, но пользователь, выполняющий установку, должен быть членом группы администраторов целевого экземпляра службы SQL Server Analysis Service.</span><span class="sxs-lookup"><span data-stu-id="60461-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="60461-186">Дополнительные сведения о настройке разрешений администратора сервера служб Analysis Services содержатся в разделе [предоставление разрешений администратора сервера (службы Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="60461-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="60461-187">**Использование нескольких разделов:** По умолчанию задано значение "несколько разделов", для которого требуется выпуск SQL Server бизнес-аналитики Edition или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="60461-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="60461-188">В качестве выпуска Standard Edition выберите параметр "один раздел".</span><span class="sxs-lookup"><span data-stu-id="60461-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="60461-189">Обратите внимание на то, что производительность обработки куба может быть снижена при использовании одного раздела.</span><span class="sxs-lookup"><span data-stu-id="60461-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="60461-190">Параметр выбор для нескольких разделов невозможно изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="60461-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="60461-191">Чтобы изменить его, необходимо сначала удалить компонент Куба, а затем переустановить его с помощью параметра "Изменить" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="60461-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="60461-192">Пароль пользователя Куба: \*\* &amp; \*\* Имя и пароль учетной записи службы домена (маскированный), который будет инициировать обработку куба.</span><span class="sxs-lookup"><span data-stu-id="60461-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="60461-193">Если для установки выбран компонент архива QoE, это поле будет предварительно заполнено значением, указанным на странице Конфигурация архива для пользователя задания агента SQL, но мы рекомендуем указать другую учетную запись службы домена, чтобы программа установки могла предоставить минимальные требуемые права для него.</span><span class="sxs-lookup"><span data-stu-id="60461-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="60461-194">При нажатии кнопки Далее будет выполнен другой цикл проверки, и появится сообщение о проблемах.</span><span class="sxs-lookup"><span data-stu-id="60461-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="60461-195">После успешного завершения проверки установщик перейдет на страницу конфигурации портала.</span><span class="sxs-lookup"><span data-stu-id="60461-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="60461-196">На странице Конфигурация портала укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="60461-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="60461-197">**Архивный SQL Server QoE:** Имя экземпляра SQL Server, где расположена архивная база данных QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="60461-198">Обратите внимание, что в отличие от страницы Конфигурация архива QoE и страницы Конфигурация куба, имя компьютера не зафиксировано и должно быть указано.</span><span class="sxs-lookup"><span data-stu-id="60461-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="60461-199">Если для установки выбран компонент архива QoE, это поле будет предварительно заполнено значением, указанным на странице Конфигурация архива QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="60461-200">**Сервер анализа Куба:** Имя экземпляра службы SQL Server Analysis Service для места, где расположен куб.</span><span class="sxs-lookup"><span data-stu-id="60461-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="60461-201">Если для установки выбран компонент Куба, в это поле будет предварительно заполнено значение, указанное на странице конфигурации куба.</span><span class="sxs-lookup"><span data-stu-id="60461-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="60461-202">**SQL Server репозитория:** Имя экземпляра SQL Server, на котором будет создана база данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="60461-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="60461-203">Если имя экземпляра SQL Server, где расположена архивная база данных QoE, было предоставлено ранее в настройке (в других компонентах), это поле будет предварительно заполнено именем экземпляра SQL Server для архивной базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="60461-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="60461-204">Это может быть любой экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60461-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="60461-205">**База данных репозитория:** По умолчанию параметру присвоено значение "создать новую базу данных".</span><span class="sxs-lookup"><span data-stu-id="60461-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="60461-206">Так как обновление базы данных репозитория не поддерживается, единственные ситуации, в которых можно использовать параметр "использовать существующую базу данных", могут быть только в том случае, если существующая база данных репозитория имеет ту же схему, что и устанавливаемая сборка.</span><span class="sxs-lookup"><span data-stu-id="60461-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="60461-207">**Пользователь пула приложений IIS — пароль имени &amp; пользователя:** Учетная запись, под которой должен выполняться пул приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="60461-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="60461-208">Поля "имя пользователя" и "пароль" будут недоступны, если выбраны встроенные системные учетные записи.</span><span class="sxs-lookup"><span data-stu-id="60461-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="60461-209">Эти поля будут включены только в том случае, если в раскрывающемся списке выбран параметр "другое", чтобы пользователь мог ввести сведения об учетной записи службы домена.</span><span class="sxs-lookup"><span data-stu-id="60461-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="60461-210">При нажатии кнопки Далее будет выполнен полный круг проверки, чтобы обеспечить доступ к экземплярам SQL Server с помощью предоставленных учетных данных и доступности служб IIS на компьютере.</span><span class="sxs-lookup"><span data-stu-id="60461-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="60461-211">После успешного завершения проверки Установщик продолжит установку.</span><span class="sxs-lookup"><span data-stu-id="60461-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="60461-212">По завершении работы программы установки, скорее всего, будет выполняться задание агента SQL Server, в результате чего выполняется начальная загрузка данных QoE и обработка куба.</span><span class="sxs-lookup"><span data-stu-id="60461-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="60461-213">В зависимости от объема данных в QoE портал не сможет получить доступ к данным для просмотра.</span><span class="sxs-lookup"><span data-stu-id="60461-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="60461-214">Чтобы проверить состояние загрузки данных и обработки куба, перейдите на `http://<machinename>/CQD/#/Health`страницу.</span><span class="sxs-lookup"><span data-stu-id="60461-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="60461-215">Обратите внимание, что URL-адрес для проверки состояния загрузки Куба задается с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="60461-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="60461-216">Если ввести "работоспособность", URL-адрес не будет работать.</span><span class="sxs-lookup"><span data-stu-id="60461-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="60461-217">Необходимо ввести "работоспособность" в конце URL-адреса с прописной буквы H.</span><span class="sxs-lookup"><span data-stu-id="60461-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="60461-218">Подробные сообщения журнала будут отображаться, если включен режим отладки.</span><span class="sxs-lookup"><span data-stu-id="60461-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="60461-219">Чтобы включить режим отладки, перейдите на страницу **%Системдриве%\програм Files\Skype для бизнеса 2015 ккд\коедатасервице\веб.конфиг**и обновите следующую строку, чтобы присвоить параметру значение **true**:</span><span class="sxs-lookup"><span data-stu-id="60461-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="60461-220">Доступ к главной странице портала предоставляется через `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="60461-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="60461-221">Управление доступом пользователей к порталу</span><span class="sxs-lookup"><span data-stu-id="60461-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="60461-222">Для управления авторизацией пользователей на портале рекомендуется использовать авторизацию URL-адресов, которая появилась в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="60461-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="60461-223">Более подробную информацию о безопасности IIS можно узнать в статье [сведения об авторизации URL-адресов iis 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="60461-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="60461-224">Любой веб-сайт или веб-приложение наследуют авторизацию URL-адреса по умолчанию, настроенную для всей службы IIS, обычно это "разрешить всем пользователям".</span><span class="sxs-lookup"><span data-stu-id="60461-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="60461-225">Если доступ к порталу должен быть более четким, администраторы могут предоставлять доступ только определенной группе пользователей, редактируя "правила авторизации".</span><span class="sxs-lookup"><span data-stu-id="60461-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Развертывание правил авторизации качества вызова в IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="60461-227">Значок "правила авторизации" не следует путать с параметром "авторизация .NET" в разделе ASP.NET, который является другим механизмом проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="60461-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="60461-228">Сначала администраторы должны удалить унаследованное правило "разрешить все пользователи".</span><span class="sxs-lookup"><span data-stu-id="60461-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="60461-229">Это предотвращает доступ к порталу для всех неавторизованных пользователей.</span><span class="sxs-lookup"><span data-stu-id="60461-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Развертывание CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="60461-231">Затем администраторы должны добавить новые правила разрешения и предоставить определенным пользователям разрешение на доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="60461-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="60461-232">Для управления пользователями рекомендуется создавать локальную группу под названием "Ккдпорталусерс".</span><span class="sxs-lookup"><span data-stu-id="60461-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Развертывание панели мониторинга качества вызовов](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="60461-234">Сведения о конфигурации хранятся в файле Web. config, расположенном в физическом каталоге портала.</span><span class="sxs-lookup"><span data-stu-id="60461-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="60461-235">Следующий шаг — настройка панели мониторинга для CQD.</span><span class="sxs-lookup"><span data-stu-id="60461-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="60461-236">После того как пользователи проходят проверку подлинности службами IIS, они должны иметь разрешения на доступ к каталогу CQD для доступа к контенту веб-портала.</span><span class="sxs-lookup"><span data-stu-id="60461-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="60461-237">Можно изменить списки управления доступом на вкладке Безопасность в свойствах каталога CQD, чтобы добавить отдельных пользователей или группы; Однако рекомендуемый подход — оставить разрешения на доступ к файлам без изменений.</span><span class="sxs-lookup"><span data-stu-id="60461-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="60461-238">Вместо этого измените параметр IIS так, чтобы он использовал рабочий процесс IIS для доступа к каталогу CQD, независимо от того, какой пользователь прошел проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="60461-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="60461-239">Важно изменить этот параметр только для приложения CQD, а не для двух приложений API: Коедатасервице и Коерепоситорисервице.</span><span class="sxs-lookup"><span data-stu-id="60461-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="60461-240">Настройка доступа к файлам для CQD (панель мониторинга)</span><span class="sxs-lookup"><span data-stu-id="60461-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="60461-241">Откройте редактор конфигурации для CQD.</span><span class="sxs-lookup"><span data-stu-id="60461-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="60461-243">В разделе Раздел выберите **System. Server/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="60461-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="60461-245">Измените значение Аусентикатедусероверриде на **усеворкерпроцессусер**.</span><span class="sxs-lookup"><span data-stu-id="60461-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов — редактор конфигураций](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="60461-247">Нажмите кнопку **Применить** в правой части страницы.</span><span class="sxs-lookup"><span data-stu-id="60461-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="60461-248">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="60461-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="60461-249">CQD не показывает данные после развертывания</span><span class="sxs-lookup"><span data-stu-id="60461-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="60461-250">Может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="60461-250">You may receive the following error:</span></span>

<span data-ttu-id="60461-251">*Не удалось выполнить запрос во время его выполнения в Кубе. С помощью редактора запросов измените запрос и устраните все неполадки. Кроме того, убедитесь, что куб доступен.*</span><span class="sxs-lookup"><span data-stu-id="60461-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="60461-252">Это означает, что куб должен быть обработан в службах SQL Server Analysis Services до использования в CQD.</span><span class="sxs-lookup"><span data-stu-id="60461-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="60461-253">Для устранения этой проблемы выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60461-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="60461-254">Откройте SQL Management Studio и выберите **службы Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="60461-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="60461-255">Разверните объект **коекубе** , выберите **QoE метрика**, щелкните правой кнопкой мыши и выберите **Browse (обзор**).</span><span class="sxs-lookup"><span data-stu-id="60461-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="60461-256">Если этот параметр возвращает пустой браузер, куб еще не был выполнен.</span><span class="sxs-lookup"><span data-stu-id="60461-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="60461-257">Щелкните правой кнопкой мыши **QoE метрика** ангаин и выберите пункт **процесс**.</span><span class="sxs-lookup"><span data-stu-id="60461-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="60461-258">По завершении обработки щелкните объект правой кнопкой мыши и выберите пункт **Обзор** , чтобы убедиться, что страница браузера теперь отображает данные.</span><span class="sxs-lookup"><span data-stu-id="60461-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="60461-259">У пользователей возникают проблемы с входом в систему, так как установщик не создает правильные параметры в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="60461-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="60461-260">В редких случаях установщик не создает правильные параметры в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="60461-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="60461-261">Для предоставления пользователям возможности входа в CQD требуется ручное изменение.</span><span class="sxs-lookup"><span data-stu-id="60461-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="60461-262">Если у пользователей возникают проблемы с входом в систему, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="60461-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="60461-263">Откройте диспетчер IIS и перейдите на веб-сайт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60461-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="60461-265">Щелкните "Проверка подлинности".</span><span class="sxs-lookup"><span data-stu-id="60461-265">Click on "Authentication".</span></span> <span data-ttu-id="60461-266">Если "Анонимная проверка подлинности", "олицетворение" ASP.NET "," Проверка подлинности формы "и" Проверка подлинности Windows "не совпадают с указанными ниже параметрами, вручную измените их в соответствии с приведенными ниже параметрами.</span><span class="sxs-lookup"><span data-stu-id="60461-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="60461-267">Все остальные механизмы проверки подлинности должны быть отключены.</span><span class="sxs-lookup"><span data-stu-id="60461-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="60461-269">В разделе "Проверка подлинности Windows" щелкните Дополнительные параметры справа.</span><span class="sxs-lookup"><span data-stu-id="60461-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="60461-271">Установите флажок "Расширенная защита", чтобы принять и установить флажок "включить проверку подлинности в режиме ядра".</span><span class="sxs-lookup"><span data-stu-id="60461-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="60461-273">Повторите указанные выше действия для каждой из записей "CQD", "Коедатасервице" и "Коерепоситорисервице" ниже "Default Web Site".</span><span class="sxs-lookup"><span data-stu-id="60461-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="60461-274">Для привязок портов HTTP и HTTPS Установщик создаст привязки портов для номеров портов по умолчанию (порт 80 для HTTP и порт 443 для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="60461-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="60461-275">Если на компьютере, на котором используются эти привязки, имеется другой веб-сайт, произойдет конфликт, и поведение IIS не будет предсказуемо.</span><span class="sxs-lookup"><span data-stu-id="60461-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="60461-276">Лучший способ избежать этой проблемы — убедиться в отсутствии других веб-сайтов, сопоставленных с портами 80 и 443, прежде чем устанавливать CQD.</span><span class="sxs-lookup"><span data-stu-id="60461-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="60461-277">Включение протокола SSL/TLS в IIS и принудительное подключение пользователей через безопасный протокол HTTPS, а не HTTP:</span><span class="sxs-lookup"><span data-stu-id="60461-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="60461-278">Configure Secure Sockets Layer в службах IIS: [Настройка протокола Secure Sockets в службах IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="60461-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="60461-279">После завершения замените `http` на `https`.</span><span class="sxs-lookup"><span data-stu-id="60461-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="60461-280">Инструкции по включению протокола TLS в подключениях SQL Server приведены [в статье как включить шифрование SSL для экземпляра SQL Server с помощью консоли управления (MMC](https://support.microsoft.com/kb/316898/)).</span><span class="sxs-lookup"><span data-stu-id="60461-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="60461-281">Сбой синхронизации Куба</span><span class="sxs-lookup"><span data-stu-id="60461-281">Cube Sync Fails</span></span>

<span data-ttu-id="60461-282">В QoEMetrics могут содержаться некоторые недопустимые записи на основе часов конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="60461-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="60461-283">Если отклонение по времени превышает 60 ИРС, импорт Куба завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="60461-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="60461-284">Проверьте минимальное и максимальное значение StartTime/EndTime, используя параметры, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="60461-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="60461-285">Искать и удалять записи в крайних прошлых и очень удаленных возможностях, они могут быть продолжены и добиваться процессов синхронизации.</span><span class="sxs-lookup"><span data-stu-id="60461-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="60461-286">Выберите MIN (StartTime) (время начала) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="60461-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="60461-287">Выберите максимальное (StartTime) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="60461-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="60461-288">Выберите MIN (EndTime) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="60461-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="60461-289">Выберите максимальное (EndTime) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="60461-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="60461-290">Задачи, выполняемые после установки</span><span class="sxs-lookup"><span data-stu-id="60461-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="60461-291">Импорт зданий и сетей</span><span class="sxs-lookup"><span data-stu-id="60461-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="60461-292">После установки CQD выполните следующие задачи по настройке:</span><span class="sxs-lookup"><span data-stu-id="60461-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="60461-293">Определение типов здания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="60461-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="60461-294">Определение типов владения для здания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="60461-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="60461-295">Определение типов сети (настоятельно рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="60461-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="60461-296">Импорт зданий (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="60461-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="60461-297">Импорт подсетей (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="60461-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="60461-298">Определение типов построений</span><span class="sxs-lookup"><span data-stu-id="60461-298">Define Building Types</span></span>

<span data-ttu-id="60461-299">Типы построений используются для описания различных определений или типов зданий в Организации.</span><span class="sxs-lookup"><span data-stu-id="60461-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60461-300">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="60461-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60461-301">Примеры</span><span class="sxs-lookup"><span data-stu-id="60461-301">Examples</span></span>
  
- <span data-ttu-id="60461-302">Главный офис</span><span class="sxs-lookup"><span data-stu-id="60461-302">Headquarters</span></span>
    
- <span data-ttu-id="60461-303">Удаленный Office</span><span class="sxs-lookup"><span data-stu-id="60461-303">Remote Office</span></span>
    
- <span data-ttu-id="60461-304">Совместное размещение</span><span class="sxs-lookup"><span data-stu-id="60461-304">Joint-venture location</span></span>
    
  <span data-ttu-id="60461-305">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="60461-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="60461-306">Параметры Буилдингтипеид и Буилдингтипедеск являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="60461-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="60461-307">Определение типов владения для здания</span><span class="sxs-lookup"><span data-stu-id="60461-307">Define Building Ownership Types</span></span>

<span data-ttu-id="60461-308">Типы владения используются для различения собственных активов и арендованных активов.</span><span class="sxs-lookup"><span data-stu-id="60461-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60461-309">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="60461-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60461-310">Примеры</span><span class="sxs-lookup"><span data-stu-id="60461-310">Examples</span></span>
  
- <span data-ttu-id="60461-311">Аренда в аренду без ПОВТОРЕНИЯ&amp;</span><span class="sxs-lookup"><span data-stu-id="60461-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="60461-312">Аренда в аренду&amp;(Contoso)</span><span class="sxs-lookup"><span data-stu-id="60461-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="60461-313">Владелец contoso</span><span class="sxs-lookup"><span data-stu-id="60461-313">Contoso Owned</span></span>
    
- <span data-ttu-id="60461-314">Арендованный дочерний</span><span class="sxs-lookup"><span data-stu-id="60461-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="60461-315">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="60461-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60461-316">Параметры Овнершиптипеид и Овнершиптипедеск являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="60461-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="60461-317">Определение сетевых имен</span><span class="sxs-lookup"><span data-stu-id="60461-317">Define Network Names</span></span>

<span data-ttu-id="60461-318">Типы сети используются для описания различных типов сетей в Организации.</span><span class="sxs-lookup"><span data-stu-id="60461-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="60461-319">Это дает возможность фильтровать (или отфильтровывать) определенные типы сетей.</span><span class="sxs-lookup"><span data-stu-id="60461-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60461-320">Настоятельно рекомендуется определить сетевые имена, но это необязательно.</span><span class="sxs-lookup"><span data-stu-id="60461-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="60461-321">Если вы решили не определять сетевые имена, убедитесь, что для каждой записи Ккднетворк задано значение Буилдингид 0.</span><span class="sxs-lookup"><span data-stu-id="60461-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="60461-322">Примеры</span><span class="sxs-lookup"><span data-stu-id="60461-322">Examples</span></span>
  
- <span data-ttu-id="60461-323">VPN</span><span class="sxs-lookup"><span data-stu-id="60461-323">VPN</span></span>
    
- <span data-ttu-id="60461-324">Labs</span><span class="sxs-lookup"><span data-stu-id="60461-324">LAB</span></span>
    
  <span data-ttu-id="60461-325">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="60461-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="60461-326">Параметры Нетворкнамеид и Нетворкнаме являются обязательными, параметр Нетворктипе является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="60461-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="60461-327">Импорт зданий</span><span class="sxs-lookup"><span data-stu-id="60461-327">Import Buildings</span></span>

<span data-ttu-id="60461-328">При импорте зданий вы можете создавать конкретные аналитические сведения (некачественные вызовы для каждого здания на WiFi/Wired и т. д.).</span><span class="sxs-lookup"><span data-stu-id="60461-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60461-329">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="60461-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="60461-330">Перед импортом нового здания уже должно быть определено предопределенное Буилдингкэй.</span><span class="sxs-lookup"><span data-stu-id="60461-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="60461-331">Для этого выполните команду SQL "SELECT MAX (Буилдингкэй) FROM CqdBuilding", чтобы определить текущее значение, и добавьте 1 к результату.</span><span class="sxs-lookup"><span data-stu-id="60461-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="60461-332">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="60461-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60461-333">Параметры Буилдингкэй, Буилдингнаме, Буилдингшортнаме, Овнершиптипеид, Буилдингтипеид являются обязательными, другие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="60461-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="60461-334">Импорт подсетей</span><span class="sxs-lookup"><span data-stu-id="60461-334">Import Subnets</span></span>

<span data-ttu-id="60461-335">При импорте зданий вы можете создавать конкретные аналитические сведения (некачественные вызовы для каждого здания на WiFi/Wired и т. д.).</span><span class="sxs-lookup"><span data-stu-id="60461-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60461-336">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="60461-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="60461-337">Импортируйте подсети и сопоставьте их с зданиями, импортированными на последнем этапе.</span><span class="sxs-lookup"><span data-stu-id="60461-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="60461-338">Если вы решили не заполнять Нетворкнаме, убедитесь, что каждая запись в этой таблице использует Нетворкнамеид 0.</span><span class="sxs-lookup"><span data-stu-id="60461-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="60461-339">Дополнительные сведения о синтаксисе и параметрах SQL для панели мониторинга качества звонков приведены в разделе [Использование панели мониторинга качества звонков для Skype для бизнеса Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span><span class="sxs-lookup"><span data-stu-id="60461-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="60461-340">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="60461-340">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60461-341">Параметры Network и Упдатеддате являются обязательными, другие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="60461-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="60461-342">Необязательно: BSSID</span><span class="sxs-lookup"><span data-stu-id="60461-342">Optional: BSSID</span></span>

<span data-ttu-id="60461-343">Заполнение BSSID Information предоставляет дополнительную корреляцию потоков WiFi по контроллеру или радио.</span><span class="sxs-lookup"><span data-stu-id="60461-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="60461-344">Это дополнение к фильтрации по сборке или подсети.</span><span class="sxs-lookup"><span data-stu-id="60461-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="60461-345">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="60461-345">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="60461-346">**Сведения о Ккдбссидтабле**</span><span class="sxs-lookup"><span data-stu-id="60461-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="60461-347">**Как показано в CQD**</span><span class="sxs-lookup"><span data-stu-id="60461-347">**As shown in CQD**</span></span>|<span data-ttu-id="60461-348">**Таблица Ккдбссид**</span><span class="sxs-lookup"><span data-stu-id="60461-348">**CQDBssid Table**</span></span>|<span data-ttu-id="60461-349">**Примеры входных данных**</span><span class="sxs-lookup"><span data-stu-id="60461-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60461-350">Ннаме AP</span><span class="sxs-lookup"><span data-stu-id="60461-350">Ap NName</span></span>  <br/> |<span data-ttu-id="60461-351">ТОЧКУ</span><span class="sxs-lookup"><span data-stu-id="60461-351">AP</span></span>  <br/> |<span data-ttu-id="60461-352">AP1</span><span class="sxs-lookup"><span data-stu-id="60461-352">AP1</span></span>  <br/> |
|<span data-ttu-id="60461-353">ббссид</span><span class="sxs-lookup"><span data-stu-id="60461-353">BBssid</span></span>  <br/> |<span data-ttu-id="60461-354">BSS</span><span class="sxs-lookup"><span data-stu-id="60461-354">BSS</span></span>  <br/> |<span data-ttu-id="60461-355">00-00-00-00-00-00 (необходимо использовать фформат с разделителями)</span><span class="sxs-lookup"><span data-stu-id="60461-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="60461-356">Контроллер</span><span class="sxs-lookup"><span data-stu-id="60461-356">Controller</span></span>  <br/> |<span data-ttu-id="60461-357">Создания</span><span class="sxs-lookup"><span data-stu-id="60461-357">Building</span></span>  <br/> |<span data-ttu-id="60461-358">Аруба AP 7</span><span class="sxs-lookup"><span data-stu-id="60461-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="60461-359">Device</span><span class="sxs-lookup"><span data-stu-id="60461-359">Device</span></span>  <br/> |<span data-ttu-id="60461-360">Рес</span><span class="sxs-lookup"><span data-stu-id="60461-360">ess</span></span>  <br/> |<span data-ttu-id="60461-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="60461-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="60461-362">Сети</span><span class="sxs-lookup"><span data-stu-id="60461-362">Radio</span></span>  <br/> |<span data-ttu-id="60461-363">физического</span><span class="sxs-lookup"><span data-stu-id="60461-363">phy</span></span>  <br/> |<span data-ttu-id="60461-364">бгн</span><span class="sxs-lookup"><span data-stu-id="60461-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="60461-365">Обработка импортированных данных</span><span class="sxs-lookup"><span data-stu-id="60461-365">Processing the imported data</span></span>

<span data-ttu-id="60461-366">По умолчанию после импорта данных здания и сети он будет применяться только к записям, созданным после этого момента времени.</span><span class="sxs-lookup"><span data-stu-id="60461-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="60461-367">Чтобы отметить все предыдущие записи новыми данными, необходимо запустить хранимую процедуру Ккдупдатебуилдинг, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="60461-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="60461-368">Присвойте ей дату первой записи (с помощью команды SELECT MIN (StartTime) FROM Ккдпартитионедстреамвиев SQL), EndDate завтрашнего дня, а затем значение NULL для последних двух значений.</span><span class="sxs-lookup"><span data-stu-id="60461-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="60461-369">После того как данные сопоставлены с данными потока, куб служб SSIS должен повторно обработать все записи.</span><span class="sxs-lookup"><span data-stu-id="60461-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="60461-370">Это также применимо при массовом добавлении данных BSSID/ISP.</span><span class="sxs-lookup"><span data-stu-id="60461-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="60461-371">Убедитесь, что выбран пункт "процесс полон".</span><span class="sxs-lookup"><span data-stu-id="60461-371">Ensure that "Process Full" is selected.</span></span>
  

