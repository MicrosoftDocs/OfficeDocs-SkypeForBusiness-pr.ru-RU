---
title: Развертывание группы доступности Always On на тыловом сервере в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Развертывание (установка) группы доступности Always On в развертывании Skype для бизнеса Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830659"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="2cf38-103">Развертывание группы доступности Always On на тыловом сервере в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2cf38-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="2cf38-104">Развертывание (установка) группы доступности Always On (AG) в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="2cf38-105">Развертывание ag зависит от того, развертывается ли она в новом пуле, в существующем пуле, использующем зеркальное отражение, или в существующем пуле, который в настоящее время не имеет высокой доступности для базы данных тыловой части.</span><span class="sxs-lookup"><span data-stu-id="2cf38-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2cf38-106">Использование AG с ролью сервера сохраняемой беседы не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2cf38-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="2cf38-107">Развертывание группы доступности Always On в новом пуле переднего доступа</span><span class="sxs-lookup"><span data-stu-id="2cf38-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="2cf38-108">Развертывание группы доступности Always On в существующем пуле, использующем зеркальное отражение базы данных</span><span class="sxs-lookup"><span data-stu-id="2cf38-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="2cf38-109">Развертывание группы доступности Always On в существующем пуле, который не использует зеркальное отражение базы данных</span><span class="sxs-lookup"><span data-stu-id="2cf38-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="2cf38-110">Развертывание группы доступности Always On в новом пуле переднего доступа</span><span class="sxs-lookup"><span data-stu-id="2cf38-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="2cf38-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="2cf38-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="2cf38-112">Включить функцию failover Clustering на всех серверах баз данных, которые будут в составе ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="2cf38-113">На каждом сервере сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2cf38-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="2cf38-114">Откройте диспетчер серверов и **нажмите кнопку "Добавить роли и функции".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="2cf38-115">**Нажимайте кнопку** "Далее", пока не дойдете до **окна "Выбор компонентов".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="2cf38-116">В этом поле выберите **"Отбойная кластеризация".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="2cf38-117">В **окне "Добавление компонентов, необходимых для кластерной** отбойной работы", нажмите кнопку **"Добавить функции".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="2cf38-118">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="2cf38-119">Проверьте конфигурацию кластера.</span><span class="sxs-lookup"><span data-stu-id="2cf38-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="2cf38-120">В диспетчере серверов выберите меню **"Инструменты",** а затем пункт **"Диспетчер отбойных кластеров".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="2cf38-121">В **области "Действия"** в правой части экрана щелкните **"Проверить конфигурацию".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="2cf38-122">На странице **Перед началом работы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-123">Выберите серверы для добавления в кластер и нажмите кнопку **"Выполнить все тесты".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="2cf38-124">В поле **сводки** проверьте все ошибки, которые сообщает мастер.</span><span class="sxs-lookup"><span data-stu-id="2cf38-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="2cf38-125">Затем нажмите **кнопку "Готово",** чтобы завершить проверку.</span><span class="sxs-lookup"><span data-stu-id="2cf38-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="2cf38-126">Возможно, мастер вывести несколько предупреждений, особенно если вы не используете общее хранилище.</span><span class="sxs-lookup"><span data-stu-id="2cf38-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="2cf38-127">Использование общего хранилища не требуется.</span><span class="sxs-lookup"><span data-stu-id="2cf38-127">You are not required to use shared storage.</span></span> <span data-ttu-id="2cf38-128">Тем не менее,  если вы видите какие-либо сообщения об ошибках, необходимо устранить эти проблемы, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="2cf38-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="2cf38-129">Создание кластера windows Server Failover Cluster (WSFC).</span><span class="sxs-lookup"><span data-stu-id="2cf38-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="2cf38-130">В **мастере управления кластером** для отбойной передачи щелкните правой кнопкой мыши "Управление отбойным кластером" и выберите **"Создать кластер".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="2cf38-131">На странице **Перед началом работы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-132">Добавьте имя кластера и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="2cf38-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="2cf38-133">После проверки параметров нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-134">На странице Подтверждение нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-135">После создания кластера нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="2cf38-136">Рекомендуется настроить параметры кворума кластера для использования файловой папки-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="2cf38-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="2cf38-137">Для этого сделайте вот что:</span><span class="sxs-lookup"><span data-stu-id="2cf38-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="2cf38-138">Щелкните правой кнопкой мыши имя кластера, выберите "Дополнительные действия" и выберите "Настройка параметров **кворума кластера".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="2cf38-139">На странице **"Выбор параметра конфигурации кворума"** щелкните **"Выберите свидетель кворума".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="2cf38-140">На странице **"Выбор свидетеля кворума"** щелкните **"Настройка файловой папки-свидетеля".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="2cf38-141">На странице **"Настройка файлового свидетеля"** введите путь к нужному файловому файлу и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-142">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="2cf38-143">На каждом сервере в кластере в SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2cf38-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="2cf38-144">Откройте диспетчер конфигураций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="2cf38-145">В дереве в левой части экрана щелкните SQL Server **services,** а затем дважды щелкните SQL Server службу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="2cf38-146">В поле **"Свойства"** выберите вкладку **"Высокий уровень доступности AlwaysOn".** Выберите **"Включить группы доступности AlwaysOn".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="2cf38-147">Перезапустите SQL Server по запросу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="2cf38-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="2cf38-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="2cf38-149">В этом случае укажите AG в качестве SQL для пула.</span><span class="sxs-lookup"><span data-stu-id="2cf38-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="2cf38-150">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="2cf38-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="2cf38-151">Откройте SQL Server Management Studio и подключите его к SQL Server экземпляру.</span><span class="sxs-lookup"><span data-stu-id="2cf38-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="2cf38-152">В обозревателе объектов разоберете папку **"Высокий уровень доступности Always On".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="2cf38-153">Щелкните правой кнопкой мыши папку **"Группы** доступности" и выберите "Мастер новой **группы доступности".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="2cf38-154">Если **появится страница** "Введение", нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-155">На странице **"Указание имени группы** доступности" введите имя группы доступности и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-156">На странице "Выбор баз данных" выберите базы данных, которые необходимо включить в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2cf38-157">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="2cf38-158">Не включайте базы данных **ReportServer,** **ReportServerTempDB** или Persistent Chat в группу доступности AlwaysOn, так как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2cf38-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="2cf38-159">Вы можете включить все остальные базы данных Skype для бизнеса Server в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="2cf38-160">На странице **"Указание реплик"** перейдите на вкладку **"Реплики".** Затем нажмите **кнопку "Добавить** реплики" и подключите другие экземпляры SQL, которые вы присоединили как узлы кластера для отключении Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="2cf38-161">Для каждого экземпляра выберите параметры **автоматической отключки** и **синхронной фиксации.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="2cf38-162">Не выбирайте параметр **"Читаемый дополнительный".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="2cf38-163">Перейдите **на вкладку "Конечные** точки" и убедитесь, что для номера **порта** установлено число 5022.</span><span class="sxs-lookup"><span data-stu-id="2cf38-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="2cf38-164">Перейдите **на вкладку** "Прослушиватель" и выберите параметр **"Создать прослушиватель группы доступности".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="2cf38-165">В этом параметре введите имя прослушиватель  и заведите порт 1433 (другие порты для этого параметра не поддерживаются).</span><span class="sxs-lookup"><span data-stu-id="2cf38-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="2cf38-166">Нажмите **кнопку**"Добавить", а затем в **поле IPv4-адреса** уканите предпочитаемый виртуальный IP-адрес и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="2cf38-167">На  странице "Выбор начальной синхронизации данных" выберите "Полная" и укажите папку, доступную репликам, и для учетной записи службы SQL Server, используемой обеими репликами, есть разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="2cf38-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="2cf38-168">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="2cf38-169">Эта папка будет временно использоваться при инициализации баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cf38-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="2cf38-170">При работе с большими базами данных рекомендуется вручную инициализировать их, если пропускная способность сети не может вместить размер резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cf38-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="2cf38-171">На странице проверки убедитесь, что все проверки успешно, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-172">На странице **"Сводка"** проверьте все параметры и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="2cf38-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="2cf38-173">После развертывания пула и ag выполните некоторые последние действия, чтобы убедиться, что SQL входа находятся на каждой реплике в группе доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="2cf38-174">Откройте построитель топологий, выберите **"Загрузить топологию" из** существующего развертывания и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="2cf38-175">Развяйте Skype для бизнеса Server, развяйте топологию и **SQL Server магазинах.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2cf38-176">Щелкните правой кнопкой мыши SQL новой группы доступности AlwaysOn и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="2cf38-177">В нижней части страницы в SQL Server **FQDN** измените значение на FQDN прослушиватель AG.</span><span class="sxs-lookup"><span data-stu-id="2cf38-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="2cf38-178">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2cf38-178">Publish the topology.</span></span> <span data-ttu-id="2cf38-179">В меню **действий** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2cf38-180">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="2cf38-181">Затем подождите несколько минут, пока не будет реплицироваться новая топология.</span><span class="sxs-lookup"><span data-stu-id="2cf38-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="2cf38-182">Откройте SQL Server Management Studio и перейдите к ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="2cf38-183">Перенаправь его на вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="2cf38-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="2cf38-184">Откройте skype for Business Server Management Shell и введите следующий SQL для входа в эту реплику:</span><span class="sxs-lookup"><span data-stu-id="2cf38-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="2cf38-185">Повторите два предыдущих шага (перенаправляйте группу на вторичную реплику, а затем используйте) для каждой  `Install-CsDatabase -Update` реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="2cf38-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="2cf38-186">Развертывание группы доступности Always On в существующем пуле, использующем зеркальное отражение базы данных</span><span class="sxs-lookup"><span data-stu-id="2cf38-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="2cf38-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="2cf38-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="2cf38-188">Если в пуле, обновляемом до ag, размещено центральное хранилище управления для организации, перед обновлением этого пула необходимо сначала переместить CMS в другой пул.</span><span class="sxs-lookup"><span data-stu-id="2cf38-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="2cf38-189">Используйте Move-CsManagementServer для перемещения пула.</span><span class="sxs-lookup"><span data-stu-id="2cf38-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="2cf38-190">Если в организации нет другого пула, можно временно развернуть сервер Standard Edition и переместить CMS на этот сервер перед обновлением пула до ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="2cf38-191">Отведите все данные от зеркала к основному узлу, открыв skype для бизнеса Server Management Shell и введя следующий cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cf38-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="2cf38-192">Повторите этот cmdlet для каждого типа базы данных в пуле.</span><span class="sxs-lookup"><span data-stu-id="2cf38-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="2cf38-193">Чтобы найти все типы баз данных, хранимые в этом пуле, можно использовать следующий cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cf38-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="2cf38-194">Используйте построитель топологий для удаления зеркального отражания базы данных из пула.</span><span class="sxs-lookup"><span data-stu-id="2cf38-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="2cf38-195">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2cf38-195">Open Topology Builder.</span></span> <span data-ttu-id="2cf38-196">В своей топологии разйдите в **enterprise Edition front End Pools,** щелкните правой кнопкой мыши имя пула и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="2cf38-197">Для каждого типа SQL в пуле с помощью этого SQL **зеркального** зеркального хранения.</span><span class="sxs-lookup"><span data-stu-id="2cf38-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="2cf38-198">Опубликуем измененную топологию.</span><span class="sxs-lookup"><span data-stu-id="2cf38-198">Publish the changed topology.</span></span> <span data-ttu-id="2cf38-199">В меню **действий** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2cf38-200">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="2cf38-201">Используйте SQL Server Management Studio для разрыва зеркала.</span><span class="sxs-lookup"><span data-stu-id="2cf38-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="2cf38-202">Откройте SQL Server Management Studio, перейдите к базам данных, щелкните правой кнопкой мыши **"Задачи"** и выберите **"Зеркало".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="2cf38-203">Затем нажмите **кнопку "Удалить зеркальное** отражение" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="2cf38-204">Повторите это для всех баз данных в пуле, которые будут преобразованы в ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="2cf38-205">Настройка функции failover Clustering на всех серверах баз данных, которые будут частью ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="2cf38-206">На каждом сервере сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2cf38-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="2cf38-207">Откройте диспетчер серверов и **нажмите кнопку "Добавить роли и функции".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="2cf38-208">**Нажимайте кнопку** "Далее", пока не дойдете до **окна "Выбор компонентов".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="2cf38-209">В этом поле выберите **"Отбойная кластеризация".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="2cf38-210">В **окне "Добавление компонентов, необходимых для кластерной** отбойной работы", нажмите кнопку **"Добавить функции".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="2cf38-211">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="2cf38-212">Проверьте конфигурацию кластера.</span><span class="sxs-lookup"><span data-stu-id="2cf38-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="2cf38-213">В диспетчере серверов выберите меню **"Инструменты",** а затем пункт **"Диспетчер отбойных кластеров".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="2cf38-214">В **области "Действия"** в правой части экрана щелкните **"Проверить конфигурацию".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="2cf38-215">На странице **Перед началом работы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-216">Выберите серверы для добавления в кластер и нажмите кнопку **"Выполнить все тесты".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="2cf38-217">В поле **сводки** проверьте все ошибки, которые сообщает мастер.</span><span class="sxs-lookup"><span data-stu-id="2cf38-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="2cf38-218">Затем нажмите **кнопку "Готово",** чтобы завершить проверку.</span><span class="sxs-lookup"><span data-stu-id="2cf38-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="2cf38-219">Возможно, мастер вывести несколько предупреждений, особенно если вы не используете общее хранилище.</span><span class="sxs-lookup"><span data-stu-id="2cf38-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="2cf38-220">Использование общего хранилища не требуется.</span><span class="sxs-lookup"><span data-stu-id="2cf38-220">You are not required to use shared storage.</span></span> <span data-ttu-id="2cf38-221">Тем не менее,  если вы видите какие-либо сообщения об ошибках, необходимо устранить эти проблемы, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="2cf38-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="2cf38-222">Создайте кластер ото всех серверов Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="2cf38-223">В **мастере управления кластером** для отбойной передачи щелкните правой кнопкой мыши "Управление отбойным кластером" и выберите **"Создать кластер".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="2cf38-224">На странице **Перед началом работы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-225">Добавьте имя кластера и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="2cf38-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="2cf38-226">После проверки параметров нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-227">На странице Подтверждение нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-228">После создания кластера нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="2cf38-229">Рекомендуется настроить параметры кворума кластера для использования файловой папки-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="2cf38-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="2cf38-230">Для этого сделайте вот что:</span><span class="sxs-lookup"><span data-stu-id="2cf38-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="2cf38-231">Щелкните правой кнопкой мыши имя кластера, выберите "Дополнительные действия" и выберите "Настройка параметров **кворума кластера".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="2cf38-232">На странице **"Выбор параметра конфигурации кворума"** щелкните **"Выберите свидетель кворума".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="2cf38-233">На странице **"Выбор свидетеля кворума"** щелкните **"Настройка файловой папки-свидетеля".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="2cf38-234">На странице **"Настройка файлового свидетеля"** введите путь к нужному файловому файлу и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-235">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="2cf38-236">На каждом сервере в кластере в SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2cf38-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="2cf38-237">Откройте диспетчер конфигураций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="2cf38-238">В дереве в левой части экрана щелкните SQL Server **services,** а затем дважды щелкните SQL Server службу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="2cf38-239">В поле **"Свойства"** выберите вкладку **"Высокий уровень доступности AlwaysOn".** Выберите **"Включить группы доступности AlwaysOn".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="2cf38-240">Перезапустите SQL Server по запросу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="2cf38-241">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="2cf38-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="2cf38-242">Откройте SQL Server Management Studio и подключите его к SQL Server экземпляру.</span><span class="sxs-lookup"><span data-stu-id="2cf38-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="2cf38-243">В обозревателе объектов разоберете папку **"Высокий уровень доступности Always On".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="2cf38-244">Щелкните правой кнопкой мыши папку **"Группы** доступности" и выберите "Мастер новой **группы доступности".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="2cf38-245">Если **появится страница** "Введение", нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="2cf38-246">На странице **"Указание имени группы** доступности" введите имя группы доступности и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="2cf38-247">На странице "Выбор баз данных" выберите базы данных, которые необходимо включить в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2cf38-248">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="2cf38-249">Не включайте базы данных **ReportServer,** **ReportServerTempDB** или Persistent Chat в группу доступности AlwaysOn, так как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2cf38-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="2cf38-250">Вы можете включить все остальные базы данных Skype для бизнеса Server в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2cf38-251">На странице **"Указание реплик"** перейдите на вкладку **"Реплики".** Затем нажмите **кнопку "Добавить** реплики" и подключите другие экземпляры SQL, которые вы присоединили как узлы кластера для отключении Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="2cf38-252">Для каждого экземпляра выберите параметры **автоматической отключки** и **синхронной фиксации.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="2cf38-253">Не выбирайте параметр **"Читаемый дополнительный".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="2cf38-254">Перейдите **на вкладку "Конечные** точки" и убедитесь, что для номера **порта** установлено число 5022.</span><span class="sxs-lookup"><span data-stu-id="2cf38-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="2cf38-255">Перейдите **на вкладку** "Прослушиватель" и выберите параметр **"Создать прослушиватель группы доступности".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="2cf38-256">В этом параметре введите имя прослушиватель  и заведите порт 1433 (другие порты для этого параметра не поддерживаются).</span><span class="sxs-lookup"><span data-stu-id="2cf38-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="2cf38-257">Нажмите **кнопку**"Добавить", а затем в **поле IPv4-адреса** уканите предпочитаемый виртуальный IP-адрес и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="2cf38-258">На  странице "Выбор начальной синхронизации данных" выберите "Полная" и укажите папку, доступную репликам, и для учетной записи службы SQL Server, используемой обеими репликами, есть разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="2cf38-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="2cf38-259">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="2cf38-260">Эта папка будет временно использоваться при инициализации баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cf38-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="2cf38-261">При работе с большими базами данных рекомендуется вручную инициализировать их, если пропускная способность сети не может вместить размер резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cf38-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="2cf38-262">На странице проверки убедитесь, что все проверки успешно, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="2cf38-263">На странице **"Сводка"** проверьте все параметры и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="2cf38-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="2cf38-264">Создайте новое хранилище, указав прослушиватель AG и указав в качестве основного узла AG основной основной узел старого зеркала.</span><span class="sxs-lookup"><span data-stu-id="2cf38-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="2cf38-265">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2cf38-265">Open Topology Builder.</span></span> <span data-ttu-id="2cf38-266">В топологии разйдите раздел "Общие компоненты", щелкните правой кнопкой мыши SQL Server **"Магазины"** и выберите "Новый SQL Server **Store".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="2cf38-267">На странице "Определение нового **SQL Store"**  сначала выберите "Параметры высокой доступности", а затем убедитесь, что в этом SQL группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="2cf38-268">В поле **SQL Server FQDN** прослушиватель доступности введите FQDN прослушиватель, созданный при создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="2cf38-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="2cf38-269">В поле **SQL Server FQDN** введите FQDN основного узла AG и нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="2cf38-270">Это должен быть основной частью старого зеркала для этого магазина.</span><span class="sxs-lookup"><span data-stu-id="2cf38-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="2cf38-271">Связать новую ag с пулом переднего конца.</span><span class="sxs-lookup"><span data-stu-id="2cf38-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="2cf38-272">В построитель топологий щелкните правой кнопкой мыши пул, чтобы связать его с ag, и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="2cf38-273">В **области "Связи"** в **SQL Server Store** выберите ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="2cf38-274">Выберите ту же группу для любых других баз данных в пуле, которые нужно переместить в группу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="2cf38-275">Убедившись, что все необходимые базы данных настроены на ag, нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="2cf38-276">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2cf38-276">Publish the topology.</span></span> <span data-ttu-id="2cf38-277">В меню **действий** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2cf38-278">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="2cf38-279">Выполните некоторые последние действия, чтобы SQL учетные записи для входа в каждую реплику в группе доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2cf38-280">Откройте построитель топологий, выберите **"Загрузить топологию" из** существующего развертывания и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="2cf38-281">Развяйте Skype для бизнеса Server, развяйте топологию и **SQL Server магазинах.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2cf38-282">Щелкните правой кнопкой мыши SQL новой ag и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="2cf38-283">В нижней части страницы в SQL Server **FQDN** измените значение на FQDN прослушиватель AG.</span><span class="sxs-lookup"><span data-stu-id="2cf38-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="2cf38-284">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2cf38-284">Publish the topology.</span></span> <span data-ttu-id="2cf38-285">В меню **действий** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2cf38-286">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="2cf38-287">Затем подождите несколько минут, пока не будет реплицироваться новая топология.</span><span class="sxs-lookup"><span data-stu-id="2cf38-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="2cf38-288">Откройте SQL Server Management Studio и перейдите к ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="2cf38-289">Перенаправь его на вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="2cf38-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="2cf38-290">Откройте skype for Business Server Management Shell и введите следующий SQL для входа в эту реплику:</span><span class="sxs-lookup"><span data-stu-id="2cf38-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="2cf38-291">Повторите два предыдущих шага (перенаправляйте группу на вторичную реплику, а затем используйте) для каждой  `Install-CsDatabase -Update` реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="2cf38-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="2cf38-292">Развертывание группы доступности Always On в существующем пуле, который не использует зеркальное отражение базы данных</span><span class="sxs-lookup"><span data-stu-id="2cf38-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="2cf38-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="2cf38-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="2cf38-294">Если в пуле, обновляемом до ag, размещено центральное хранилище управления для организации, перед обновлением этого пула необходимо сначала переместить CMS в другой пул.</span><span class="sxs-lookup"><span data-stu-id="2cf38-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="2cf38-295">Используйте Move-CsManagementServer для перемещения пула.</span><span class="sxs-lookup"><span data-stu-id="2cf38-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="2cf38-296">Если в организации нет другого пула, можно временно развернуть сервер Standard Edition и переместить CMS на этот сервер перед обновлением пула до ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="2cf38-297">Настройка функции failover Clustering на всех серверах баз данных, которые будут частью ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="2cf38-298">На каждом сервере сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2cf38-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="2cf38-299">Откройте диспетчер серверов и **нажмите кнопку "Добавить роли и функции".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="2cf38-300">**Нажимайте кнопку** "Далее", пока не дойдете до **окна "Выбор компонентов".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="2cf38-301">В этом поле выберите **"Отбойная кластеризация".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="2cf38-302">В **окне "Добавление компонентов, необходимых для кластерной** отбойной работы", нажмите кнопку **"Добавить функции".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="2cf38-303">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="2cf38-304">Проверьте конфигурацию кластера.</span><span class="sxs-lookup"><span data-stu-id="2cf38-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="2cf38-305">В диспетчере серверов выберите меню **"Инструменты",** а затем пункт **"Диспетчер отбойных кластеров".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="2cf38-306">В **области "Действия"** в правой части экрана щелкните **"Проверить конфигурацию".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="2cf38-307">На странице **Перед началом работы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-308">Выберите серверы для добавления в кластер и нажмите кнопку **"Выполнить все тесты".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="2cf38-309">В поле **сводки** проверьте все ошибки, которые сообщает мастер.</span><span class="sxs-lookup"><span data-stu-id="2cf38-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="2cf38-310">Затем нажмите **кнопку "Готово",** чтобы завершить проверку.</span><span class="sxs-lookup"><span data-stu-id="2cf38-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="2cf38-311">Возможно, мастер вывести несколько предупреждений, особенно если вы не используете общее хранилище.</span><span class="sxs-lookup"><span data-stu-id="2cf38-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="2cf38-312">Использование общего хранилища не требуется.</span><span class="sxs-lookup"><span data-stu-id="2cf38-312">You are not required to use shared storage.</span></span> <span data-ttu-id="2cf38-313">Тем не менее,  если вы видите какие-либо сообщения об ошибках, необходимо устранить эти проблемы, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="2cf38-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="2cf38-314">Создание кластера windows Server Failover Cluster (WSFC).</span><span class="sxs-lookup"><span data-stu-id="2cf38-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="2cf38-315">В **мастере управления кластером** для отбойной передачи щелкните правой кнопкой мыши "Управление отбойным кластером" и выберите **"Создать кластер".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="2cf38-316">На странице **Перед началом работы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-317">Добавьте имя кластера и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="2cf38-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="2cf38-318">После проверки параметров нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-319">На странице Подтверждение нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-320">После создания кластера нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="2cf38-321">Рекомендуется настроить параметры кворума кластера для использования файловой папки-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="2cf38-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="2cf38-322">Для этого сделайте вот что:</span><span class="sxs-lookup"><span data-stu-id="2cf38-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="2cf38-323">Щелкните правой кнопкой мыши имя кластера, выберите "Дополнительные действия" и выберите "Настройка параметров **кворума кластера".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="2cf38-324">На странице **"Выбор параметра конфигурации кворума"** щелкните **"Выберите свидетель кворума".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="2cf38-325">На странице **"Выбор свидетеля кворума"** щелкните **"Настройка файловой папки-свидетеля".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="2cf38-326">На странице **"Настройка файлового свидетеля"** введите путь к нужному файловому файлу и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-327">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="2cf38-328">На каждом сервере в кластере в SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2cf38-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="2cf38-329">Откройте диспетчер конфигураций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2cf38-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="2cf38-330">В дереве в левой части экрана щелкните SQL Server **services,** а затем дважды щелкните SQL Server службу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="2cf38-331">В поле **"Свойства"** выберите вкладку **"Высокий уровень доступности AlwaysOn".** Выберите **"Включить группы доступности AlwaysOn".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="2cf38-332">Перезапустите SQL Server по запросу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="2cf38-333">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="2cf38-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="2cf38-334">Откройте SQL Server Management Studio и подключите его к SQL Server экземпляру.</span><span class="sxs-lookup"><span data-stu-id="2cf38-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="2cf38-335">В обозревателе объектов разоберете папку **"Высокий уровень доступности Always On".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="2cf38-336">Щелкните правой кнопкой мыши папку **"Группы** доступности" и выберите "Мастер новой **группы доступности".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="2cf38-337">Если **появится страница** "Введение", нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-338">На странице **"Указание имени группы** доступности" введите имя группы доступности и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-339">На странице "Выбор баз данных" выберите базы данных, которые необходимо включить в ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="2cf38-340">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="2cf38-341">Не включайте базы данных **ReportServer,** **ReportServerTempDB** или Persistent Chat в ag, так как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2cf38-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="2cf38-342">Вы можете включить все остальные базы данных Skype для бизнеса Server в ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="2cf38-343">На странице **"Указание реплик"** перейдите на вкладку **"Реплики".** Затем нажмите **кнопку "Добавить реплики"** и подключите другие экземпляры SQL, которые вы присоединили как узлы WSFC.</span><span class="sxs-lookup"><span data-stu-id="2cf38-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="2cf38-344">Для каждого экземпляра выберите параметры **автоматической отключки** и **синхронной фиксации.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="2cf38-345">Не выбирайте параметр **"Читаемый дополнительный".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="2cf38-346">Перейдите **на вкладку "Конечные** точки" и убедитесь, что для номера **порта** установлено число 5022.</span><span class="sxs-lookup"><span data-stu-id="2cf38-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="2cf38-347">Перейдите **на вкладку** "Прослушиватель" и выберите параметр **"Создать прослушиватель группы доступности".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="2cf38-348">В этом параметре введите имя прослушиватель  и заведите порт 1433 (другие порты для этого параметра не поддерживаются).</span><span class="sxs-lookup"><span data-stu-id="2cf38-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="2cf38-349">Нажмите **кнопку**"Добавить", а затем в **поле IPv4-адреса** уканите предпочитаемый виртуальный IP-адрес и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="2cf38-350">На  странице "Выбор начальной синхронизации данных" выберите "Полная" и укажите папку, доступную репликам, и для учетной записи службы SQL Server, используемой обеими репликами, есть разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="2cf38-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="2cf38-351">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2cf38-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="2cf38-352">Эта папка будет временно использоваться при инициализации баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cf38-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="2cf38-353">При работе с большими базами данных рекомендуется вручную инициализировать их, если пропускная способность сети не может вместить размер резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cf38-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="2cf38-354">На странице проверки убедитесь, что все проверки успешно, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="2cf38-355">На странице **"Сводка"** проверьте все параметры и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="2cf38-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="2cf38-356">Создайте новое хранилище, указывав прослушиватель AG.</span><span class="sxs-lookup"><span data-stu-id="2cf38-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="2cf38-357">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2cf38-357">Open Topology Builder.</span></span> <span data-ttu-id="2cf38-358">В топологии разйдите раздел "Общие компоненты", щелкните правой кнопкой мыши SQL Server **"Магазины"** и выберите "Новый SQL Server **Store".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="2cf38-359">На странице "Определение нового **SQL Store"**  сначала выберите "Параметры высокой доступности", а затем убедитесь, что в этом SQL группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2cf38-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="2cf38-360">В поле **SQL Server FQDN** прослушиватель доступности введите FQDN прослушиватель, созданный при создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="2cf38-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="2cf38-361">В поле **SQL Server FQDN** введите FQDN основного узла AG и нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="2cf38-362">Связать новую группу доступности Always On с пулом переднего доступа.</span><span class="sxs-lookup"><span data-stu-id="2cf38-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="2cf38-363">В построитель топологий щелкните правой кнопкой мыши пул, чтобы связать его с ag, и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="2cf38-364">В **области "Связи"** в **SQL Server Store** выберите ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="2cf38-365">Выберите ту же группу для любых других баз данных в пуле, которые нужно переместить в группу.</span><span class="sxs-lookup"><span data-stu-id="2cf38-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="2cf38-366">Убедившись, что все необходимые базы данных настроены на ag, нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="2cf38-367">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2cf38-367">Publish the topology.</span></span> <span data-ttu-id="2cf38-368">В меню **действий** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2cf38-369">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="2cf38-370">Выполните некоторые последние действия, чтобы SQL учетные записи для входа в каждую реплику в AG.</span><span class="sxs-lookup"><span data-stu-id="2cf38-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="2cf38-371">Откройте построитель топологий, выберите **"Загрузить топологию" из** существующего развертывания и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="2cf38-372">Развяйте Skype для бизнеса Server, развяйте топологию и **SQL Server магазинах.**</span><span class="sxs-lookup"><span data-stu-id="2cf38-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2cf38-373">Щелкните правой кнопкой мыши SQL новой ag и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="2cf38-374">В нижней части страницы в SQL Server **FQDN** измените значение на FQDN прослушиватель AG.</span><span class="sxs-lookup"><span data-stu-id="2cf38-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="2cf38-375">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2cf38-375">Publish the topology.</span></span> <span data-ttu-id="2cf38-376">В меню **действий** **щелкните "Топология",** а затем **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2cf38-377">Затем на странице подтверждения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="2cf38-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="2cf38-378">Затем подождите несколько минут, пока не будет реплицироваться новая топология.</span><span class="sxs-lookup"><span data-stu-id="2cf38-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="2cf38-379">Откройте SQL Server Management Studio и перейдите к ag.</span><span class="sxs-lookup"><span data-stu-id="2cf38-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="2cf38-380">Перенаправь его на вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="2cf38-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="2cf38-381">Откройте skype for Business Server Management Shell и введите следующий SQL для входа в эту реплику:</span><span class="sxs-lookup"><span data-stu-id="2cf38-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="2cf38-382">Повторите два предыдущих шага (перенаправляйте группу на вторичную реплику, а затем используйте) для каждой  `Install-CsDatabase -Update` реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="2cf38-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
