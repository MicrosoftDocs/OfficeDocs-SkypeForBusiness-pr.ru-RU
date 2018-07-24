---
title: Развертывание панели мониторинга качества звонков для Скайп для Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Сводка: Сведения о процессе развертывания для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: 860792fc39deed592f0d4369018cf85dd7de4a74
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988988"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="20f40-104">Развертывание панели мониторинга качества звонков для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20f40-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20f40-105">**Сводка:** Сведения о процессе развертывания для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="20f40-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="20f40-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="20f40-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="20f40-107">Общие сведения о развертывании</span><span class="sxs-lookup"><span data-stu-id="20f40-107">Deployment Overview</span></span>

<span data-ttu-id="20f40-108">Панель мониторинга качества звонков (CQD) состоит из трех основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="20f40-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="20f40-109">**Архивная база данных**, где репликации и хранятся данные качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="20f40-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="20f40-110">**Куб**, где обобщения данных из базы данных архивов качества взаимодействия для обеспечения оптимальной и быстрый доступ.</span><span class="sxs-lookup"><span data-stu-id="20f40-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="20f40-111">**Портал**, где пользователи могут создавать запросы и визуализировать данные о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Компоненты CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="20f40-113">Процесс установки для архива качества взаимодействия включает создание качества взаимодействия архивной базы данных, развертывание хранимой процедуры SQL Server, перемещение данных из источника показатели качества взаимодействия базы данных в базу данных о качестве взаимодействия архива и настройке задания агента SQL Server для выполнения хранимую процедура с заданной периодичностью.</span><span class="sxs-lookup"><span data-stu-id="20f40-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="20f40-114">Развертывание куба получает сведения от пользователя, на которых архив качества взаимодействия расположен, развертывает куб и выполняет настройку регулярные задания агента SQL Server, который будет обновлять куб с заданной периодичностью.</span><span class="sxs-lookup"><span data-stu-id="20f40-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="20f40-115">Установка портала создает базы данных репозитория, в которой хранятся сопоставления пользователей CQD для каждого пользователя отчеты и запросы.</span><span class="sxs-lookup"><span data-stu-id="20f40-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="20f40-116">Затем оно выполняет настройку веб-приложения IIS, который является панели мониторинга, где пользователи могли просматривать предварительно определенный набор отчетов, а также настраивать и создавать собственные запросы для визуализации данных из куба.</span><span class="sxs-lookup"><span data-stu-id="20f40-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="20f40-117">Установка портала создает два дополнительных веб-приложения, которые предоставляет API-интерфейсы для пользователей для программного доступа к хранилище и куб.</span><span class="sxs-lookup"><span data-stu-id="20f40-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="20f40-118">(Эти интерфейсы API используются во внутреннем панели мониторинга, а также.)</span><span class="sxs-lookup"><span data-stu-id="20f40-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="20f40-119">**Этап**</span><span class="sxs-lookup"><span data-stu-id="20f40-119">**Phase**</span></span>|<span data-ttu-id="20f40-120">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="20f40-120">**Steps**</span></span>|<span data-ttu-id="20f40-121">**Членство в ролях и группе**</span><span class="sxs-lookup"><span data-stu-id="20f40-121">**Roles and group membership**</span></span>|<span data-ttu-id="20f40-122">**Документация**</span><span class="sxs-lookup"><span data-stu-id="20f40-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="20f40-123">Установка необходимого оборудования и программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="20f40-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="20f40-124">Принятие решения по конфигурации CQD и выберите команду SQL Server, из которого требуется выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="20f40-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="20f40-125">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="20f40-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="20f40-126">«Предварительно требования к установке» в разделе документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20f40-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="20f40-127">Установка CQD.</span><span class="sxs-lookup"><span data-stu-id="20f40-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="20f40-128">Запустите MSI-файла после его развертывания.</span><span class="sxs-lookup"><span data-stu-id="20f40-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="20f40-129">Для выполнения программы установки, Установка учетной записи пользователя домена, который является членом группы локальных администраторов и иметь доступ на чтение к базе данных показатели качества взаимодействия на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="20f40-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="20f40-130">Разделы «Учетные записи и шаги развертывания» в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20f40-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="20f40-131">Предоставление доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="20f40-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="20f40-132">Для управления авторизации пользователя на портале, рекомендуется использовать авторизации URL-адрес, который был введен в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="20f40-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="20f40-133">Для получения дополнительных сведений см [Общее представление о IIS 7.0 URL-адрес](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="20f40-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="20f40-134">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="20f40-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="20f40-135">Управление доступом пользователей для раздела портала в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20f40-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="20f40-136">Необязательно: Предоставить сведения о сопоставлении подсети.</span><span class="sxs-lookup"><span data-stu-id="20f40-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="20f40-137">Заполните сети и сопоставление построения таблиц в базе данных архива качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="20f40-138">Учетная запись с доступ на запись к базе данных архива качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="20f40-139">«Предоставление сведений о подсети» в разделе документации для пользователя.</span><span class="sxs-lookup"><span data-stu-id="20f40-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="20f40-140">Развертывание панели мониторинга качества звонков включает в себя настройку инфраструктуры и установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="20f40-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="20f40-141">В следующей процедуре показано процесса.</span><span class="sxs-lookup"><span data-stu-id="20f40-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="20f40-142">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="20f40-142">Deployment Steps</span></span>

1. <span data-ttu-id="20f40-143">Скопируйте CallQualityDashboard.msi на компьютере, где должна быть установлена компонент базы данных архива CQD (это компьютера, на котором установлен сервер SQL).</span><span class="sxs-lookup"><span data-stu-id="20f40-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="20f40-144">Выполнение MSI-файла (Windows выводит запрос на запуск с правами администратора, делать это).</span><span class="sxs-lookup"><span data-stu-id="20f40-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="20f40-145">Примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="20f40-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="20f40-146">Выберите папку назначения, где будет находиться файлов, связанных компонентов панели мониторинга качества звонков или примите расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="20f40-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="20f40-147">Выберите все компоненты.</span><span class="sxs-lookup"><span data-stu-id="20f40-147">Select all features.</span></span>
    
6. <span data-ttu-id="20f40-148">На странице конфигурации качества взаимодействия архива введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="20f40-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="20f40-149">**Показатели качества взаимодействия SQL Server:** Имя экземпляра SQL Server, для которой находится база данных показатели качества взаимодействия (это будет источник данных).</span><span class="sxs-lookup"><span data-stu-id="20f40-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="20f40-150">**Архива QoE имя сервера SQL:** Это поле только для чтения, фиксированной полное доменное имя на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20f40-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="20f40-151">Архив DB может устанавливаться только на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20f40-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="20f40-152">**Архива QoE экземпляр SQL Server:** Локальный имя экземпляра SQL Server для которой должен быть создан база данных архива.</span><span class="sxs-lookup"><span data-stu-id="20f40-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="20f40-153">Чтобы использовать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="20f40-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="20f40-154">Чтобы использовать именованный экземпляр SQL Server, укажите имя экземпляра (например имя после "\").</span><span class="sxs-lookup"><span data-stu-id="20f40-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="20f40-155">**Качества взаимодействия архивной базы данных:** По умолчанию включен режим «Создать базу данных».</span><span class="sxs-lookup"><span data-stu-id="20f40-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="20f40-156">Так как база данных архива обновления не поддерживается, единственный случай, в котором можно использовать параметр «Использовать существующую базу данных» — Если существующая база данных архива имеет той же схеме, построения, чтобы установить.</span><span class="sxs-lookup"><span data-stu-id="20f40-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="20f40-157">**Базы данных каталог файлов:** Путь, где должны размещаться файлы базы данных (MDF и LDF) для базы данных архива.</span><span class="sxs-lookup"><span data-stu-id="20f40-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="20f40-158">Это должен быть на диск (HDD2 в Рекомендуемая конфигурация оборудования) отдельно от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="20f40-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="20f40-159">Обратите внимание, что с момента фиксированные имена файлов в установку во избежание любой вероятность конфликта рекомендуется использовать пустой каталог с файлами, не.</span><span class="sxs-lookup"><span data-stu-id="20f40-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="20f40-160">**Использовать несколько разделов:** По умолчанию задано значение «Несколько раздел», который требуется выпуск Business Intelligence или Enterprise edition SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20f40-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="20f40-161">Для Standard edition выберите параметр «Один раздел».</span><span class="sxs-lookup"><span data-stu-id="20f40-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="20f40-162">Обратите внимание, что если используется один раздел изменится производительность обработки куба.</span><span class="sxs-lookup"><span data-stu-id="20f40-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="20f40-163">Выбор варианта использования нескольких секций нельзя изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="20f40-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="20f40-164">Измените его куба, функция должна быть первой удален и затем переустановить с помощью команды «Изменить» в панели управления.</span><span class="sxs-lookup"><span data-stu-id="20f40-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="20f40-165">**Partition каталог файлов:** Путь, где должны размещаться разделы для качества взаимодействия архивной базы данных.</span><span class="sxs-lookup"><span data-stu-id="20f40-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="20f40-166">Это должен быть на диск (HDD3 в Рекомендуемая конфигурация оборудования) отдельно от диска операционной системы и диск файлы журнала базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="20f40-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="20f40-167">Обратите внимание, что с момента фиксированные имена файлов в установку во избежание любой вероятность конфликта рекомендуется использовать пустой каталог с файлами, не.</span><span class="sxs-lookup"><span data-stu-id="20f40-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="20f40-168">**Пользователя задания агента SQL — имя пользователя &amp; пароль:** Имя учетной записи службы домена и пароль (маской), который будет использоваться для запуска «Данных о качестве взаимодействия архива» шаг задания агента SQL Server (который будет работать хранимую процедуру для получения данных из DB показатели качества взаимодействия в архив базы данных, поэтому учетная запись должна иметь доступ на чтение к DB показатели качества взаимодействия,  как указано в разделе учетные записи.</span><span class="sxs-lookup"><span data-stu-id="20f40-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="20f40-169">Эта учетная запись также должен иметь имя входа в экземпляр SQL Server QoE архива).</span><span class="sxs-lookup"><span data-stu-id="20f40-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="20f40-170">Учетная запись, которой работает экземпляр SQL Server, такие как NT SERVICE\MSSQLSERVER должна иметь доступ к папкам, приведенном выше, для успешной установки.</span><span class="sxs-lookup"><span data-stu-id="20f40-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="20f40-171">Дополнительные сведения см [Настроить разрешения файловой системы для доступа к базе данных модуля](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="20f40-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="20f40-172">После нажатия кнопки Далее, программа установки выполнит необходимые предварительные проверки и отчет о найденные проблемы, возникающие.</span><span class="sxs-lookup"><span data-stu-id="20f40-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="20f40-173">Когда все необходимые предварительные проверки прохода, установщик будут поступать на странице "Конфигурация куба".</span><span class="sxs-lookup"><span data-stu-id="20f40-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="20f40-174">Если программа установки отображает предупреждение, которое не в настоящее время работает служба агента SQL Server для экземпляра SQL Server архив качества взаимодействия, можно продолжить установку, но post установки убедитесь в том, что служба агента SQL работает и значение тип запуска Автоматическое, чтобы запускает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="20f40-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="20f40-175">На странице Конфигурация куба введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="20f40-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="20f40-176">**Архива QoE имя сервера SQL:** Это поле только для чтения, фиксированной полное доменное имя на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20f40-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="20f40-177">Куб может устанавливаться только с компьютера, на котором имеется база данных архива качества взаимодействия (Примечание.</span><span class="sxs-lookup"><span data-stu-id="20f40-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="20f40-178">Сам куб может устанавливаться на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20f40-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="20f40-179">Ниже приведены)</span><span class="sxs-lookup"><span data-stu-id="20f40-179">See below)</span></span>
    
   - <span data-ttu-id="20f40-180">**Архива QoE экземпляр SQL Server:** Имя экземпляра SQL Server для где расположена база данных архива качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="20f40-181">Чтобы указать экземпляр SQL Server по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="20f40-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="20f40-182">Чтобы указать именованный экземпляр SQL Server, введите имя экземпляра (например имя после "\").</span><span class="sxs-lookup"><span data-stu-id="20f40-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="20f40-183">Если компонент качества взаимодействия архив был выбран для установки, это поле будет предварительно заполненный с значение, заданное на странице Конфигурация архив качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="20f40-184">**Куба сервера анализа:** Имя экземпляра службы аналитики SQL Server для которой должен быть создан куб.</span><span class="sxs-lookup"><span data-stu-id="20f40-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="20f40-185">Это может быть другой компьютер, но установка, пользователь должен быть членом группы администраторов сервера нужного экземпляра службы аналитики SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20f40-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="20f40-186">Дополнительные сведения о настройке разрешений администратора сервера служб Analysis можно [Предоставить разрешения администратора сервера (службы Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="20f40-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="20f40-187">**Использовать несколько разделов:** По умолчанию задано значение «Несколько раздел», который требуется выпуск Business Intelligence или Enterprise edition SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20f40-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="20f40-188">Для Standard edition выберите параметр «Один раздел».</span><span class="sxs-lookup"><span data-stu-id="20f40-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="20f40-189">Обратите внимание, что если используется один раздел изменится производительность обработки куба.</span><span class="sxs-lookup"><span data-stu-id="20f40-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="20f40-190">Выбор варианта использования нескольких секций нельзя изменить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="20f40-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="20f40-191">Измените его куба, функция должна быть первой удален и затем переустановить с помощью команды «Изменить» в панели управления.</span><span class="sxs-lookup"><span data-stu-id="20f40-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="20f40-192">**Куба пользователя — имя пользователя &amp; пароль:** Имя учетной записи службы домена и пароль (маской), который будет запускать обработки куба.</span><span class="sxs-lookup"><span data-stu-id="20f40-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="20f40-193">Если компонент качества взаимодействия архив был выбран для установки, это поле будет предварительно заполненный с значение, заданное на странице Конфигурация архива для пользователя задания агента SQL, но рекомендуется указать учетную запись службы другом домене, чтобы программа установки может предоставить Обязательный прав на него.</span><span class="sxs-lookup"><span data-stu-id="20f40-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="20f40-194">После нажатия кнопки Далее, будет выполнена другой round проверки и сообщает проблемы.</span><span class="sxs-lookup"><span data-stu-id="20f40-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="20f40-195">После успешного завершения проверки установщик перейдите на страницу настройки портала.</span><span class="sxs-lookup"><span data-stu-id="20f40-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="20f40-196">На странице настройки портала введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="20f40-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="20f40-197">**Архива QoE SQL Server:** Имя экземпляра SQL Server для котором расположена база данных архива качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="20f40-198">Обратите внимание, что в отличие от страницы конфигурации качества взаимодействия архива и на странице Конфигурация куба, имя компьютера, имя не устранена и должен быть указан.</span><span class="sxs-lookup"><span data-stu-id="20f40-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="20f40-199">Если компонент качества взаимодействия архив был выбран для установки, это поле будет предварительно заполненный с значение, заданное на странице Конфигурация архив качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20f40-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="20f40-200">**Куба сервера анализа:** Имя экземпляра службы аналитики SQL Server для где расположена куба.</span><span class="sxs-lookup"><span data-stu-id="20f40-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="20f40-201">Если компонент куб был выбран для установки, это поле будет предварительно заполненный со значением, содержащимся на странице "Конфигурация куба".</span><span class="sxs-lookup"><span data-stu-id="20f40-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="20f40-202">**Репозитория SQL Server:** Имя экземпляра SQL Server, где должен быть создан базы данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="20f40-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="20f40-203">Если этот параметр указан имя экземпляра SQL Server, для которой расположена база данных архива качества взаимодействия ранее в программе установки (в других компонентов) в этом поле будет предварительно заполнен QoE архива базы данных имя экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20f40-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="20f40-204">Это может быть любой экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20f40-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="20f40-205">**Базы данных репозитория:** По умолчанию параметр имеет значение «Создать базу данных».</span><span class="sxs-lookup"><span data-stu-id="20f40-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="20f40-206">Так как база данных репозитория обновления не поддерживается, единственный случай, в котором можно использовать параметр «Использовать существующую базу данных» — Если существующая база данных репозитория есть той же схеме, построения, чтобы установить.</span><span class="sxs-lookup"><span data-stu-id="20f40-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="20f40-207">**Пользователь пула приложений IIS - имя пользователя &amp; пароль:** Учетная запись, который должен выполняться пул приложений IIS, в группе.</span><span class="sxs-lookup"><span data-stu-id="20f40-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="20f40-208">Поля имя пользователя и пароль становится недоступной, если выбрана встроенная системных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="20f40-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="20f40-209">Эти поля будет доступен только в том случае, если выбран «Прочие» из раскрывающегося списка, пользователь может ввести данные учетной записи службы домена.</span><span class="sxs-lookup"><span data-stu-id="20f40-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="20f40-210">После нажатия кнопки Далее, окончательный round проверки будет выполнено, чтобы убедиться, что экземпляры SQL Server, доступны, используя учетные данные и доступны на компьютере, что службы IIS.</span><span class="sxs-lookup"><span data-stu-id="20f40-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="20f40-211">После успешного завершения проверки установщик будет продолжить установку.</span><span class="sxs-lookup"><span data-stu-id="20f40-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="20f40-212">После завершения установки, вероятнее всего хода выполнения, выполнив начальной загрузки данных о качестве взаимодействия и обработки куба будет задания агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20f40-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="20f40-213">В зависимости от объема данных в качества взаимодействия портала не будут иметь данных, которые доступны для просмотра еще.</span><span class="sxs-lookup"><span data-stu-id="20f40-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="20f40-214">Чтобы проверить состояние загрузки данных и обработки куба, перейдите к `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="20f40-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="20f40-215">Обратите внимание, что URL-адрес для проверки состояния обработки куба файл для загрузки с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="20f40-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="20f40-216">Если ввести работоспособности URL-адреса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="20f40-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="20f40-217">Необходимо ввести «Работоспособности» в конце URL-адрес с заглавной буквы з.</span><span class="sxs-lookup"><span data-stu-id="20f40-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="20f40-218">Подробный журнал сообщения будут отображаться при включенном режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="20f40-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="20f40-219">Чтобы включить режим отладки, перейдите к **%SYSTEMDRIVE%\Program Files\Skype для бизнеса 2015 CQD\QoEDataService\web.config**и обновить следующую строку, поэтому значение присвоено **значение True**:</span><span class="sxs-lookup"><span data-stu-id="20f40-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="20f40-220">Главной страницы портала доступную через `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="20f40-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="20f40-221">Управление доступом пользователей портала</span><span class="sxs-lookup"><span data-stu-id="20f40-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="20f40-222">Для управления авторизации пользователя на портале, рекомендуется использовать авторизации URL-адрес, который был введен в IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="20f40-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="20f40-223">Дополнительные сведения о безопасности служб IIS [Общие сведения о IIS 7.0 URL-адрес авторизации ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)см.</span><span class="sxs-lookup"><span data-stu-id="20f40-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="20f40-224">Любой веб-сайта или веб-приложения наследуют по умолчанию авторизации URL-адреса, настроенные для всей службы IIS, которая обычно является «Разрешить все пользователи».</span><span class="sxs-lookup"><span data-stu-id="20f40-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="20f40-225">Если доступ к порталу должен быть более жесткие, затем администраторов можно предоставить доступ только определенные группы пользователей путем редактирования «Правил авторизации».</span><span class="sxs-lookup"><span data-stu-id="20f40-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Развертывание мониторинга качества вызовов - Правила авторизации в IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="20f40-227">Значок правил авторизации, не следует путать с «Authorization .NET» в разделе раздела ASP.NET, который представляет собой механизм различных авторизации.</span><span class="sxs-lookup"><span data-stu-id="20f40-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="20f40-228">Администраторам необходимо удалить правило наследуемые «разрешить все пользователи».</span><span class="sxs-lookup"><span data-stu-id="20f40-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="20f40-229">Это любой неавторизованный пользователям запрещается доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="20f40-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Развертывание CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="20f40-231">Затем администраторы должны добавить новые правила разрешить и предоставление определенным пользователям разрешения на доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="20f40-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="20f40-232">Рекомендуется создать в локальную группу с именем «CQDPortalUsers» Управление пользователями.</span><span class="sxs-lookup"><span data-stu-id="20f40-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Развертывание панели мониторинга качества вызовов](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="20f40-234">Сведения о конфигурации хранятся в файле web.config, расположенном по физический каталог портала.</span><span class="sxs-lookup"><span data-stu-id="20f40-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="20f40-235">Следующим шагом является Настройка панели мониторинга CQD.</span><span class="sxs-lookup"><span data-stu-id="20f40-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="20f40-236">После проверки подлинности пользователей службами IIS, у них для получения прав файл в каталоге CQD, чтобы получить доступ к веб-портала содержимого.</span><span class="sxs-lookup"><span data-stu-id="20f40-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="20f40-237">Можно изменить списки управления доступом на вкладке Безопасность свойств каталога CQD Добавление отдельных пользователей и групп; Тем не менее рекомендуется оставить разрешения файла без изменений.</span><span class="sxs-lookup"><span data-stu-id="20f40-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="20f40-238">Вместо этого измените параметр служб IIS, чтобы использовать рабочий процесс IIS для доступа к каталогу CQD, независимо от того, что проверка подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="20f40-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="20f40-239">Важно только изменить этот параметр для приложения CQD, а не для двух приложений API: QoEDataService и QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="20f40-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="20f40-240">Настройка доступа к файлам для CQD (панель мониторинга)</span><span class="sxs-lookup"><span data-stu-id="20f40-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="20f40-241">Откройте редактор конфигурации для CQD.</span><span class="sxs-lookup"><span data-stu-id="20f40-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="20f40-243">В разделе Выбор **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="20f40-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="20f40-245">Измените authenticatedUserOverride на **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="20f40-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов - Редактор конфигурации](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="20f40-247">Нажмите кнопку **Применить** в правой части страницы.</span><span class="sxs-lookup"><span data-stu-id="20f40-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="20f40-248">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="20f40-248">Known Issues</span></span>

<span data-ttu-id="20f40-249">В редких случаях установщик не удается создать правильные параметры в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="20f40-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="20f40-250">Чтобы разрешить пользователям войдите в CQD требуется заданное вручную изменение.</span><span class="sxs-lookup"><span data-stu-id="20f40-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="20f40-251">Если пользователи удается войти в систему, выполните следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="20f40-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="20f40-252">Откройте настройки диспетчера служб IIS и перейдите по умолчанию веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="20f40-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="20f40-254">Щелкните «Проверка подлинности».</span><span class="sxs-lookup"><span data-stu-id="20f40-254">Click on "Authentication".</span></span> <span data-ttu-id="20f40-255">Если «Анонимный доступ», «ASP.NET олицетворения», «Проверка подлинности форм» и «Проверка подлинности Windows» не соответствуют параметрам, показанного ниже, вручную измените их в соответствии с настройкой.</span><span class="sxs-lookup"><span data-stu-id="20f40-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="20f40-256">Все другие способы проверки подлинности должны быть отключены.</span><span class="sxs-lookup"><span data-stu-id="20f40-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="20f40-258">«Проверка подлинности Windows» нажмите кнопку Дополнительные параметры в правой части.</span><span class="sxs-lookup"><span data-stu-id="20f40-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="20f40-260">Значение «Расширенной защиты» принять и установите флажок «Включить в режиме ядра проверка подлинности».</span><span class="sxs-lookup"><span data-stu-id="20f40-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Развертывание панели мониторинга качества вызовов](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="20f40-262">Повторите описанные действия для каждой записи «CQD», «QoEDataService» и «QoERepositoryService» ниже «по умолчанию веб-сайта».</span><span class="sxs-lookup"><span data-stu-id="20f40-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="20f40-263">Для привязки портов HTTP и HTTPS установщик создаст привязки портов на номера портов по умолчанию (порт 80 для HTTP) и порт 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="20f40-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="20f40-264">Если на компьютере, который использует эти привязки другого веб-сайта, будет конфликта и многократном поведение служб IIS.</span><span class="sxs-lookup"><span data-stu-id="20f40-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="20f40-265">Чтобы избежать этой проблемы рекомендуется убедитесь в том, что нет других веб-сайтах, сопоставляются с порта 80 и 443 перед установкой CQD.</span><span class="sxs-lookup"><span data-stu-id="20f40-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="20f40-266">Чтобы включить протокол SSL/TLS в службах IIS и принудительное подключение через безопасный протокол HTTPS вместо HTTP:</span><span class="sxs-lookup"><span data-stu-id="20f40-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="20f40-267">Настроить протокол SSL в службах IIS, см [Настройка протокол SSL в IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="20f40-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="20f40-268">После замены `http` с `https`.</span><span class="sxs-lookup"><span data-stu-id="20f40-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="20f40-269">Инструкции по включению TLS в подключения к SQL Server Узнайте, [как включить SSL-шифрования для экземпляра SQL Server с помощью консоли управления ](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="20f40-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="20f40-270">Сбой синхронизации куба</span><span class="sxs-lookup"><span data-stu-id="20f40-270">Cube Sync Fails</span></span>

<span data-ttu-id="20f40-271">QoEMetrics может содержать несколько недопустимых записей на основании часы конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="20f40-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="20f40-272">Если отклонение времени превышает 60 лет, произойдет ошибка импорта куба.</span><span class="sxs-lookup"><span data-stu-id="20f40-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="20f40-273">Установите флажок мин и Макс StartTime и EndTime с помощью Выбор ниже.</span><span class="sxs-lookup"><span data-stu-id="20f40-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="20f40-274">Поиск и удаления записей в будущем дальнем последние и очень удаленных, их можно пренебречь и будет разбить процессов синхронизации.</span><span class="sxs-lookup"><span data-stu-id="20f40-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="20f40-275">Выберите MIN(StartTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="20f40-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="20f40-276">Выберите MAX(StartTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="20f40-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="20f40-277">Выберите MIN(EndTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="20f40-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="20f40-278">Выберите MAX(EndTime) из CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="20f40-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="20f40-279">Задачи после установки</span><span class="sxs-lookup"><span data-stu-id="20f40-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="20f40-280">Импорт зданий и сетей</span><span class="sxs-lookup"><span data-stu-id="20f40-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="20f40-281">После установки CQD необходимо выполните следующие задачи по настройке:</span><span class="sxs-lookup"><span data-stu-id="20f40-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="20f40-282">Определение типов построения (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="20f40-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="20f40-283">Определение типов построения владельца (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="20f40-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="20f40-284">Определение типов сети (что рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="20f40-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="20f40-285">Импорт зданий (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="20f40-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="20f40-286">Импорт подсети (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="20f40-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="20f40-287">Определение типов построения</span><span class="sxs-lookup"><span data-stu-id="20f40-287">Define Building Types</span></span>

<span data-ttu-id="20f40-288">Типы построения используются для описания определений разные зданий или типов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="20f40-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="20f40-289">Этот шаг является обязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="20f40-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="20f40-290">Примеры</span><span class="sxs-lookup"><span data-stu-id="20f40-290">Examples</span></span>
  
- <span data-ttu-id="20f40-291">Головной офис</span><span class="sxs-lookup"><span data-stu-id="20f40-291">Headquarters</span></span>
    
- <span data-ttu-id="20f40-292">Удаленного офиса</span><span class="sxs-lookup"><span data-stu-id="20f40-292">Remote Office</span></span>
    
- <span data-ttu-id="20f40-293">Расположение совместном предприятии</span><span class="sxs-lookup"><span data-stu-id="20f40-293">Joint-venture location</span></span>
    
 <span data-ttu-id="20f40-294">**Примеры синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="20f40-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="20f40-295">Параметры BuildingTypeId и BuildingTypeDesc являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="20f40-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="20f40-296">Определение типов владельца построения</span><span class="sxs-lookup"><span data-stu-id="20f40-296">Define Building Ownership Types</span></span>

<span data-ttu-id="20f40-297">Типы прав владельца используются для различения собственные vs аренду активов.</span><span class="sxs-lookup"><span data-stu-id="20f40-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20f40-298">Этот шаг является обязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="20f40-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="20f40-299">Примеры</span><span class="sxs-lookup"><span data-stu-id="20f40-299">Examples</span></span>
  
- <span data-ttu-id="20f40-300">Contoso аренду не RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="20f40-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="20f40-301">Contoso аренду RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="20f40-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="20f40-302">Владельцем Contoso</span><span class="sxs-lookup"><span data-stu-id="20f40-302">Contoso Owned</span></span>
    
- <span data-ttu-id="20f40-303">Дочерним подразделением аренду</span><span class="sxs-lookup"><span data-stu-id="20f40-303">Subsidiary Leased</span></span>
    
 <span data-ttu-id="20f40-304">**Примеры синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="20f40-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="20f40-305">Параметры OwnershipTypeId и OwnershipTypeDesc являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="20f40-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="20f40-306">Определение сетевых имен</span><span class="sxs-lookup"><span data-stu-id="20f40-306">Define Network Names</span></span>

<span data-ttu-id="20f40-307">Типы сети используются для описания различных типов сетей в рамках организации.</span><span class="sxs-lookup"><span data-stu-id="20f40-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="20f40-308">Это дает возможность фильтрации (или отфильтровать) определенного типа сети.</span><span class="sxs-lookup"><span data-stu-id="20f40-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20f40-309">Настоятельно рекомендуется для определения имен сети, но он не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="20f40-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="20f40-310">Если вы решили не определили имена сети, убедитесь, что для каждой записи CqdNetwork равно BuildingId 0.</span><span class="sxs-lookup"><span data-stu-id="20f40-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="20f40-311">Примеры</span><span class="sxs-lookup"><span data-stu-id="20f40-311">Examples</span></span>
  
- <span data-ttu-id="20f40-312">VPN</span><span class="sxs-lookup"><span data-stu-id="20f40-312">VPN</span></span>
    
- <span data-ttu-id="20f40-313">ЛАБОРАТОРИИ</span><span class="sxs-lookup"><span data-stu-id="20f40-313">LAB</span></span>
    
 <span data-ttu-id="20f40-314">**Примеры синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="20f40-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="20f40-315">Параметры NetworkNameID и NetworkName являются обязательными, параметр NetworkType, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="20f40-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="20f40-316">Импорт зданий</span><span class="sxs-lookup"><span data-stu-id="20f40-316">Import Buildings</span></span>

<span data-ttu-id="20f40-317">Импорт зданий предоставляет возможность получения построение полезные сведения о конкретных (низкого уровня звонков в построение на WiFi/проводной сети, и т.д.).</span><span class="sxs-lookup"><span data-stu-id="20f40-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="20f40-318">Этот шаг является обязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="20f40-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="20f40-319">Перед импортом новое построение вам необходимо иметь предварительно заданных BuildingKey определяемую.</span><span class="sxs-lookup"><span data-stu-id="20f40-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="20f40-320">Для этого используйте команду SQL «ВЫБЕРИТЕ MAX(BuildingKey) из CqdBuilding» определение текущее значение и добавление 1 результат.</span><span class="sxs-lookup"><span data-stu-id="20f40-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="20f40-321">**Примеры синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="20f40-321">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="20f40-322">BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId параметры являются обязательными, другие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="20f40-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="20f40-323">Импорт подсетей</span><span class="sxs-lookup"><span data-stu-id="20f40-323">Import Subnets</span></span>

<span data-ttu-id="20f40-324">Импорт зданий предоставляет возможность получения построение полезные сведения о конкретных (низкого уровня звонков в построение на WiFi/проводной сети, и т.д.).</span><span class="sxs-lookup"><span data-stu-id="20f40-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="20f40-325">Этот шаг является обязательным, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="20f40-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="20f40-326">Импорт подсети и сопоставить их зданий, импортирован на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="20f40-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="20f40-327">Если не следует заполнить NetworkName, убедитесь, что каждой записи в этой таблице использует NetworkNameID 0.</span><span class="sxs-lookup"><span data-stu-id="20f40-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="20f40-328">**Примеры синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="20f40-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="20f40-329">Сети и UpdatedDate параметры являются обязательными, другие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="20f40-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="20f40-330">Необязательно: BSSID</span><span class="sxs-lookup"><span data-stu-id="20f40-330">Optional: BSSID</span></span>

<span data-ttu-id="20f40-331">Заполнение сведения BSSID предоставляет дополнительные корреляции потока WiFi контроллером или радио.</span><span class="sxs-lookup"><span data-stu-id="20f40-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="20f40-332">Это в дополнение к фильтрация по построению или подсети.</span><span class="sxs-lookup"><span data-stu-id="20f40-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="20f40-333">**Примеры синтаксиса SQL**</span><span class="sxs-lookup"><span data-stu-id="20f40-333">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="20f40-334">**Сведения о CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="20f40-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="20f40-335">**Как показано на CQD**</span><span class="sxs-lookup"><span data-stu-id="20f40-335">**As shown in CQD**</span></span>|<span data-ttu-id="20f40-336">**В таблице CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="20f40-336">**CQDBssid Table**</span></span>|<span data-ttu-id="20f40-337">**Пример исходные данные**</span><span class="sxs-lookup"><span data-stu-id="20f40-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20f40-338">AP NName</span><span class="sxs-lookup"><span data-stu-id="20f40-338">Ap NName</span></span>  <br/> |<span data-ttu-id="20f40-339">AP</span><span class="sxs-lookup"><span data-stu-id="20f40-339">AP</span></span>  <br/> |<span data-ttu-id="20f40-340">AP1</span><span class="sxs-lookup"><span data-stu-id="20f40-340">AP1</span></span>  <br/> |
|<span data-ttu-id="20f40-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="20f40-341">BBssid</span></span>  <br/> |<span data-ttu-id="20f40-342">BSS</span><span class="sxs-lookup"><span data-stu-id="20f40-342">BSS</span></span>  <br/> |<span data-ttu-id="20f40-343">00-00-00-00-00-00 (необходимо использовать с разделителями fformat)</span><span class="sxs-lookup"><span data-stu-id="20f40-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="20f40-344">Контроллер</span><span class="sxs-lookup"><span data-stu-id="20f40-344">Controller</span></span>  <br/> |<span data-ttu-id="20f40-345">Building</span><span class="sxs-lookup"><span data-stu-id="20f40-345">Building</span></span>  <br/> |<span data-ttu-id="20f40-346">Аруба AP 7</span><span class="sxs-lookup"><span data-stu-id="20f40-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="20f40-347">Устройства</span><span class="sxs-lookup"><span data-stu-id="20f40-347">Device</span></span>  <br/> |<span data-ttu-id="20f40-348">ess</span><span class="sxs-lookup"><span data-stu-id="20f40-348">ess</span></span>  <br/> |<span data-ttu-id="20f40-349">Контроллер1</span><span class="sxs-lookup"><span data-stu-id="20f40-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="20f40-350">Радио</span><span class="sxs-lookup"><span data-stu-id="20f40-350">Radio</span></span>  <br/> |<span data-ttu-id="20f40-351">phy</span><span class="sxs-lookup"><span data-stu-id="20f40-351">phy</span></span>  <br/> |<span data-ttu-id="20f40-352">bgn</span><span class="sxs-lookup"><span data-stu-id="20f40-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="20f40-353">Обработка импортированных данных</span><span class="sxs-lookup"><span data-stu-id="20f40-353">Processing the imported data</span></span>

<span data-ttu-id="20f40-354">По умолчанию после импорта данных построения/сети он применяется только к записей, созданных после этого времени.</span><span class="sxs-lookup"><span data-stu-id="20f40-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="20f40-355">Чтобы отметить все предыдущие записи с помощью новых данных, необходимо выполнить процедуру, хранимых CqdUpdateBuilding, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="20f40-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="20f40-356">Задайте для него Дата первой записи (определение, с помощью команды выберите MIN(StartTime) из CqdPartitionedStreamView SQL), EndDate завтрашнему дню, тогда значение NULL для последние два значения.</span><span class="sxs-lookup"><span data-stu-id="20f40-356">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="20f40-357">После данных связан с поток данных, SSIS куба необходимо повторно обработать все записи.</span><span class="sxs-lookup"><span data-stu-id="20f40-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="20f40-358">Это также относится когда Массовое добавление данных BSSID/поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="20f40-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="20f40-359">Убедитесь, что выбран «Процесс Full».</span><span class="sxs-lookup"><span data-stu-id="20f40-359">Ensure that "Process Full" is selected.</span></span>
  

