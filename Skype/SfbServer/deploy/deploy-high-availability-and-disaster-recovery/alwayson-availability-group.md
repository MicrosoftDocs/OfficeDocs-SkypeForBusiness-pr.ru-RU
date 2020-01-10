---
title: Развертывание группы доступности Always on на обратном стороне сервера в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Разверните (установите) группу доступности Always On в развертывании Skype для бизнеса Server.
ms.openlocfilehash: eadf3c67f5d2618d7070c2a3540c2a9ad08b5942
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002919"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="dc1af-103">Развертывание группы доступности Always on на обратном стороне сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc1af-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="dc1af-104">Разверните (установите) группу доступности Always On (AG) в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="dc1af-105">Способ развертывания AG зависит от того, выполняется ли развертывание в новом пуле, в существующем пуле, использующем зеркальное отображение, или в существующем пуле, в настоящее время не имеющего высокой доступности для серверной базы данных.</span><span class="sxs-lookup"><span data-stu-id="dc1af-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc1af-106">Использование AG с ролью сервера сохраняемого чата не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="dc1af-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="dc1af-107">Развертывание группы доступности Always On в новом пуле переднего плана</span><span class="sxs-lookup"><span data-stu-id="dc1af-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="dc1af-108">Развертывание группы доступности Always On в существующем пуле, использующем зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="dc1af-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="dc1af-109">Развертывание группы доступности Always On в существующем пуле, который не использует зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="dc1af-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="dc1af-110">Развертывание группы доступности Always On в новом пуле переднего плана</span><span class="sxs-lookup"><span data-stu-id="dc1af-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="dc1af-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="dc1af-111"></span></span>

1. <span data-ttu-id="dc1af-112">Включите функцию отказоустойчивой кластеризации на всех серверах баз данных, которые будут входить в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="dc1af-113">On each server, do the following</span><span class="sxs-lookup"><span data-stu-id="dc1af-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="dc1af-114">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="dc1af-p102">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="dc1af-117">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="dc1af-118">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="dc1af-119">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="dc1af-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="dc1af-120">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="dc1af-121">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="dc1af-122">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-123">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="dc1af-p103">В поле **Сводка** отметьте все ошибки, обнаруженные в ходе работы мастера. Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p103">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="dc1af-p104">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="dc1af-129">Создайте отказоустойчивый кластер Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="dc1af-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="dc1af-130">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="dc1af-131">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-p105">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-134">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-135">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="dc1af-p106">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="dc1af-138">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="dc1af-139">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="dc1af-140">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="dc1af-141">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-142">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="dc1af-143">На каждом сервере в кластере включите функцию AG в диспетчере конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="dc1af-p107">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="dc1af-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="dc1af-p108">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="dc1af-148">Используйте построитель топологии для создания пула переднего плана, как описано в разделе [Создание и публикация новой топологии в Skype для бизнеса Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="dc1af-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="dc1af-149">После этого укажите AG для пула в качестве хранилища SQL.</span><span class="sxs-lookup"><span data-stu-id="dc1af-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="dc1af-150">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="dc1af-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="dc1af-151">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="dc1af-152">В обозревателе объектов разверните папку " **всегда в высоком уровне доступности** ".</span><span class="sxs-lookup"><span data-stu-id="dc1af-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="dc1af-153">Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="dc1af-154">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-155">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-156">На странице Выбор баз данных выберите базы данных, которые вы хотите включить в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dc1af-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="dc1af-157">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="dc1af-158">Не включайте базы данных **ReportServer**, **reportservertempdb**и persistent чата в группу доступности AlwaysOn, так как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="dc1af-159">В группу доступности AlwaysOn вы можете включить все другие базы данных Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="dc1af-160">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="dc1af-p113">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p113">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="dc1af-163">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="dc1af-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="dc1af-p114">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="dc1af-p114">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="dc1af-166">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="dc1af-p115">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p115">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="dc1af-p116">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p116">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="dc1af-171">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-172">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="dc1af-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="dc1af-173">После развертывания пула и AG выполните некоторые заключительные действия, чтобы убедиться, что имена входа SQL находятся на каждой реплике в группе доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dc1af-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="dc1af-174">Откройте конфигуратор топологии, выберите пункт **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="dc1af-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="dc1af-176">Щелкните правой кнопкой мыши хранилище SQL для новой группы доступности AlwaysOn и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="dc1af-177">В нижней части страницы в поле **FQDN сервера SQL Server** измените значение на полное доменное имя прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="dc1af-p118">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="dc1af-182">Откройте центр SQL Server Management Studio и перейдите в "AG".</span><span class="sxs-lookup"><span data-stu-id="dc1af-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="dc1af-183">Fail it over to a secondary replica.</span><span class="sxs-lookup"><span data-stu-id="dc1af-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="dc1af-184">Откройте командную консоль управления Skype для бизнеса Server и введите следующий командлет для создания имен входа SQL в этой реплике:</span><span class="sxs-lookup"><span data-stu-id="dc1af-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="dc1af-185">Повторите предыдущие два действия (для группы с помощью дополнительной реплики), а затем используйте `Install-CsDatabase -Update`ее для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="dc1af-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="dc1af-186">Развертывание группы доступности Always On в существующем пуле, использующем зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="dc1af-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="dc1af-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="dc1af-187"></span></span>

> [!NOTE]
> <span data-ttu-id="dc1af-188">Если в пуле, который вы обновляете до AG, размещено центральное хранилище управления для Организации, необходимо сначала переместить CMS в другой пул, прежде чем обновлять этот пул.</span><span class="sxs-lookup"><span data-stu-id="dc1af-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="dc1af-189">Use the Move-CsManagementServer cmdlet to move the pool.</span><span class="sxs-lookup"><span data-stu-id="dc1af-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="dc1af-190">Если у вас нет другого пула в вашей организации, вы можете временно развернуть сервер Standard Edition и переместить CMS на этот сервер перед обновлением пула до AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="dc1af-191">Чтобы перенести все данные из зеркала на основной узел, откройте консоль управления Skype для бизнеса Server и введите следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="dc1af-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="dc1af-p121">Повторно выполните этот командлет для каждого типа баз данных в пуле. Для поиска всех типов баз данных, хранящихся в пуле, можно выполнить следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="dc1af-194">Для удаления зеркального отображения базы данных из пула используйте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="dc1af-195">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-195">Open Topology Builder.</span></span> <span data-ttu-id="dc1af-196">В данной топологии разверните узел **Пулы переднего плана Enterprise Edition**, щелкните имя пула правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="dc1af-197">Для каждого типа хранилищ SQL в пуле снимите флажок, **разрешающий зеркальное отображение хранилищ SQL Store Mirroring**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="dc1af-p123">Опубликуйте измененную топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="dc1af-201">С помощью Microsoft SQL Server Management Studio отключите зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="dc1af-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="dc1af-p124">Откройте SQL Server Management Studio, перейдите к базам данных, щелкните **Задачи** правой кнопкой мыши и выберите **Зеркало**. Затем щелкните **Отключить отображение** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="dc1af-204">Повторите эти действия для всех баз данных в пуле, которые будут преобразованы в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="dc1af-205">Настройте функцию отказоустойчивой кластеризации на всех серверах баз данных, которые будут входить в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="dc1af-206">On each server, do the following</span><span class="sxs-lookup"><span data-stu-id="dc1af-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="dc1af-207">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="dc1af-p126">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="dc1af-210">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="dc1af-211">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="dc1af-212">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="dc1af-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="dc1af-213">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="dc1af-214">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="dc1af-215">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-216">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="dc1af-p127">В поле **Сводка** отметьте все ошибки, обнаруженные в ходе работы мастера. Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p127">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="dc1af-p128">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="dc1af-222">Создайте отказоустойчивый кластер Windows Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="dc1af-223">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="dc1af-224">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-p129">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-227">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-228">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="dc1af-p130">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="dc1af-231">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="dc1af-232">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="dc1af-233">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="dc1af-234">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-235">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="dc1af-236">На каждом сервере в кластере включите функцию AG в диспетчере конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="dc1af-p131">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="dc1af-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="dc1af-p132">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="dc1af-241">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="dc1af-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="dc1af-242">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="dc1af-243">В обозревателе объектов разверните папку " **всегда в высоком уровне доступности** ".</span><span class="sxs-lookup"><span data-stu-id="dc1af-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="dc1af-244">Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="dc1af-245">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="dc1af-246">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="dc1af-247">На странице Выбор баз данных выберите базы данных, которые вы хотите включить в группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dc1af-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="dc1af-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="dc1af-249">Не включайте базы данных **ReportServer**, **reportservertempdb**и persistent чата в группу доступности AlwaysOn, так как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="dc1af-250">В группу доступности AlwaysOn вы можете включить все другие базы данных Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="dc1af-251">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="dc1af-p136">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="dc1af-254">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="dc1af-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="dc1af-p137">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="dc1af-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="dc1af-257">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="dc1af-p138">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="dc1af-p139">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="dc1af-262">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="dc1af-263">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="dc1af-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="dc1af-264">Создание нового магазина с указанием прослушивателя AG и указанием участника старого зеркала в качестве основного узла для AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="dc1af-265">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-265">Open Topology Builder.</span></span> <span data-ttu-id="dc1af-266">В данной топологии разверните узел **Общие компоненты**, щелкните **Хранилища SQL Server** правой кнопкой мыши и выберите **Создать хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="dc1af-267">На странице **Определение нового хранилища SQL Server** сначала установите флажок **Параметры высокого уровня доступности**, затем убедитесь в том, что в раскрывающемся списке отображаются группы доступности SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dc1af-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="dc1af-268">В поле **Полное доменное имя прослушивателя группы доступности SQL Server** введите полное доменное имя прослушивателя, созданного в процессе создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="dc1af-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="dc1af-269">В поле **FQDN сервера SQL Server** введите полное доменное имя основного узла AG и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="dc1af-270">This should be the principal of the old mirror for this store.</span><span class="sxs-lookup"><span data-stu-id="dc1af-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="dc1af-271">Свяжите новую AG с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="dc1af-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="dc1af-272">В построителе топологии щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="dc1af-273">В разделе **связи**в поле **хранилище SQL Server** выберите AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="dc1af-274">Выберите одну и ту же группу для всех баз данных в пуле, которые вы хотите переместить в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="dc1af-275">Убедившись в том, что все необходимые базы данных настроены для AG, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="dc1af-276">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="dc1af-276">Publish the topology.</span></span> <span data-ttu-id="dc1af-277">В меню **Действие** щелкните **Топология**, затем **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="dc1af-278">Затем на странице подтверждения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="dc1af-279">Выполните некоторые заключительные действия, чтобы убедиться, что имена входа SQL находятся на каждой реплике в группе доступность AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dc1af-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="dc1af-280">Откройте конфигуратор топологии, выберите пункт **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="dc1af-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="dc1af-282">Щелкните правой кнопкой мыши хранилище SQL нового AG и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="dc1af-283">В нижней части страницы в поле **FQDN сервера SQL Server** измените значение на полное доменное имя прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="dc1af-p145">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="dc1af-288">Откройте центр SQL Server Management Studio и перейдите в "AG".</span><span class="sxs-lookup"><span data-stu-id="dc1af-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="dc1af-289">Fail it over to a secondary replica.</span><span class="sxs-lookup"><span data-stu-id="dc1af-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="dc1af-290">Откройте командную консоль управления Skype для бизнеса Server и введите следующий командлет для создания имен входа SQL в этой реплике:</span><span class="sxs-lookup"><span data-stu-id="dc1af-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="dc1af-291">Повторите предыдущие два действия (для группы с помощью дополнительной реплики), а затем используйте `Install-CsDatabase -Update`ее для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="dc1af-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="dc1af-292">Развертывание группы доступности Always On в существующем пуле, который не использует зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="dc1af-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="dc1af-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="dc1af-293"></span></span>

> [!NOTE]
> <span data-ttu-id="dc1af-294">Если в пуле, который вы обновляете до AG, размещено центральное хранилище управления для Организации, необходимо сначала переместить CMS в другой пул, прежде чем обновлять этот пул.</span><span class="sxs-lookup"><span data-stu-id="dc1af-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="dc1af-295">Use the Move-CsManagementServer cmdlet to move the pool.</span><span class="sxs-lookup"><span data-stu-id="dc1af-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="dc1af-296">Если у вас нет другого пула в вашей организации, вы можете временно развернуть сервер Standard Edition и переместить CMS на этот сервер перед обновлением пула до AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="dc1af-297">Настройте функцию отказоустойчивой кластеризации на всех серверах баз данных, которые будут входить в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="dc1af-298">On each server, do the following</span><span class="sxs-lookup"><span data-stu-id="dc1af-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="dc1af-299">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="dc1af-p149">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="dc1af-302">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="dc1af-303">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="dc1af-304">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="dc1af-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="dc1af-305">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="dc1af-306">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="dc1af-307">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-308">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="dc1af-p150">В поле **Сводка** отметьте все ошибки, обнаруженные в ходе работы мастера. Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p150">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="dc1af-p151">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="dc1af-314">Создайте отказоустойчивый кластер Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="dc1af-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="dc1af-315">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="dc1af-316">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-p152">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-319">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-320">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="dc1af-p153">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="dc1af-323">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="dc1af-324">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="dc1af-325">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="dc1af-326">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-327">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="dc1af-328">На каждом сервере в кластере включите AG в диспетчере конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="dc1af-p154">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="dc1af-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="dc1af-p155">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="dc1af-333">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="dc1af-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="dc1af-334">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc1af-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="dc1af-335">В обозревателе объектов разверните папку " **всегда в высоком уровне доступности** ".</span><span class="sxs-lookup"><span data-stu-id="dc1af-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="dc1af-336">Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="dc1af-337">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-338">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-339">На странице Выбор баз данных выберите базы данных, которые вы хотите включить в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="dc1af-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="dc1af-341">Не включайте базы данных **ReportServer**, **reportservertempdb**и сохраняемые чата в AG, так как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="dc1af-342">Вы можете включить все другие базы данных Skype для бизнеса Server в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="dc1af-343">На странице **Определение реплики** перейдите на вкладку **реплики** . Затем нажмите кнопку **Добавить реплики** и подключитесь к другим экземплярам SQL, которые вы присоединились как узлы WSFC.</span><span class="sxs-lookup"><span data-stu-id="dc1af-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="dc1af-p159">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="dc1af-346">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="dc1af-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="dc1af-p160">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="dc1af-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="dc1af-349">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="dc1af-p161">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="dc1af-p162">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="dc1af-354">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="dc1af-355">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="dc1af-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="dc1af-356">Создание нового магазина с указанием прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="dc1af-357">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="dc1af-357">Open Topology Builder.</span></span> <span data-ttu-id="dc1af-358">В данной топологии разверните узел **Общие компоненты**, щелкните **Хранилища SQL Server** правой кнопкой мыши и выберите **Создать хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="dc1af-359">На странице **Определение нового хранилища SQL Server** сначала установите флажок **Параметры высокого уровня доступности**, затем убедитесь в том, что в раскрывающемся списке отображаются группы доступности SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dc1af-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="dc1af-360">В поле **Полное доменное имя прослушивателя группы доступности SQL Server** введите полное доменное имя прослушивателя, созданного в процессе создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="dc1af-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="dc1af-361">В поле **FQDN сервера SQL Server** введите полное доменное имя основного узла AG и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="dc1af-362">Свяжите новую группу доступности Always On с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="dc1af-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="dc1af-363">В построителе топологии щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="dc1af-364">В разделе **связи**в поле **хранилище SQL Server** выберите AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="dc1af-365">Выберите одну и ту же группу для всех баз данных в пуле, которые вы хотите переместить в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="dc1af-366">Убедившись в том, что все необходимые базы данных настроены для AG, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="dc1af-367">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="dc1af-367">Publish the topology.</span></span> <span data-ttu-id="dc1af-368">В меню **Действие** щелкните **Топология**, затем **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="dc1af-369">Затем на странице подтверждения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="dc1af-370">Выполните некоторые заключительные действия, чтобы убедиться в том, что логины SQL находятся на каждой реплике в AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="dc1af-371">Откройте конфигуратор топологии, выберите пункт **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="dc1af-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="dc1af-373">Щелкните правой кнопкой мыши хранилище SQL нового AG и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc1af-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="dc1af-374">В нижней части страницы в поле **FQDN сервера SQL Server** измените значение на полное доменное имя прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="dc1af-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="dc1af-p167">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="dc1af-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="dc1af-379">Откройте центр SQL Server Management Studio и перейдите в "AG".</span><span class="sxs-lookup"><span data-stu-id="dc1af-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="dc1af-380">Fail it over to a secondary replica.</span><span class="sxs-lookup"><span data-stu-id="dc1af-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="dc1af-381">Откройте командную консоль управления Skype для бизнеса Server и введите следующий командлет для создания имен входа SQL в этой реплике:</span><span class="sxs-lookup"><span data-stu-id="dc1af-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="dc1af-382">Повторите предыдущие два действия (для группы с помощью дополнительной реплики), а затем используйте `Install-CsDatabase -Update`ее для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="dc1af-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
