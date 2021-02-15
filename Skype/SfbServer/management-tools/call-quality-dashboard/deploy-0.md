---
title: Развертывание панели мониторинга качества звонков для Skype для бизнеса Server
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
description: Сводка. Сведения о процессе развертывания панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 797288428530a055987d8b0a8e1ebf6a9e8b9dcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832719"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="fdeca-104">Развертывание панели мониторинга качества звонков для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fdeca-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="fdeca-105">**Сводка:** Узнайте о процессе развертывания панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="fdeca-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="fdeca-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fdeca-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="fdeca-107">Обзор развертывания</span><span class="sxs-lookup"><span data-stu-id="fdeca-107">Deployment Overview</span></span>

<span data-ttu-id="fdeca-108">Панель мониторинга качества вызовов (CQD) состоит из трех основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="fdeca-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="fdeca-109">**Архивная** база данных, в которой реплицированы и хранятся данные о качестве работы.</span><span class="sxs-lookup"><span data-stu-id="fdeca-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="fdeca-110">**Куб,** где данные из базы данных архива QoE агрегируются для оптимизированного и быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="fdeca-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="fdeca-111">**Портал,** где пользователи могут легко запрашивать и визуализировать данные о QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Компоненты CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="fdeca-113">Процесс настройки архива QoE включает в себя создание базы данных архива QoE, развертывание хранимой процедуры SQL Server, которая переместит данные из базы данных показателей качества качества в архивную базу данных качества и настройку задания агента SQL Server для выполнения хранимой процедуры с регулярным интервалом.</span><span class="sxs-lookup"><span data-stu-id="fdeca-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="fdeca-114">Развертывание куба получает от пользователя сведения о расположении архива QoE, развертывает куб и настраивает обычное задание агента SQL Server, которое регулярно обновляет куб.</span><span class="sxs-lookup"><span data-stu-id="fdeca-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="fdeca-115">При установке портала создается база данных репозитория, в которой хранится сопоставление пользователей CQD с отчетами и запросами каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="fdeca-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="fdeca-116">Затем настраивается веб-приложение IIS, которое является панелью мониторинга, где пользователи могут видеть предварительно определенный набор отчетов, а также настраивать и создавать собственные запросы для визуализации данных из куба.</span><span class="sxs-lookup"><span data-stu-id="fdeca-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="fdeca-117">Установка портала создает два дополнительных веб-приложения, которые предоставляет пользователям программный доступ к репозиторию и кубу.</span><span class="sxs-lookup"><span data-stu-id="fdeca-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="fdeca-118">(Эти API также используются внутри панели мониторинга.)</span><span class="sxs-lookup"><span data-stu-id="fdeca-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="fdeca-119">**Этап**</span><span class="sxs-lookup"><span data-stu-id="fdeca-119">**Phase**</span></span>|<span data-ttu-id="fdeca-120">**Действия**</span><span class="sxs-lookup"><span data-stu-id="fdeca-120">**Steps**</span></span>|<span data-ttu-id="fdeca-121">**Роли и членство в группах**</span><span class="sxs-lookup"><span data-stu-id="fdeca-121">**Roles and group membership**</span></span>|<span data-ttu-id="fdeca-122">**Документация**</span><span class="sxs-lookup"><span data-stu-id="fdeca-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fdeca-123">Установите необходимое оборудование и программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="fdeca-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="fdeca-124">Выберите конфигурацию CQD и выберите SQL Server, из которого выполняется установка.</span><span class="sxs-lookup"><span data-stu-id="fdeca-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="fdeca-125">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="fdeca-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="fdeca-126">Раздел "Требования перед установкой" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fdeca-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="fdeca-127">Установите CQD.</span><span class="sxs-lookup"><span data-stu-id="fdeca-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="fdeca-128">Запустите MSI после документа развертывания.</span><span class="sxs-lookup"><span data-stu-id="fdeca-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="fdeca-129">Для выполнения установки учетная запись установки должна быть пользователем домена, который является членом локальной группы администраторов и имеет доступ на чтение к базе данных метрик качества качества работы на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="fdeca-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="fdeca-130">Разделы "Учетные записи и этапы развертывания" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fdeca-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="fdeca-131">Предоставление доступа пользователю.</span><span class="sxs-lookup"><span data-stu-id="fdeca-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="fdeca-132">Для управления авторизацией пользователей на портале рекомендуется использовать авторизацию URL-адресов, которая была представлена в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="fdeca-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="fdeca-133">Дополнительные сведения см. [в теме "Understanding IIS 7.0 URL Authorization" (Авторизация URL-адресов IIS 7.0).](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="fdeca-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="fdeca-134">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="fdeca-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="fdeca-135">Управление доступом пользователей для раздела "Портал" в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fdeca-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="fdeca-136">Необязательный. Предоставление сведений о сопоставлении подсети.</span><span class="sxs-lookup"><span data-stu-id="fdeca-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="fdeca-137">Заполнять таблицы сопоставления сети и построения в базе данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="fdeca-138">Учетная запись с доступом на запись к базе данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="fdeca-139">Раздел "Сведения о подсети" в документации пользователя.</span><span class="sxs-lookup"><span data-stu-id="fdeca-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="fdeca-140">Развертывание панели мониторинга качества вызовов включает настройку инфраструктуры и установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="fdeca-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="fdeca-141">Процесс описан в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="fdeca-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="fdeca-142">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="fdeca-142">Deployment Steps</span></span>

1. <span data-ttu-id="fdeca-143">Скопируйте CallQualityDashboard.msi на компьютер, на котором должен быть установлен компонент архивной базы данных CQD (это компьютер, на котором SQL Server установлено).</span><span class="sxs-lookup"><span data-stu-id="fdeca-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="fdeca-144">Выполните MSI (Windows запросит запуск с привилегиями администратора, сделайте это).</span><span class="sxs-lookup"><span data-stu-id="fdeca-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="fdeca-145">Примите eula.</span><span class="sxs-lookup"><span data-stu-id="fdeca-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="fdeca-146">Выберите папку назначения, в которой будут расположены файлы, связанные с компонентами панели мониторинга качества вызовов, или примите расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fdeca-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="fdeca-147">Выберите все функции.</span><span class="sxs-lookup"><span data-stu-id="fdeca-147">Select all features.</span></span>
    
6. <span data-ttu-id="fdeca-148">На странице "Конфигурация архива QoE" указите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fdeca-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="fdeca-149">**Показатели качества SQL Server:** SQL Server экземпляра, где расположена DB метрик качества связи (это будет источник данных).</span><span class="sxs-lookup"><span data-stu-id="fdeca-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="fdeca-150">**Имя архива SQL Server QoE:** Это поле только для чтения и фиксировано к полному доменному имени локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="fdeca-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="fdeca-151">Архивную DB можно установить только на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdeca-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="fdeca-152">**Экземпляр архива QoE SQL Server:** Локальное SQL Server экземпляра, для которого будет создана архивная DB.</span><span class="sxs-lookup"><span data-stu-id="fdeca-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="fdeca-153">Чтобы использовать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="fdeca-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="fdeca-154">Чтобы использовать именуемую SQL Server, укажите имя экземпляра (например, имя после \" ").</span><span class="sxs-lookup"><span data-stu-id="fdeca-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="fdeca-155">**Архивная база данных QoE:** По умолчанию для этого параметра установлено значение "Создать новую базу данных".</span><span class="sxs-lookup"><span data-stu-id="fdeca-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="fdeca-156">Поскольку обновление архивной базы данных не поддерживается, единственным обстоятельствам, при котором можно использовать параметр "Использовать существующую базу данных", является использование той же схемы существующей базы данных архива, что и устанавливаемая сборка.</span><span class="sxs-lookup"><span data-stu-id="fdeca-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="fdeca-157">**Каталог файлов базы данных:** Путь к расположению файлов базы данных (MDF и LDF) для архивной базы данных.</span><span class="sxs-lookup"><span data-stu-id="fdeca-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="fdeca-158">Он должен быть на диске (HDD2 в рекомендуемой конфигурации оборудования) отдельно от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fdeca-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="fdeca-159">Обратите внимание, что так как имена файлов исправлены при установке, во избежание потенциальных конфликтов рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="fdeca-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="fdeca-160">**Используйте несколько разделов:** По умолчанию установлено значение "Multiple partition", для которого требуется выпуск Business Intelligence или enterprise SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdeca-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="fdeca-161">В стандартном выпуске выберите параметр "Один раздел".</span><span class="sxs-lookup"><span data-stu-id="fdeca-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="fdeca-162">Обратите внимание, что производительность обработки куба может повлиять на работу с одним разделом.</span><span class="sxs-lookup"><span data-stu-id="fdeca-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="fdeca-163">Выбор параметра "Использовать несколько разделов" нельзя изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="fdeca-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="fdeca-164">Чтобы изменить его, необходимо сначала сменить функцию куба, а затем переустановить ее с помощью параметра "Изменить" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="fdeca-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="fdeca-165">**Каталог файлов раздела:** Путь к разделу базы данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="fdeca-166">Он должен быть на диске (HDD3 в рекомендуемой конфигурации оборудования) отдельно от диска ОС и SQL файлов журнала базы данных.</span><span class="sxs-lookup"><span data-stu-id="fdeca-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="fdeca-167">Обратите внимание, что так как имена файлов исправлены при установке, во избежание потенциальных конфликтов рекомендуется использовать пустой каталог без файлов.</span><span class="sxs-lookup"><span data-stu-id="fdeca-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="fdeca-168">**SQL агента — имя пользователя &amp; Пароль:** имя и пароль учетной записи службы домена (с маской), которые будут использоваться для запуска шага "Данные архива качества обслуживания" задания агента SQL Server (которое будет запускать хранимую процедуру для извлечения данных из DB показателей качества обслуживания в архивную DB, поэтому эта учетная запись должна иметь доступ на чтение к DB метрик качества обслуживания, как указано в разделе "Учетные записи".</span><span class="sxs-lookup"><span data-stu-id="fdeca-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="fdeca-169">Эта учетная запись также должна иметь вход в архив QoE SQL Server экземпляре).</span><span class="sxs-lookup"><span data-stu-id="fdeca-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="fdeca-170">Учетная запись, в SQL Server, например NT SERVICE\MSSQLSERVER, должна иметь доступ к каталогам, заданным выше, для успешной установки.</span><span class="sxs-lookup"><span data-stu-id="fdeca-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="fdeca-171">Подробные сведения см. в подсистеме настройки разрешений [файловой системы для доступа к яику базы данных](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fdeca-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="fdeca-172">После нажатия кнопки "Далее" установщик выполняет проверки на наличие необходимых условий и сообщает о проблемах.</span><span class="sxs-lookup"><span data-stu-id="fdeca-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="fdeca-173">Когда все необходимые проверки будут пройдены, установщик перейдите на страницу "Конфигурация куба".</span><span class="sxs-lookup"><span data-stu-id="fdeca-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fdeca-174">Если установщик отображает предупреждение о том, что служба агента SQL Server для экземпляра архива QoE SQL Server в настоящее время не запущена, установка может продолжиться, но после установки убедитесь, что служба агента SQL запущена, и установите для типа запуска автоматический запуск запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="fdeca-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="fdeca-175">На странице "Конфигурация куба" укайте следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fdeca-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="fdeca-176">**Имя архива SQL Server QoE:** Это поле только для чтения и фиксировано к полному доменному имени локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="fdeca-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="fdeca-177">Куб можно установить только с компьютера с архивной базой данных QoE (примечание.</span><span class="sxs-lookup"><span data-stu-id="fdeca-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="fdeca-178">Куб может быть установлен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdeca-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="fdeca-179">См. ниже)</span><span class="sxs-lookup"><span data-stu-id="fdeca-179">See below)</span></span>
    
   - <span data-ttu-id="fdeca-180">**Экземпляр архива QoE SQL Server:** SQL Server экземпляра, где расположена архивная БД QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="fdeca-181">Чтобы указать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="fdeca-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="fdeca-182">Чтобы указать именуемую SQL Server экземпляра, введите имя экземпляра (например, имя после \" ").</span><span class="sxs-lookup"><span data-stu-id="fdeca-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="fdeca-183">Если для установки был выбран компонент "Архив QoE", это поле будет предварительно заполнено значением, предоставленным на странице "Конфигурация архива качества связи".</span><span class="sxs-lookup"><span data-stu-id="fdeca-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="fdeca-184">**Сервер анализа куба:** SQL Server экземпляра службы аналитики для места создания куба.</span><span class="sxs-lookup"><span data-stu-id="fdeca-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="fdeca-185">Это может быть другой компьютер, но устанавливающий пользователь должен быть членом группы администраторов сервера целевого SQL Server службы аналитики.</span><span class="sxs-lookup"><span data-stu-id="fdeca-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="fdeca-186">Дополнительные сведения о настройке разрешений администратора сервера analysis Services см. в поднаправлении разрешений администратора сервера [(службы analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="fdeca-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="fdeca-187">**Используйте несколько разделов:** По умолчанию установлено значение "Multiple partition", для которого требуется выпуск Business Intelligence или enterprise SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdeca-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="fdeca-188">В стандартном выпуске выберите параметр "Один раздел".</span><span class="sxs-lookup"><span data-stu-id="fdeca-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="fdeca-189">Обратите внимание, что производительность обработки куба может повлиять на работу с одним разделом.</span><span class="sxs-lookup"><span data-stu-id="fdeca-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="fdeca-190">Выбор параметра "Использовать несколько разделов" нельзя изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="fdeca-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="fdeca-191">Чтобы изменить его, необходимо сначала сменить функцию куба, а затем переустановить ее с помощью параметра "Изменить" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="fdeca-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="fdeca-192">**Пользователь куба — имя пользователя &amp; Пароль: имя** и пароль учетной записи службы домена (маскировать), которые запускают обработку куба.</span><span class="sxs-lookup"><span data-stu-id="fdeca-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="fdeca-193">Если для установки был выбран компонент архива качества обслуживания, это поле будет предварительно заполнено значением, предоставленным на странице "Конфигурация архива" для пользователя задания агента SQL, но мы рекомендуем указать другую учетную запись службы домена, чтобы установка предоставила ему наименее необходимые права.</span><span class="sxs-lookup"><span data-stu-id="fdeca-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="fdeca-194">При нажатии кнопки "Далее" будет выполнен еще один этап проверки, и будет отчитаться о любых проблемах.</span><span class="sxs-lookup"><span data-stu-id="fdeca-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="fdeca-195">После успешного завершения проверки установщик перейдите на страницу "Конфигурация портала".</span><span class="sxs-lookup"><span data-stu-id="fdeca-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="fdeca-196">На странице "Конфигурация портала" у вас должны быть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fdeca-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="fdeca-197">**Архив qoE SQL Server:** SQL Server экземпляра, в котором расположена база данных архива QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="fdeca-198">Обратите внимание, что в отличие от страницы "Конфигурация архива QoE" и "Конфигурация куба", имя компьютера не является фиксированным и должно быть предоставлено.</span><span class="sxs-lookup"><span data-stu-id="fdeca-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="fdeca-199">Если для установки был выбран компонент "Архив QoE", это поле будет предварительно заполнено значением, предоставленным на странице "Конфигурация архива качества связи".</span><span class="sxs-lookup"><span data-stu-id="fdeca-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="fdeca-200">**Сервер анализа куба:** SQL Server имени экземпляра службы analysis Services для того, где расположен куб.</span><span class="sxs-lookup"><span data-stu-id="fdeca-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="fdeca-201">Если для установки был выбран компонент куба, это поле будет предварительно заполнено значением, предоставленным на странице "Конфигурация куба".</span><span class="sxs-lookup"><span data-stu-id="fdeca-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="fdeca-202">**Репозиторий SQL Server:** SQL Server экземпляра, в котором будет создана база данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="fdeca-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="fdeca-203">Если имя экземпляра SQL Server, где расположена база данных архива QoE, было предоставлено ранее в установке (в других компонентах), это поле будет предварительно заполнено именем экземпляра SQL Server архива QoE.</span><span class="sxs-lookup"><span data-stu-id="fdeca-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="fdeca-204">Это может быть любой SQL Server экземпляр.</span><span class="sxs-lookup"><span data-stu-id="fdeca-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="fdeca-205">**База данных репозитория:** По умолчанию параметр имеет значение "Создать новую базу данных".</span><span class="sxs-lookup"><span data-stu-id="fdeca-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="fdeca-206">Поскольку обновление базы данных репозитория не поддерживается, единственным обстоятельствам, при котором можно использовать параметр "Использовать существующую базу данных", является то, что существующая база данных репозитория имеет ту же схему, что и устанавливаемая сборка.</span><span class="sxs-lookup"><span data-stu-id="fdeca-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="fdeca-207">**Пользователь пула приложений IIS — имя пользователя &amp; Пароль:** учетная запись, в которую должен выполняться пул приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="fdeca-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="fdeca-208">Поля "Имя пользователя" и "Пароль" будут серыми, если выбраны встроенные системные учетные записи.</span><span class="sxs-lookup"><span data-stu-id="fdeca-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="fdeca-209">Эти поля будут включены, только если в выпадаемом поле выбрано "Другое", чтобы пользователь вошел в учетную запись службы домена.</span><span class="sxs-lookup"><span data-stu-id="fdeca-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="fdeca-210">При нажатии кнопки "Далее" будет завершен заключительный этап проверки, чтобы убедиться, что экземпляры SQL Server доступны с использованием предоставленных учетных данных и что на компьютере доступны IIS.</span><span class="sxs-lookup"><span data-stu-id="fdeca-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="fdeca-211">После успешного завершения проверки установщик продолжит установку.</span><span class="sxs-lookup"><span data-stu-id="fdeca-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="fdeca-212">По инициалу установщика, скорее всего, будет SQL Server агент, который будет обрабатывать данные О КАЧЕСТВЕ и куб.</span><span class="sxs-lookup"><span data-stu-id="fdeca-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="fdeca-213">В зависимости от объема данных в QoE данные на портале пока недоступны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="fdeca-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="fdeca-214">Чтобы проверить состояние загрузки данных и обработки куба, перейдите к  `http://<machinename>/CQD/#/Health` .</span><span class="sxs-lookup"><span data-stu-id="fdeca-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="fdeca-215">Обратите внимание, что URL-адрес для проверки состояния обработки куба загрузки чувствителен к регистру.</span><span class="sxs-lookup"><span data-stu-id="fdeca-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="fdeca-216">Если ввести "health", URL-адрес не будет работать.</span><span class="sxs-lookup"><span data-stu-id="fdeca-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="fdeca-217">Необходимо ввести "Health" в конце URL-адреса с загоном H.</span><span class="sxs-lookup"><span data-stu-id="fdeca-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="fdeca-218">Подробные сообщения журнала будут показаны, если включен режим отлаживания.</span><span class="sxs-lookup"><span data-stu-id="fdeca-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="fdeca-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype for Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True:**</span><span class="sxs-lookup"><span data-stu-id="fdeca-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="fdeca-220">Главная страница портала доступна через  `http://<machinename>/CQD` .</span><span class="sxs-lookup"><span data-stu-id="fdeca-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="fdeca-221">Управление доступом пользователей для портала</span><span class="sxs-lookup"><span data-stu-id="fdeca-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="fdeca-222">Для управления авторизацией пользователей на портале рекомендуется использовать авторизацию URL-адресов, которая была представлена в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="fdeca-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="fdeca-223">Дополнительные сведения о безопасности IIS см. в сведениях об авторизации [URL-адресов IIS 7.0.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="fdeca-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="fdeca-224">Любой веб-сайт или веб-приложение наследует авторизацию URL-адреса по умолчанию, настроенную для всего IIS, которое обычно имеет значение "Разрешить всем пользователям".</span><span class="sxs-lookup"><span data-stu-id="fdeca-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="fdeca-225">Если доступ к порталу должен быть более строгим, администраторы могут предоставить доступ только определенной группе пользователей, отредактировать "Правила авторизации".</span><span class="sxs-lookup"><span data-stu-id="fdeca-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Развертывание качества вызовов — правила авторизации в IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="fdeca-227">Не следует путать значок правил авторизации с разделом "Авторизация .NET" ASP.NET, который является другим механизмом авторизации.</span><span class="sxs-lookup"><span data-stu-id="fdeca-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="fdeca-228">Сначала администраторы должны удалить унаследованные правила "Разрешить всем пользователям".</span><span class="sxs-lookup"><span data-stu-id="fdeca-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="fdeca-229">Это предотвратит доступ любых не авторизованных пользователей к порталу.</span><span class="sxs-lookup"><span data-stu-id="fdeca-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Развертывание CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="fdeca-231">Затем администраторы должны добавить новые правила разрешений и предоставить определенным пользователям разрешение на доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="fdeca-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="fdeca-232">Для управления пользователями рекомендуется создать локальная группа CQDPortalUsers.</span><span class="sxs-lookup"><span data-stu-id="fdeca-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Развертывание панели мониторинга качества звонков](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="fdeca-234">Сведения о конфигурации хранятся в web.config в физическом каталоге портала.</span><span class="sxs-lookup"><span data-stu-id="fdeca-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="fdeca-235">Следующим шагом является настройка панели мониторинга CQD.</span><span class="sxs-lookup"><span data-stu-id="fdeca-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="fdeca-236">После проверки подлинности пользователей службами IIS им необходимо иметь разрешения на доступ к контенту веб-портала в каталоге CQD.</span><span class="sxs-lookup"><span data-stu-id="fdeca-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="fdeca-237">Можно изменить ALS с помощью вкладки безопасности свойств каталога CQD, чтобы добавить отдельных пользователей или группы; Однако рекомендуется оставить разрешения файлов без сундуков.</span><span class="sxs-lookup"><span data-stu-id="fdeca-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="fdeca-238">Вместо этого измените параметр IIS, чтобы использовать рабочий процесс IIS для доступа к каталогу CQD независимо от того, какой пользователь имеет проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="fdeca-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fdeca-239">Важно изменить этот параметр только для приложения CQD, а не для двух приложений API: QoEDataService и QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="fdeca-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="fdeca-240">Настройка доступа к файлам для CQD (информационная панель)</span><span class="sxs-lookup"><span data-stu-id="fdeca-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="fdeca-241">Откройте редактор конфигурации для CQD.</span><span class="sxs-lookup"><span data-stu-id="fdeca-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="fdeca-243">В разделе выберите **system.webServer/serverRuntime.**</span><span class="sxs-lookup"><span data-stu-id="fdeca-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="fdeca-245">Измените authenticatedUserOverride на **UseWorkerProcessUser.**</span><span class="sxs-lookup"><span data-stu-id="fdeca-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов — редактор конфигураций](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="fdeca-247">Нажмите **кнопку "Применить"** в правой части страницы.</span><span class="sxs-lookup"><span data-stu-id="fdeca-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="fdeca-248">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="fdeca-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="fdeca-249">CQD не отображает данные после развертывания</span><span class="sxs-lookup"><span data-stu-id="fdeca-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="fdeca-250">Может возникнуть следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="fdeca-250">You may receive the following error:</span></span>

<span data-ttu-id="fdeca-251">*Не удалось выполнить запрос во время его выполнения в кубе. Используйте редактор запросов для изменения запроса и устранения любых проблем. Кроме того, убедитесь, что куб доступен.*</span><span class="sxs-lookup"><span data-stu-id="fdeca-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="fdeca-252">Это означает, что куб должен быть обработан в SQL Server analysis Services перед его помощью в CQD.</span><span class="sxs-lookup"><span data-stu-id="fdeca-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="fdeca-253">Чтобы устранить эту проблему, с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fdeca-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="fdeca-254">Откройте SQL Management Studio и выберите **службы Analysis Services.**</span><span class="sxs-lookup"><span data-stu-id="fdeca-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="fdeca-255">Разйдите объект **QoECube,** выберите **метрику качества,** щелкните правой кнопкой мыши и выберите **"Обзор".**</span><span class="sxs-lookup"><span data-stu-id="fdeca-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="fdeca-256">Если возвращается пустой браузер, куб еще не был продолжит работу.</span><span class="sxs-lookup"><span data-stu-id="fdeca-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="fdeca-257">Щелкните правой кнопкой **мыши метрики** качества и выберите **"Процесс".**</span><span class="sxs-lookup"><span data-stu-id="fdeca-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="fdeca-258">После завершения обработки щелкните объект правой  кнопкой мыши и выберите "Обзор", чтобы подтвердить, что на странице браузера теперь показаны данные.</span><span class="sxs-lookup"><span data-stu-id="fdeca-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="fdeca-259">Пользователи не могут войти в систему, так как установщику не удается создать правильные параметры в IIS</span><span class="sxs-lookup"><span data-stu-id="fdeca-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="fdeca-260">В редких случаях установщику не удается создать правильные параметры в IIS.</span><span class="sxs-lookup"><span data-stu-id="fdeca-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="fdeca-261">Чтобы разрешить пользователям входить в CQD, необходимо вручную изменить его.</span><span class="sxs-lookup"><span data-stu-id="fdeca-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="fdeca-262">Если у пользователей возникли проблемы с входом в систему, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fdeca-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="fdeca-263">Откройте диспетчер IIS и перейдите на веб-сайт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fdeca-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="fdeca-265">Щелкните "Проверка подлинности".</span><span class="sxs-lookup"><span data-stu-id="fdeca-265">Click on "Authentication".</span></span> <span data-ttu-id="fdeca-266">Если параметры "Анонимная проверка подлинности", "ASP.NET подмена", "Проверка подлинности формы" и "Проверка подлинности Windows" не соответствуют показанным ниже настройкам, вручную измените их в соответствие с настройками ниже.</span><span class="sxs-lookup"><span data-stu-id="fdeca-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="fdeca-267">Все остальные механизмы проверки подлинности должны быть отключены.</span><span class="sxs-lookup"><span data-stu-id="fdeca-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="fdeca-269">В области "Проверка подлинности Windows" щелкните "Дополнительные параметры" справа.</span><span class="sxs-lookup"><span data-stu-id="fdeca-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="fdeca-271">Задайте для "Расширенной защиты" действие "Принять" и установите в поле "Включить проверку подлинности в режиме ядра".</span><span class="sxs-lookup"><span data-stu-id="fdeca-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Развертывание панели мониторинга качества звонков](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="fdeca-273">Повторите вышеперечисленные действия для каждой записи "CQD", "QoEDataService" и "QoERepositoryService" ниже "Веб-сайт по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="fdeca-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="fdeca-274">Для привязок портов HTTP и HTTPS установщик создаст привязки портов на номерах портов по умолчанию (порт 80 для HTTP и порт 443 для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="fdeca-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="fdeca-275">Если на компьютере есть другой веб-сайт, использующий эти привязки, будет конфликт, и поведение IIS будет невозможно предсказать.</span><span class="sxs-lookup"><span data-stu-id="fdeca-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="fdeca-276">Лучший способ избежать этой проблемы — убедиться, что перед установкой CQD никакие другие веб-сайты не соедина с портами 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="fdeca-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="fdeca-277">Чтобы включить протокол SSL/TLS в IIS и принудительно подключить пользователей через безопасный протокол HTTPS вместо HTTP:</span><span class="sxs-lookup"><span data-stu-id="fdeca-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="fdeca-278">Настройка уровня безопасных sockets в IIS см. в подстроке "Настройка уровня secure [Sockets Layer" в IIS 7.](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fdeca-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="fdeca-279">После этого замените его на  `http` `https` .</span><span class="sxs-lookup"><span data-stu-id="fdeca-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="fdeca-280">Инструкции по включению TLS в подключениях SQL Server см. в инструкции по включению [шифрования SSL](https://support.microsoft.com/kb/316898/)для экземпляра SQL Server с помощью консоли управления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fdeca-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="fdeca-281">Сбой синхронизации куба</span><span class="sxs-lookup"><span data-stu-id="fdeca-281">Cube Sync Fails</span></span>

<span data-ttu-id="fdeca-282">QoEMetrics может содержать некоторые недопустимые записи на основе часов конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fdeca-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="fdeca-283">Если время больше 60 yrs, импорт куба не удастся.</span><span class="sxs-lookup"><span data-stu-id="fdeca-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="fdeca-284">Проверьте min и Max StartTime/EndTime, используя выборки ниже.</span><span class="sxs-lookup"><span data-stu-id="fdeca-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="fdeca-285">Искать и удалять записи в далеком и очень далеком будущем, их можно игнорировать и разбить процессы синхронизации.</span><span class="sxs-lookup"><span data-stu-id="fdeca-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="fdeca-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="fdeca-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="fdeca-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="fdeca-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="fdeca-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="fdeca-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="fdeca-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="fdeca-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="fdeca-290">Задачи после установки</span><span class="sxs-lookup"><span data-stu-id="fdeca-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="fdeca-291">Импорт зданий и сетей</span><span class="sxs-lookup"><span data-stu-id="fdeca-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="fdeca-292">После установки CQD выполните следующие задачи настройки:</span><span class="sxs-lookup"><span data-stu-id="fdeca-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="fdeca-293">Определение типов здания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fdeca-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="fdeca-294">Определение типов владения здания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fdeca-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="fdeca-295">Определение типов сети (настоятельно рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fdeca-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="fdeca-296">Импорт зданий (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fdeca-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="fdeca-297">Импорт подсетей (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fdeca-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="fdeca-298">Определение типов зданий</span><span class="sxs-lookup"><span data-stu-id="fdeca-298">Define Building Types</span></span>

<span data-ttu-id="fdeca-299">Типы зданий используются для описания различных определений или типов зданий в организации.</span><span class="sxs-lookup"><span data-stu-id="fdeca-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fdeca-300">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="fdeca-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="fdeca-301">Примеры</span><span class="sxs-lookup"><span data-stu-id="fdeca-301">Examples</span></span>
  
- <span data-ttu-id="fdeca-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="fdeca-302">Headquarters</span></span>
    
- <span data-ttu-id="fdeca-303">Удаленный офис</span><span class="sxs-lookup"><span data-stu-id="fdeca-303">Remote Office</span></span>
    
- <span data-ttu-id="fdeca-304">Совместное размещение</span><span class="sxs-lookup"><span data-stu-id="fdeca-304">Joint-venture location</span></span>
    
  <span data-ttu-id="fdeca-305">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="fdeca-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="fdeca-306">Необходимы параметры BuildingTypeId и BuildingTypeDesc.</span><span class="sxs-lookup"><span data-stu-id="fdeca-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="fdeca-307">Определение типов владения здания</span><span class="sxs-lookup"><span data-stu-id="fdeca-307">Define Building Ownership Types</span></span>

<span data-ttu-id="fdeca-308">Типы владения используются для разлиения владельцев и арендованных активов.</span><span class="sxs-lookup"><span data-stu-id="fdeca-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fdeca-309">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="fdeca-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="fdeca-310">Примеры</span><span class="sxs-lookup"><span data-stu-id="fdeca-310">Examples</span></span>
  
- <span data-ttu-id="fdeca-311">Contoso Leased non-RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="fdeca-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="fdeca-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="fdeca-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="fdeca-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="fdeca-313">Contoso Owned</span></span>
    
- <span data-ttu-id="fdeca-314">Аренда дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="fdeca-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="fdeca-315">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="fdeca-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="fdeca-316">Параметры OwnershipTypeId и OwnershipTypeDesc являются обязательной.</span><span class="sxs-lookup"><span data-stu-id="fdeca-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="fdeca-317">Определение имен сетей</span><span class="sxs-lookup"><span data-stu-id="fdeca-317">Define Network Names</span></span>

<span data-ttu-id="fdeca-318">Типы сетей используются для описания различных типов сетей в организации.</span><span class="sxs-lookup"><span data-stu-id="fdeca-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="fdeca-319">Это дает возможность отфильтровать (или отфильтровать) определенные сетевые типы.</span><span class="sxs-lookup"><span data-stu-id="fdeca-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fdeca-320">Настоятельно рекомендуется определить имена сетей, но они необязательны.</span><span class="sxs-lookup"><span data-stu-id="fdeca-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="fdeca-321">Если вы решили не определять имена сетей, убедитесь, что каждая запись CqdNetwork имеет buildingId 0.</span><span class="sxs-lookup"><span data-stu-id="fdeca-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="fdeca-322">Примеры</span><span class="sxs-lookup"><span data-stu-id="fdeca-322">Examples</span></span>
  
- <span data-ttu-id="fdeca-323">VPN</span><span class="sxs-lookup"><span data-stu-id="fdeca-323">VPN</span></span>
    
- <span data-ttu-id="fdeca-324">LAB</span><span class="sxs-lookup"><span data-stu-id="fdeca-324">LAB</span></span>
    
  <span data-ttu-id="fdeca-325">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="fdeca-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="fdeca-326">Параметры NetworkNameID и NetworkName являются обязательными, параметр NetworkType является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="fdeca-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="fdeca-327">Импорт зданий</span><span class="sxs-lookup"><span data-stu-id="fdeca-327">Import Buildings</span></span>

<span data-ttu-id="fdeca-328">Импорт зданий дает возможность получать конкретные сведения о построении (звонков низкого качества для каждого здания на WiFi/ Wired и т. д.).</span><span class="sxs-lookup"><span data-stu-id="fdeca-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fdeca-329">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="fdeca-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="fdeca-330">Перед импортом нового здания уже должен быть определен предопределен BuildingKey.</span><span class="sxs-lookup"><span data-stu-id="fdeca-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="fdeca-331">Для этого выдайте команду SELECT MAX(BuildingKey) FROM CqdBuilding SQL, чтобы определить текущее значение и добавить 1 в результат.</span><span class="sxs-lookup"><span data-stu-id="fdeca-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="fdeca-332">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="fdeca-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="fdeca-333">Параметры BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId являются обязательными, остальные параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="fdeca-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="fdeca-334">Импорт подсетей</span><span class="sxs-lookup"><span data-stu-id="fdeca-334">Import Subnets</span></span>

<span data-ttu-id="fdeca-335">Импорт зданий позволяет получать конкретные сведения о построении (неудовлетворительные звонки для каждого здания на Wi-Fi/ Wired и т. д.).</span><span class="sxs-lookup"><span data-stu-id="fdeca-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fdeca-336">Этот шаг является необязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="fdeca-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="fdeca-337">Импорт подсетей и их соотнося со зданиями, импортируемыми на последнем шаге.</span><span class="sxs-lookup"><span data-stu-id="fdeca-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="fdeca-338">Если вы решили не заполнять NetworkName, убедитесь, что каждая запись в этой таблице использует NetworkNameID 0.</span><span class="sxs-lookup"><span data-stu-id="fdeca-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="fdeca-339">Дополнительные сведения о синтаксисах SQL и параметрах панели мониторинга качества звонков см. в этой [теме.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)</span><span class="sxs-lookup"><span data-stu-id="fdeca-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="fdeca-340">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="fdeca-340">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="fdeca-341">Параметры Network и UpdatedDate являются обязательными, остальные параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="fdeca-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="fdeca-342">Необязательно: BSSID</span><span class="sxs-lookup"><span data-stu-id="fdeca-342">Optional: BSSID</span></span>

<span data-ttu-id="fdeca-343">Заполнение данных BSSID дает дополнительную корреляцию потока Wi-Fi по контроллеру или радио.</span><span class="sxs-lookup"><span data-stu-id="fdeca-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="fdeca-344">Это дополнение к фильтрации по построению или подсети.</span><span class="sxs-lookup"><span data-stu-id="fdeca-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="fdeca-345">**Пример SQL синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="fdeca-345">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="fdeca-346">**Сведения о CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="fdeca-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="fdeca-347">**Как показано в CQD**</span><span class="sxs-lookup"><span data-stu-id="fdeca-347">**As shown in CQD**</span></span>|<span data-ttu-id="fdeca-348">**Таблица CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="fdeca-348">**CQDBssid Table**</span></span>|<span data-ttu-id="fdeca-349">**Примеры входных данных**</span><span class="sxs-lookup"><span data-stu-id="fdeca-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fdeca-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="fdeca-350">Ap NName</span></span>  <br/> |<span data-ttu-id="fdeca-351">AP</span><span class="sxs-lookup"><span data-stu-id="fdeca-351">AP</span></span>  <br/> |<span data-ttu-id="fdeca-352">AP1</span><span class="sxs-lookup"><span data-stu-id="fdeca-352">AP1</span></span>  <br/> |
|<span data-ttu-id="fdeca-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="fdeca-353">BBssid</span></span>  <br/> |<span data-ttu-id="fdeca-354">BSS</span><span class="sxs-lookup"><span data-stu-id="fdeca-354">BSS</span></span>  <br/> |<span data-ttu-id="fdeca-355">00-00-00-00-00-00-00 (необходимо использовать разнородных fformat)</span><span class="sxs-lookup"><span data-stu-id="fdeca-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="fdeca-356">Контроллер</span><span class="sxs-lookup"><span data-stu-id="fdeca-356">Controller</span></span>  <br/> |<span data-ttu-id="fdeca-357">Building</span><span class="sxs-lookup"><span data-stu-id="fdeca-357">Building</span></span>  <br/> |<span data-ttu-id="fdeca-358">Аруба AP 7</span><span class="sxs-lookup"><span data-stu-id="fdeca-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="fdeca-359">Устройство</span><span class="sxs-lookup"><span data-stu-id="fdeca-359">Device</span></span>  <br/> |<span data-ttu-id="fdeca-360">ess</span><span class="sxs-lookup"><span data-stu-id="fdeca-360">ess</span></span>  <br/> |<span data-ttu-id="fdeca-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="fdeca-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="fdeca-362">Радио</span><span class="sxs-lookup"><span data-stu-id="fdeca-362">Radio</span></span>  <br/> |<span data-ttu-id="fdeca-363">phy</span><span class="sxs-lookup"><span data-stu-id="fdeca-363">phy</span></span>  <br/> |<span data-ttu-id="fdeca-364">bgn</span><span class="sxs-lookup"><span data-stu-id="fdeca-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="fdeca-365">Обработка импортируемых данных</span><span class="sxs-lookup"><span data-stu-id="fdeca-365">Processing the imported data</span></span>

<span data-ttu-id="fdeca-366">По умолчанию после импорта данных о зданиях и сетях они будут применяться только к записям, созданным после этого момента.</span><span class="sxs-lookup"><span data-stu-id="fdeca-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="fdeca-367">Чтобы пометить все предыдущие записи новыми данными, необходимо выполнить хранимую процедуру CqdUpdateBuilding, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="fdeca-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="fdeca-368">Присвойте ей дату первой записи (определите, что с помощью команды Select MIN(StartTime) FROM CqdPartitionedStreamView SQL), endDate завтра, а затем значение NULL для последних двух значений.</span><span class="sxs-lookup"><span data-stu-id="fdeca-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="fdeca-369">После связываия данных с потоками кубУ SSIS необходимо повторно обрезать все записи.</span><span class="sxs-lookup"><span data-stu-id="fdeca-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="fdeca-370">Это также применяется при массовом добавлении данных BSSID/ISP.</span><span class="sxs-lookup"><span data-stu-id="fdeca-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="fdeca-371">Убедитесь, что выбрана "Процесс заполнен".</span><span class="sxs-lookup"><span data-stu-id="fdeca-371">Ensure that "Process Full" is selected.</span></span>
  

