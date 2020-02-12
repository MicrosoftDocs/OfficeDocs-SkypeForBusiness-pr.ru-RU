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
description: 'Сводка: сведения о процессе развертывания для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 3ab7ea5130b33578169505969ee8f43a73a2ac32
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888838"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="a98dd-104">Развертывание панели мониторинга качества звонков для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a98dd-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="a98dd-105">**Сводка:** Сведения о процессе развертывания для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a98dd-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="a98dd-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a98dd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="a98dd-107">Общие сведения о развертывании</span><span class="sxs-lookup"><span data-stu-id="a98dd-107">Deployment Overview</span></span>

<span data-ttu-id="a98dd-108">Панель мониторинга качества звонков (CQD) состоит из трех основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="a98dd-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="a98dd-109">**Архивная база данных**, на которой реплицируются и сохраняются данные качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="a98dd-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="a98dd-110">**Куб**, где данные из архивной базы данных QoE объединяются для оптимизации и быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="a98dd-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="a98dd-111">**Портал**, где пользователи могут легко запрашивать и визуализировать данные QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Компоненты CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="a98dd-113">Процесс настройки архивации QoE включает в себя создание архивной базы данных QoE, развертывание хранимой процедуры SQL Server, которая будет перемещать данные из исходной базы данных QoE метрик в QoE архивной базе данных и настройку задания агента SQL Server для выполнения сохраненных процедуры с регулярным интервалом.</span><span class="sxs-lookup"><span data-stu-id="a98dd-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="a98dd-114">Развертывание куба возвращает данные от пользователя, на котором находится архив QoE, развертывает куб и устанавливает регулярное задание агента SQL Server, которое будет обновлять куб через регулярные интервалы.</span><span class="sxs-lookup"><span data-stu-id="a98dd-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="a98dd-115">Установка портала создает базу данных репозитория, в которой хранится сопоставление CQD пользователей с отчетами и запросами каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a98dd-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="a98dd-116">Затем настраивается веб-приложение IIS, представляющее собой панель мониторинга, в которой пользователи могут просматривать предварительно определенный набор отчетов, а также настраивать и создавать собственные запросы для визуализации данных из куба.</span><span class="sxs-lookup"><span data-stu-id="a98dd-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="a98dd-117">Установка портала создает два дополнительных веб-приложения, которые предоставляют API для пользователей для программного доступа к хранилищу и Кубу.</span><span class="sxs-lookup"><span data-stu-id="a98dd-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="a98dd-118">(Эти API-интерфейсы также используются на панели мониторинга для внутренних целей).</span><span class="sxs-lookup"><span data-stu-id="a98dd-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="a98dd-119">**Этап**</span><span class="sxs-lookup"><span data-stu-id="a98dd-119">**Phase**</span></span>|<span data-ttu-id="a98dd-120">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="a98dd-120">**Steps**</span></span>|<span data-ttu-id="a98dd-121">**Членство в ролях и группе**</span><span class="sxs-lookup"><span data-stu-id="a98dd-121">**Roles and group membership**</span></span>|<span data-ttu-id="a98dd-122">**Документация**</span><span class="sxs-lookup"><span data-stu-id="a98dd-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a98dd-123">Установка необходимого оборудования и программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a98dd-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="a98dd-124">Определите конфигурацию CQD и выберите сервер SQL Server, с которого нужно выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="a98dd-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="a98dd-125">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="a98dd-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="a98dd-126">Раздел "требования к предварительной установке" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a98dd-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="a98dd-127">Установите CQD.</span><span class="sxs-lookup"><span data-stu-id="a98dd-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="a98dd-128">Запустите MSI-файл, следуя документу развертывания.</span><span class="sxs-lookup"><span data-stu-id="a98dd-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="a98dd-129">Чтобы выполнить настройку, учетная запись должна быть пользователем домена, который является членом локальной группы администраторов и имел доступ на чтение к базе данных метрик QoE на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a98dd-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="a98dd-130">Разделы "учетные записи и этапы развертывания" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a98dd-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="a98dd-131">Предоставление пользователям доступа.</span><span class="sxs-lookup"><span data-stu-id="a98dd-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="a98dd-132">Для управления авторизацией пользователей на портале рекомендуется использовать URL-авторизацию, которая была представлена в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="a98dd-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="a98dd-133">Дополнительные сведения можно найти в разделе [сведения об авторизации URL-адреса IIS 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="a98dd-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="a98dd-134">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="a98dd-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="a98dd-135">Управление доступом пользователей к разделу портал в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a98dd-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="a98dd-136">Необязательно: предоставление сведений о сопоставлении подсети.</span><span class="sxs-lookup"><span data-stu-id="a98dd-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="a98dd-137">Заполнение сети и создание таблиц сопоставлений в QoE архивной базе данных.</span><span class="sxs-lookup"><span data-stu-id="a98dd-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="a98dd-138">Учетная запись, доступная для записи, в архивную базу данных QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="a98dd-139">Раздел "предоставление сведений о подсети" в пользовательской документации.</span><span class="sxs-lookup"><span data-stu-id="a98dd-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="a98dd-140">Развертывание панели мониторинга качества звонков включает в себя настройку инфраструктуры и установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a98dd-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="a98dd-141">Ниже приведена процедура, в которой описан процесс.</span><span class="sxs-lookup"><span data-stu-id="a98dd-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="a98dd-142">Действия по развертыванию</span><span class="sxs-lookup"><span data-stu-id="a98dd-142">Deployment Steps</span></span>

1. <span data-ttu-id="a98dd-143">Скопируйте Каллкуалитидашбоард. msi на компьютер, на котором установлен компонент архивной базы данных CQD (это компьютер, на котором установлен SQL Server).</span><span class="sxs-lookup"><span data-stu-id="a98dd-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="a98dd-144">Запустите MSI (Windows выдаст запрос на запуск с правами администратора, сделайте это).</span><span class="sxs-lookup"><span data-stu-id="a98dd-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="a98dd-145">Принимайте условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="a98dd-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="a98dd-146">Выберите конечную папку, в которой будут размещены файлы, связанные с компонентами на панели мониторинга качества звонков, или подтвердите расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a98dd-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="a98dd-147">Выберите все функции.</span><span class="sxs-lookup"><span data-stu-id="a98dd-147">Select all features.</span></span>
    
6. <span data-ttu-id="a98dd-148">На странице Конфигурация архива QoE введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a98dd-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="a98dd-149">**QoE метрики SQL Server:** Имя экземпляра сервера SQL Server, на котором находится база данных метрик QoE (это будет источник).</span><span class="sxs-lookup"><span data-stu-id="a98dd-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="a98dd-150">**Имя архива SQL Server QoE:** Это поле доступно только для чтения и исправлено для полного доменного имени локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a98dd-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="a98dd-151">Архивная база данных может быть установлена только на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a98dd-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="a98dd-152">**Экземпляр SQL Server QoE Archive:** Имя локального экземпляра сервера SQL Server, на котором нужно создать архивную базу данных.</span><span class="sxs-lookup"><span data-stu-id="a98dd-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="a98dd-153">Чтобы использовать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="a98dd-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="a98dd-154">Чтобы использовать именованный экземпляр SQL Server, укажите имя экземпляра (например, имя после знака "\").</span><span class="sxs-lookup"><span data-stu-id="a98dd-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="a98dd-155">**QoE архивная база данных:** По умолчанию этот параметр имеет значение "создать новую базу данных".</span><span class="sxs-lookup"><span data-stu-id="a98dd-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="a98dd-156">Поскольку архивация базы данных не поддерживается, единственным случаем использования параметра "использовать существующую базу данных" может быть случай, если существующая база данных имеет ту же схему, что и сборка, которую нужно установить.</span><span class="sxs-lookup"><span data-stu-id="a98dd-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="a98dd-157">**Каталог файла базы данных:** Путь к месту размещения файлов баз данных (MDF и LDF) для архивной БД.</span><span class="sxs-lookup"><span data-stu-id="a98dd-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="a98dd-158">Это должно быть на диске (HDD2 в рекомендуемой конфигурации оборудования) отдельно от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a98dd-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="a98dd-159">Обратите внимание, что поскольку имена файлов Исправлены в установке, чтобы избежать возможного конфликта, рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="a98dd-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="a98dd-160">**Использование нескольких разделов:** Для параметра по умолчанию задано значение "несколько секций", для которого требуется выпуск SQL Server для бизнес-аналитики выпуска или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a98dd-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="a98dd-161">В качестве выпуска Standard Edition выберите параметр "один раздел".</span><span class="sxs-lookup"><span data-stu-id="a98dd-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="a98dd-162">Обратите внимание на то, что производительность обработки куба может быть снижена, если используется единственная секция.</span><span class="sxs-lookup"><span data-stu-id="a98dd-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a98dd-163">Выбор параметра "использовать несколько секций" не может быть изменен после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="a98dd-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="a98dd-164">Чтобы изменить его, необходимо сначала удалить функцию Куба, а затем повторно установить ее с помощью параметра "Изменить" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="a98dd-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="a98dd-165">**Каталог файла раздела:** Путь к разделу, в который нужно поместить разделы из архивной базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="a98dd-166">Это должно быть на диске (HDD3 в рекомендуемой конфигурации оборудования) отдельно от диска ОС и файлов журнала базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="a98dd-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="a98dd-167">Обратите внимание, что поскольку имена файлов Исправлены в установке, чтобы избежать возможного конфликта, рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="a98dd-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="a98dd-168">**Имя &amp; пользователя задания агента SQL Server — пароль:** Имя учетной записи службы домена и пароль (маска), которые будут использоваться для запуска задания "QoE Archive Data" агента SQL Server (который запускает хранимую процедуру для получения данных из QoE метрик данных в архивную базу данных, поэтому эта учетная запись должна иметь доступ на чтение к QoE метрики, как указано в разделе "учетные записи".</span><span class="sxs-lookup"><span data-stu-id="a98dd-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="a98dd-169">У этой учетной записи также должно быть имя для входа в экземпляре SQL Server Archive QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a98dd-170">Учетная запись, в которой выполняется экземпляр SQL Server, например NT СЕРВИЦЕ\МССКЛСЕРВЕР, должна иметь доступ к каталогам, указанным выше, для успешной установки.</span><span class="sxs-lookup"><span data-stu-id="a98dd-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="a98dd-171">Дополнительные сведения можно найти в разделе [Настройка разрешений файловой системы для доступа к ядру СУБД](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a98dd-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="a98dd-172">После нажатия кнопки "Далее" установщик будет выполнять проверки предварительных требований и сообщать о возникших проблемах.</span><span class="sxs-lookup"><span data-stu-id="a98dd-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="a98dd-173">После того как все условия предварительной проверки будут выполнены, установщик перейдет на страницу конфигурации куба.</span><span class="sxs-lookup"><span data-stu-id="a98dd-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a98dd-174">Если в установщике появляется предупреждение о том, что служба агента SQL Server для QoE архива SQL Server в настоящее время не выполняется, установка может быть продолжена, но после установки должна быть установлена служба агента SQL, а для типа запуска — значение Автоматическое выполнение запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a98dd-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="a98dd-175">На странице Конфигурация куба введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a98dd-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="a98dd-176">**Имя архива SQL Server QoE:** Это поле доступно только для чтения и исправлено для полного доменного имени локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a98dd-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="a98dd-177">Куб можно установить только с компьютера, на котором QoE архивная база данных (Примечание.</span><span class="sxs-lookup"><span data-stu-id="a98dd-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="a98dd-178">Сам куб может быть установлен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a98dd-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="a98dd-179">См. ниже)</span><span class="sxs-lookup"><span data-stu-id="a98dd-179">See below)</span></span>
    
   - <span data-ttu-id="a98dd-180">**Экземпляр SQL Server QoE Archive:** Имя экземпляра SQL Server, на котором расположена архивная база данных QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="a98dd-181">Чтобы указать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="a98dd-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="a98dd-182">Чтобы указать именованный экземпляр SQL Server, введите имя экземпляра (например, имя после знака "\").</span><span class="sxs-lookup"><span data-stu-id="a98dd-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="a98dd-183">Если для установки выбран компонент архивации QoE, это поле будет предварительно заполнено значением, указанным на странице конфигурации архивации QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="a98dd-184">**Сервер анализа кубов:** Имя экземпляра службы SQL Server Analysis Service для места создания куба.</span><span class="sxs-lookup"><span data-stu-id="a98dd-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="a98dd-185">Это может быть другой компьютер, но пользователь, выполняющий установку, должен быть членом группы администраторов сервера в целевом экземпляре службы SQL Server Analysis Service.</span><span class="sxs-lookup"><span data-stu-id="a98dd-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="a98dd-186">Дополнительные сведения о настройке разрешений администратора сервера служб Analysis Services см. в разделе [предоставление разрешений администратора сервера (службы Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="a98dd-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="a98dd-187">**Использование нескольких разделов:** Для параметра по умолчанию задано значение "несколько секций", для которого требуется выпуск SQL Server для бизнес-аналитики выпуска или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a98dd-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="a98dd-188">В качестве выпуска Standard Edition выберите параметр "один раздел".</span><span class="sxs-lookup"><span data-stu-id="a98dd-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="a98dd-189">Обратите внимание на то, что производительность обработки куба может быть снижена, если используется единственная секция.</span><span class="sxs-lookup"><span data-stu-id="a98dd-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="a98dd-190">Выбор параметра "использовать несколько секций" не может быть изменен после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="a98dd-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="a98dd-191">Чтобы изменить его, необходимо сначала удалить функцию Куба, а затем повторно установить ее с помощью параметра "Изменить" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="a98dd-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="a98dd-192">**Пароль пользователя — имя &amp; пользователя:** Имя учетной записи службы домена и пароль (маска), которые будут инициировать обработку куба.</span><span class="sxs-lookup"><span data-stu-id="a98dd-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="a98dd-193">Если для установки выбран компонент архивации QoE, это поле будет предварительно заполнено значением, указанным на странице Конфигурация архива для пользователя задания агента SQL, но мы рекомендуем указать другую учетную запись службы домена, чтобы программа установки могла предоставить вам для него минимально необходимый уровень привилегий.</span><span class="sxs-lookup"><span data-stu-id="a98dd-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="a98dd-194">При нажатии кнопки "Далее" будет выполнена другая круглая проверка, и появится сообщение о каких – либо проблемах.</span><span class="sxs-lookup"><span data-stu-id="a98dd-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="a98dd-195">После успешного завершения проверки установщик перейдет на страницу конфигурации портала.</span><span class="sxs-lookup"><span data-stu-id="a98dd-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="a98dd-196">На странице Конфигурация портала введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a98dd-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="a98dd-197">**QoE Архивация сервера SQL Server:** Имя экземпляра сервера SQL Server, на котором расположена база данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="a98dd-198">Обратите внимание, что в отличие от страницы Конфигурация архивации QoE и страницы Конфигурация куба, имя компьютера не фиксируется и должно быть указано.</span><span class="sxs-lookup"><span data-stu-id="a98dd-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="a98dd-199">Если для установки выбран компонент архивации QoE, это поле будет предварительно заполнено значением, указанным на странице конфигурации архивации QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="a98dd-200">**Сервер анализа кубов:** Имя экземпляра службы SQL Server Analysis Service, где расположен куб.</span><span class="sxs-lookup"><span data-stu-id="a98dd-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="a98dd-201">Если для установки выбран компонент Куба, это поле будет предварительно заполнено значением, указанным на странице конфигурации куба.</span><span class="sxs-lookup"><span data-stu-id="a98dd-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="a98dd-202">**База данных SQL Server:** Имя экземпляра SQL Server, на котором будет создана база данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="a98dd-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="a98dd-203">Если имя экземпляра сервера SQL Server, на котором находится база данных архива QoE, было предоставлено ранее в настройке (в других компонентах), это поле будет предварительно заполнено именем экземпляра SQL Server резервной копии QoE.</span><span class="sxs-lookup"><span data-stu-id="a98dd-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="a98dd-204">Это может быть любой экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a98dd-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="a98dd-205">**База данных репозитория:** По умолчанию параметру присвоено значение "создать новую базу данных".</span><span class="sxs-lookup"><span data-stu-id="a98dd-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="a98dd-206">Так как обновление базы данных репозитория не поддерживается, единственным случаем использования параметра "использовать существующую базу данных" является тот случай, если существующая БД репозитория имеет ту же схему, что и сборка, которую нужно установить.</span><span class="sxs-lookup"><span data-stu-id="a98dd-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="a98dd-207">**Пользователь пула приложений IIS — пароль имени &amp; пользователя:** Учетная запись, в которой должен выполняться пул приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="a98dd-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="a98dd-208">Поля "имя пользователя" и "пароль" будут недоступны, если выбраны встроенные системные учетные записи.</span><span class="sxs-lookup"><span data-stu-id="a98dd-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="a98dd-209">Эти поля будут включены только в том случае, если в раскрывающемся списке выбрано значение "другое", чтобы пользователь мог ввести данные учетной записи службы домена.</span><span class="sxs-lookup"><span data-stu-id="a98dd-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="a98dd-210">При нажатии кнопки "Далее" для обеспечения доступности экземпляров SQL Server с помощью предоставленных учетных данных и предоставления доступа к службам IIS на компьютере будет выполняться заключительный круглый круг проверки.</span><span class="sxs-lookup"><span data-stu-id="a98dd-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="a98dd-211">После успешного завершения проверки Установщик продолжит настройку.</span><span class="sxs-lookup"><span data-stu-id="a98dd-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="a98dd-212">По завершении работы установщика, скорее всего, выполнение задания агента SQL Server будет выполняться при первой загрузке данных QoE и обработке куба.</span><span class="sxs-lookup"><span data-stu-id="a98dd-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="a98dd-213">В зависимости от количества данных в QoE портал не сможет получить доступ к данным, пока они не будут доступны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="a98dd-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="a98dd-214">Чтобы проверить состояние загрузки данных и обработки куба, перейдите к `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="a98dd-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="a98dd-215">Обратите внимание, что URL-адрес для проверки состояния при обработке куба задается с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="a98dd-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="a98dd-216">Если вы ввели "работоспособность", URL-адрес не будет работать.</span><span class="sxs-lookup"><span data-stu-id="a98dd-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="a98dd-217">Необходимо ввести "Health" в конце URL-адреса с помощью прописной буквы "р".</span><span class="sxs-lookup"><span data-stu-id="a98dd-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="a98dd-218">Подробные сообщения журнала будут отображаться, если включен режим отладки.</span><span class="sxs-lookup"><span data-stu-id="a98dd-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="a98dd-219">Чтобы включить режим отладки, перейдите на **%Системдриве%\програм Филес\скипе для Business 2015 ккд\коедатасервице\веб.конфиг**и обновите следующую строку, чтобы установить значение **Истина**.</span><span class="sxs-lookup"><span data-stu-id="a98dd-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="a98dd-220">Главная страница портала доступна через `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="a98dd-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="a98dd-221">Управление доступом пользователей к порталу</span><span class="sxs-lookup"><span data-stu-id="a98dd-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="a98dd-222">Для управления авторизацией пользователей на портале рекомендуется использовать URL-авторизацию, которая была представлена в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="a98dd-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="a98dd-223">Дополнительные сведения о безопасности IIS можно найти в разделе [сведения об авторизации URL-адреса iis 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="a98dd-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="a98dd-224">Любой веб-сайт или веб-приложение наследуют авторизацию URL-адреса по умолчанию, настроенную для всей службы IIS (обычно это разрешено для всех пользователей).</span><span class="sxs-lookup"><span data-stu-id="a98dd-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="a98dd-225">Если доступ к порталу должен быть более строгим, администраторы могут предоставить доступ к определенной группе пользователей, изменив "правила авторизации".</span><span class="sxs-lookup"><span data-stu-id="a98dd-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Развертывание мониторинга качества вызовов - Правила авторизации в IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="a98dd-227">Значок "правила авторизации" не следует путать с параметром "авторизация .NET" в разделе ASP.NET, который является другим механизмом проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a98dd-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="a98dd-228">Администраторы должны сначала удалить унаследованное правило "разрешить все пользователи".</span><span class="sxs-lookup"><span data-stu-id="a98dd-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="a98dd-229">Это предотвратит доступ к порталу для пользователей, не имеющих разрешения.</span><span class="sxs-lookup"><span data-stu-id="a98dd-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Развертывание CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="a98dd-231">Затем администраторы должны добавить новые правила разрешения и предоставить определенным пользователям разрешение на доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="a98dd-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="a98dd-232">Рекомендуется создать локальную группу с именем "Ккдпорталусерс" для управления пользователями.</span><span class="sxs-lookup"><span data-stu-id="a98dd-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Развертывание панели мониторинга качества вызовов](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="a98dd-234">Сведения о конфигурации хранятся в файле Web. config, расположенном в физическом каталоге портала.</span><span class="sxs-lookup"><span data-stu-id="a98dd-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="a98dd-235">Следующий этап — настроить информационную панель CQD.</span><span class="sxs-lookup"><span data-stu-id="a98dd-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="a98dd-236">После того как пользователи проверяют подлинность IIS, они должны иметь разрешения на доступ к каталогу CQD для доступа к содержимому веб-портала.</span><span class="sxs-lookup"><span data-stu-id="a98dd-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="a98dd-237">Списки ACL можно изменить на вкладке "безопасность" в свойствах каталога CQD, чтобы добавить отдельных пользователей или группы; Однако рекомендуемый подход состоит в том, чтобы оставить разрешения на доступ к файлу нетронутыми.</span><span class="sxs-lookup"><span data-stu-id="a98dd-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="a98dd-238">Вместо этого измените параметр IIS так, чтобы он использовал рабочий процесс IIS для доступа к каталогу CQD вне зависимости от того, какой пользователь прошел проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="a98dd-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a98dd-239">Важно изменить этот параметр только для приложения CQD, а не для двух приложений API: Коедатасервице и Коерепоситорисервице.</span><span class="sxs-lookup"><span data-stu-id="a98dd-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="a98dd-240">Настройка доступа к файлам для CQD (панель мониторинга)</span><span class="sxs-lookup"><span data-stu-id="a98dd-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="a98dd-241">Откройте редактор конфигураций для CQD.</span><span class="sxs-lookup"><span data-stu-id="a98dd-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="a98dd-243">В разделе Раздел выберите **System., сервер или серверрунтиме**.</span><span class="sxs-lookup"><span data-stu-id="a98dd-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="a98dd-245">Измените Аусентикатедусероверриде на **усеворкерпроцессусер**.</span><span class="sxs-lookup"><span data-stu-id="a98dd-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов - Редактор конфигурации](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="a98dd-247">Нажмите кнопку **Применить** в правой части страницы.</span><span class="sxs-lookup"><span data-stu-id="a98dd-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="a98dd-248">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a98dd-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="a98dd-249">В CQD не отображаются данные после развертывания</span><span class="sxs-lookup"><span data-stu-id="a98dd-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="a98dd-250">Может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="a98dd-250">You may receive the following error:</span></span>

<span data-ttu-id="a98dd-251">*Не удалось выполнить запрос при выполнении этого куба. С помощью редактора запросов измените запрос и устраните все проблемы. Также убедитесь в том, что куб доступен.*</span><span class="sxs-lookup"><span data-stu-id="a98dd-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="a98dd-252">Это означает, что куб должен обрабатываться в службах SQL Server Analysis Services перед использованием в CQD.</span><span class="sxs-lookup"><span data-stu-id="a98dd-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="a98dd-253">Вы можете устранить эту проблему, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a98dd-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="a98dd-254">Откройте центр управления SQL и выберите пункт **службы Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a98dd-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="a98dd-255">Разверните объект **коекубе** , выберите **QoE метрику**, щелкните правой кнопкой мыши и выберите пункт **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="a98dd-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="a98dd-256">Если это возвращает пустой браузер, куб еще не был выполнен.</span><span class="sxs-lookup"><span data-stu-id="a98dd-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="a98dd-257">Щелкните правой кнопкой мыши **QoE метрика** ангаин и выберите пункт **процесс**.</span><span class="sxs-lookup"><span data-stu-id="a98dd-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="a98dd-258">После завершения обработки щелкните объект правой кнопкой мыши и нажмите кнопку **Обзор** , чтобы убедиться в том, что страница браузера теперь содержит данные.</span><span class="sxs-lookup"><span data-stu-id="a98dd-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="a98dd-259">У пользователей возникли проблемы со входом, так как установщик не может создать правильные параметры в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="a98dd-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="a98dd-260">В редких случаях программа установки не может создать правильные параметры в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="a98dd-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="a98dd-261">Для того чтобы пользователи могли входить в CQD, необходимо изменить ручной режим.</span><span class="sxs-lookup"><span data-stu-id="a98dd-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="a98dd-262">Если пользователям не удается войти в систему, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a98dd-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="a98dd-263">Откройте диспетчер IIS и перейдите на веб-сайт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a98dd-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="a98dd-265">Щелкните "Проверка подлинности".</span><span class="sxs-lookup"><span data-stu-id="a98dd-265">Click on "Authentication".</span></span> <span data-ttu-id="a98dd-266">Если "Анонимная проверка подлинности", "олицетворение", "Проверка подлинности формы" и "Проверка подлинности Windows" не соответствуют указанным ниже параметрам, вручную измените их в соответствии с указанными ниже параметрами.</span><span class="sxs-lookup"><span data-stu-id="a98dd-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="a98dd-267">Все остальные механизмы проверки подлинности должны быть отключены.</span><span class="sxs-lookup"><span data-stu-id="a98dd-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="a98dd-269">В разделе "Проверка подлинности Windows" щелкните элемент "Дополнительные параметры" в правой части экрана.</span><span class="sxs-lookup"><span data-stu-id="a98dd-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="a98dd-271">Установите флажок "Расширенная защита" и установите флажок "включить режим проверки подлинности в режиме ядра".</span><span class="sxs-lookup"><span data-stu-id="a98dd-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="a98dd-273">Повторите описанные выше действия для каждой из записей "CQD", "Коедатасервице" и "Коерепоситорисервице" под заголовком "веб-сайт по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="a98dd-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="a98dd-274">Для привязок портов HTTP и HTTPS установщик создает привязки портов по умолчанию для номеров портов (порт 80 для HTTP и порт 443 для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="a98dd-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="a98dd-275">Если на компьютере, на котором используются эти привязки, есть другой веб-сайт, произойдет конфликт и поведение IIS невозможно предсказать.</span><span class="sxs-lookup"><span data-stu-id="a98dd-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="a98dd-276">Лучший способ избежать этой проблемы — убедиться, что другие веб-сайты не сопоставляются с портами 80 и 443 перед установкой CQD.</span><span class="sxs-lookup"><span data-stu-id="a98dd-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="a98dd-277">Чтобы включить SSL/TLS в IIS и принудительно подключить пользователей с помощью протокола HTTPS, а не HTTP, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a98dd-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="a98dd-278">Настройка уровня Secure Sockets Layer в службах IIS: [Настройка уровня защищенных сокетов в службах IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a98dd-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="a98dd-279">После этого замените `http` на `https`.</span><span class="sxs-lookup"><span data-stu-id="a98dd-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="a98dd-280">Инструкции по включению TLS в подключениях SQL Server приведены [в разделе Включение шифрования SSL для экземпляра SQL Server с помощью консоли управления (Майкрософт](https://support.microsoft.com/en-us/kb/316898/)).</span><span class="sxs-lookup"><span data-stu-id="a98dd-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="a98dd-281">Не удается выполнить синхронизацию Куба</span><span class="sxs-lookup"><span data-stu-id="a98dd-281">Cube Sync Fails</span></span>

<span data-ttu-id="a98dd-282">Коеметрикс может содержать некоторые недопустимые записи на основе часов конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a98dd-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="a98dd-283">Если значение "отклонение по времени" превышает 60 ИРС, импорт Куба завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="a98dd-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="a98dd-284">Проверьте минимальное и максимальное время начала и окончания с помощью параметров, указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="a98dd-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="a98dd-285">Найдите и удалите записи в прошлом и более отдаленных, они могут быть недоступными, и они будут разбивать процессы синхронизации.</span><span class="sxs-lookup"><span data-stu-id="a98dd-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="a98dd-286">Выберите мин (StartTime) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="a98dd-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="a98dd-287">Выберите "Макс (StartTime)" из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="a98dd-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="a98dd-288">Выберите мин (EndTime) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="a98dd-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="a98dd-289">Выберите MAX (EndTime) из Ккдпартитионедстреамвиев</span><span class="sxs-lookup"><span data-stu-id="a98dd-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="a98dd-290">Задачи после установки</span><span class="sxs-lookup"><span data-stu-id="a98dd-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="a98dd-291">Импорт зданий и сетей</span><span class="sxs-lookup"><span data-stu-id="a98dd-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="a98dd-292">После установки CQD выполните указанные ниже действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="a98dd-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="a98dd-293">Определение типов зданий (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a98dd-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="a98dd-294">Определение типов владельцев (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a98dd-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="a98dd-295">Определение типов сетей (настоятельно рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a98dd-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="a98dd-296">Импорт зданий (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a98dd-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="a98dd-297">Импорт подсетей (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a98dd-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="a98dd-298">Определение типов здания</span><span class="sxs-lookup"><span data-stu-id="a98dd-298">Define Building Types</span></span>

<span data-ttu-id="a98dd-299">Типы сборки используются для описания различных определений зданий или типов в Организации.</span><span class="sxs-lookup"><span data-stu-id="a98dd-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a98dd-300">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a98dd-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a98dd-301">Примеры</span><span class="sxs-lookup"><span data-stu-id="a98dd-301">Examples</span></span>
  
- <span data-ttu-id="a98dd-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="a98dd-302">Headquarters</span></span>
    
- <span data-ttu-id="a98dd-303">Удаленный Office</span><span class="sxs-lookup"><span data-stu-id="a98dd-303">Remote Office</span></span>
    
- <span data-ttu-id="a98dd-304">Совместная работа в совместных ресурсах</span><span class="sxs-lookup"><span data-stu-id="a98dd-304">Joint-venture location</span></span>
    
  <span data-ttu-id="a98dd-305">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="a98dd-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="a98dd-306">Параметры Буилдингтипеид и Буилдингтипедеск являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="a98dd-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="a98dd-307">Определение типов владельцев для создания</span><span class="sxs-lookup"><span data-stu-id="a98dd-307">Define Building Ownership Types</span></span>

<span data-ttu-id="a98dd-308">Типы владения используются для различения владельцев и арендованных активов.</span><span class="sxs-lookup"><span data-stu-id="a98dd-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a98dd-309">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a98dd-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a98dd-310">Примеры</span><span class="sxs-lookup"><span data-stu-id="a98dd-310">Examples</span></span>
  
- <span data-ttu-id="a98dd-311">Аренда Contoso не использовалась без&amp;повторения</span><span class="sxs-lookup"><span data-stu-id="a98dd-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="a98dd-312">Аренда аренды Contoso (&amp;н)</span><span class="sxs-lookup"><span data-stu-id="a98dd-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="a98dd-313">Владелец contoso</span><span class="sxs-lookup"><span data-stu-id="a98dd-313">Contoso Owned</span></span>
    
- <span data-ttu-id="a98dd-314">Подразделение на аренду</span><span class="sxs-lookup"><span data-stu-id="a98dd-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="a98dd-315">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="a98dd-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a98dd-316">Параметры Овнершиптипеид и Овнершиптипедеск являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="a98dd-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="a98dd-317">Определение сетевых имен</span><span class="sxs-lookup"><span data-stu-id="a98dd-317">Define Network Names</span></span>

<span data-ttu-id="a98dd-318">Типы сетей используются для описания различных типов сетей в Организации.</span><span class="sxs-lookup"><span data-stu-id="a98dd-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="a98dd-319">Это позволяет отфильтровать (или отфильтровать) определенные типы сетей.</span><span class="sxs-lookup"><span data-stu-id="a98dd-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a98dd-320">Настоятельно рекомендуется определять сетевые имена, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="a98dd-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="a98dd-321">Если вы решили не определять сетевые имена, убедитесь, что каждый элемент Ккднетворк имеет Буилдингид 0.</span><span class="sxs-lookup"><span data-stu-id="a98dd-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="a98dd-322">Примеры</span><span class="sxs-lookup"><span data-stu-id="a98dd-322">Examples</span></span>
  
- <span data-ttu-id="a98dd-323">VPN;</span><span class="sxs-lookup"><span data-stu-id="a98dd-323">VPN</span></span>
    
- <span data-ttu-id="a98dd-324">ЛАБОРАТОРИИ</span><span class="sxs-lookup"><span data-stu-id="a98dd-324">LAB</span></span>
    
  <span data-ttu-id="a98dd-325">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="a98dd-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="a98dd-326">Параметры Нетворкнамеид и Нетворкнаме являются обязательными, но рекомендуется использовать параметр Нетворктипе.</span><span class="sxs-lookup"><span data-stu-id="a98dd-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="a98dd-327">Импорт зданий</span><span class="sxs-lookup"><span data-stu-id="a98dd-327">Import Buildings</span></span>

<span data-ttu-id="a98dd-328">Импорт зданий позволяет вам создать конкретные аналитические данные (некачественные звонки по зданиям в сетях Wi-Fi и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a98dd-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a98dd-329">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a98dd-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a98dd-330">Перед импортом нового здания вы уже должны иметь предварительно определенную Буилдингкэй.</span><span class="sxs-lookup"><span data-stu-id="a98dd-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="a98dd-331">Для этого выбери команду SQL "SELECT MAX (Буилдингкэй) FROM Ккдбуилдинг" для определения текущего значения и добавления 1 к результату.</span><span class="sxs-lookup"><span data-stu-id="a98dd-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="a98dd-332">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="a98dd-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a98dd-333">Параметры Буилдингкэй, Буилдингнаме, Буилдингшортнаме, Овнершиптипеид и Буилдингтипеид являются обязательными, но другие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="a98dd-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="a98dd-334">Импорт подсетей</span><span class="sxs-lookup"><span data-stu-id="a98dd-334">Import Subnets</span></span>

<span data-ttu-id="a98dd-335">Импорт зданий позволяет вам создать конкретные аналитические данные (некачественные звонки по зданиям в сетях Wi-Fi и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a98dd-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a98dd-336">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a98dd-336">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="a98dd-337">Импортируйте подсети и сопоставьте их с строениями, импортированными на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="a98dd-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="a98dd-338">Если вы решили не заполнять Нетворкнаме, убедитесь, что каждая запись в этой таблице использует Нетворкнамеид 0.</span><span class="sxs-lookup"><span data-stu-id="a98dd-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="a98dd-339">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="a98dd-339">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="a98dd-340">Параметры Network и Упдатеддате являются обязательными, но другие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="a98dd-340">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="a98dd-341">Необязательно: BSSID</span><span class="sxs-lookup"><span data-stu-id="a98dd-341">Optional: BSSID</span></span>

<span data-ttu-id="a98dd-342">Заполнение BSSID-информации обеспечивает дополнительную корреляцию потоков WiFi с помощью контроллера или радио.</span><span class="sxs-lookup"><span data-stu-id="a98dd-342">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="a98dd-343">Это дополнение к фильтрации по зданиям или подсетям.</span><span class="sxs-lookup"><span data-stu-id="a98dd-343">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="a98dd-344">**Пример синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="a98dd-344">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="a98dd-345">**Сведения о Ккдбссидтабле**</span><span class="sxs-lookup"><span data-stu-id="a98dd-345">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="a98dd-346">**Как показано в CQD**</span><span class="sxs-lookup"><span data-stu-id="a98dd-346">**As shown in CQD**</span></span>|<span data-ttu-id="a98dd-347">**Таблица Ккдбссид**</span><span class="sxs-lookup"><span data-stu-id="a98dd-347">**CQDBssid Table**</span></span>|<span data-ttu-id="a98dd-348">**Примеры входных данных**</span><span class="sxs-lookup"><span data-stu-id="a98dd-348">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a98dd-349">Ннаме AP</span><span class="sxs-lookup"><span data-stu-id="a98dd-349">Ap NName</span></span>  <br/> |<span data-ttu-id="a98dd-350">ПРОФИЛЯ</span><span class="sxs-lookup"><span data-stu-id="a98dd-350">AP</span></span>  <br/> |<span data-ttu-id="a98dd-351">AP1</span><span class="sxs-lookup"><span data-stu-id="a98dd-351">AP1</span></span>  <br/> |
|<span data-ttu-id="a98dd-352">ббссид</span><span class="sxs-lookup"><span data-stu-id="a98dd-352">BBssid</span></span>  <br/> |<span data-ttu-id="a98dd-353">BSS</span><span class="sxs-lookup"><span data-stu-id="a98dd-353">BSS</span></span>  <br/> |<span data-ttu-id="a98dd-354">00-00-00-00-00-00 (необходимо использовать фформат с разделителями)</span><span class="sxs-lookup"><span data-stu-id="a98dd-354">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="a98dd-355">Контроллер</span><span class="sxs-lookup"><span data-stu-id="a98dd-355">Controller</span></span>  <br/> |<span data-ttu-id="a98dd-356">Building</span><span class="sxs-lookup"><span data-stu-id="a98dd-356">Building</span></span>  <br/> |<span data-ttu-id="a98dd-357">Аруба AP 7</span><span class="sxs-lookup"><span data-stu-id="a98dd-357">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="a98dd-358">Device</span><span class="sxs-lookup"><span data-stu-id="a98dd-358">Device</span></span>  <br/> |<span data-ttu-id="a98dd-359">ess</span><span class="sxs-lookup"><span data-stu-id="a98dd-359">ess</span></span>  <br/> |<span data-ttu-id="a98dd-360">Controller1</span><span class="sxs-lookup"><span data-stu-id="a98dd-360">Controller1</span></span>  <br/> |
|<span data-ttu-id="a98dd-361">Переключатель</span><span class="sxs-lookup"><span data-stu-id="a98dd-361">Radio</span></span>  <br/> |<span data-ttu-id="a98dd-362">phy</span><span class="sxs-lookup"><span data-stu-id="a98dd-362">phy</span></span>  <br/> |<span data-ttu-id="a98dd-363">бгн</span><span class="sxs-lookup"><span data-stu-id="a98dd-363">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="a98dd-364">Обработка импортированных данных</span><span class="sxs-lookup"><span data-stu-id="a98dd-364">Processing the imported data</span></span>

<span data-ttu-id="a98dd-365">По умолчанию после импорта данных из сборки или сети он будет применяться только к записям, созданным после этого момента времени.</span><span class="sxs-lookup"><span data-stu-id="a98dd-365">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="a98dd-366">Чтобы пометить все предыдущие записи с новыми данными, необходимо выполнить хранимую процедуру Ккдупдатебуилдинг, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a98dd-366">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="a98dd-367">Укажите дату первой записи (с помощью команды SELECT MIN (StartTime) FROM Ккдпартитионедстреамвиев SQL), EndDate завтрашнего дня, а затем NULL для последних двух значений.</span><span class="sxs-lookup"><span data-stu-id="a98dd-367">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="a98dd-368">После того как данные будут связаны с данными потока, куб служб SSIS должен повторно обработать все записи.</span><span class="sxs-lookup"><span data-stu-id="a98dd-368">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="a98dd-369">Это также применимо при массовом добавлении данных BSSID и ISP.</span><span class="sxs-lookup"><span data-stu-id="a98dd-369">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="a98dd-370">Убедитесь, что выбран параметр "процесс полон".</span><span class="sxs-lookup"><span data-stu-id="a98dd-370">Ensure that "Process Full" is selected.</span></span>
  

