---
title: Развертывание группы доступности AlwaysOn на внутреннем сервере Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Развертывание развертывания (установить) группы обеспечения доступности AlwaysOn в вашей Скайп для Business Server.
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="2c230-103">Развертывание группы доступности AlwaysOn на внутреннем сервере Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2c230-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c230-104">Развертывание развертывания (установить) группы обеспечения доступности AlwaysOn в вашей Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="2c230-105">Развертыванием группы обеспечения доступности AlwaysOn зависит от того, является ли вы развертываете его в новый пул, существующего пула, который использует зеркальное отображение или существующего пула, который в данный момент находится не высокой доступности для Тыловой базой данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c230-106">Использование группы обеспечения доступности AlwaysOn с ролью сервера сохраняемого чата не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2c230-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2c230-107">Имена экземпляров для нескольких экземпляров группы обеспечения доступности AlwaysOn должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="2c230-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="2c230-108">Развертывание группы доступности AlwaysOn в новом пуле внешнего сервера</span><span class="sxs-lookup"><span data-stu-id="2c230-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="2c230-109">Развертывание группы доступности AlwaysOn в существующем пуле, где применяется зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="2c230-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="2c230-110">Развертывание группы доступности AlwaysOn в существующем пуле, где не применяется зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="2c230-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="2c230-111">Развертывание группы доступности AlwaysOn в новом пуле внешнего сервера</span><span class="sxs-lookup"><span data-stu-id="2c230-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="2c230-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="2c230-112"></span></span>

1. <span data-ttu-id="2c230-113">Настройка отказоустойчивой кластеризации Windows Server на всех серверах базы данных, которые будут частью группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-114">На каждом сервере выполните указанные ниже</span><span class="sxs-lookup"><span data-stu-id="2c230-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="2c230-115">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="2c230-p102">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="2c230-118">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="2c230-119">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2c230-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="2c230-120">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="2c230-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="2c230-121">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="2c230-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="2c230-122">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="2c230-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="2c230-123">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-124">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="2c230-125">В окне "**Сводка** " Проверьте все ошибки, которые мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="2c230-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="2c230-126">Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="2c230-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="2c230-p104">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="2c230-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="2c230-130">Создайте кластер.</span><span class="sxs-lookup"><span data-stu-id="2c230-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="2c230-131">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="2c230-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="2c230-132">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-p105">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-135">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-136">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2c230-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="2c230-p106">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2c230-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="2c230-139">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="2c230-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="2c230-140">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="2c230-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="2c230-141">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="2c230-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="2c230-142">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-143">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="2c230-144">На каждом сервере в кластере включите режим "Всегда включено" в диспетчере конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="2c230-p107">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="2c230-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="2c230-p108">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="2c230-149">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="2c230-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="2c230-150">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="2c230-p109">В обозревателе объектов разверните папку **Высокий уровень доступности AlwaysOn**. Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="2c230-153">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-154">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-155">На странице Выбор базы данных выберите базы данных, которые необходимо включить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-156">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="2c230-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="2c230-157">Не включайте **ReportServer**, **ReportServerTempDB**или Persistent Chat баз данных в группе обеспечения доступности AlwaysOn, как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2c230-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="2c230-158">В группе обеспечения доступности AlwaysOn можно включить все Скайп для сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="2c230-159">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="2c230-p112">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="2c230-162">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="2c230-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="2c230-p113">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="2c230-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="2c230-165">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="2c230-p114">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="2c230-p115">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="2c230-170">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-171">На странице "**Сводка** " Проверьте все параметры и нажмите кнопку Готово.</span><span class="sxs-lookup"><span data-stu-id="2c230-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="2c230-172">Используйте построитель топологий для создания пула переднего плана, как описано в статье [создания и публикации новой топологии в Скайп для Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="2c230-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="2c230-173">В этом случае укажите группы обеспечения доступности AlwaysOn хранилище SQL для пула.</span><span class="sxs-lookup"><span data-stu-id="2c230-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="2c230-174">После развертывания пула и группы обеспечения доступности AlwaysOn, выполните некоторые завершающий этап убедитесь, что имена входа SQL на каждой реплики в группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="2c230-175">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="2c230-176">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c230-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2c230-177">Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и нажмите кнопку ** Изменить свойства **.</span><span class="sxs-lookup"><span data-stu-id="2c230-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="2c230-178">В нижней части страницы в поле **Полное доменное имя SQL Server** измените значение на полное доменное имя прослушивателя группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="2c230-p118">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="2c230-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="2c230-183">Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-184">Сбое на вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="2c230-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="2c230-185">Откройте Скайп для Business Server Командная консоль и введите следующий командлет, чтобы создать входы SQL на этом реплики:</span><span class="sxs-lookup"><span data-stu-id="2c230-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="2c230-186">Повторите два предыдущих шага (переключаются в группе, чтобы вторичная реплика, а затем использовать `Install-CsDatabase -Update`) для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="2c230-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="2c230-187">Развертывание группы доступности AlwaysOn в существующем пуле, где применяется зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="2c230-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="2c230-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="2c230-188"></span></span>

> [!NOTE]
> <span data-ttu-id="2c230-189">При обновлении узлам группы обеспечения доступности AlwaysOn централизованного управления пула хранения для вашей организации, необходимо сначала переместить CMS в другой пул перед обновлением этого пула.</span><span class="sxs-lookup"><span data-stu-id="2c230-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="2c230-190">Используйте командлет Move-CsManagementServer для перемещения в пул.</span><span class="sxs-lookup"><span data-stu-id="2c230-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="2c230-191">Если у вас другой пул в вашей организации, можно временно развертывание сервера Standard Edition и переместить CMS на этом сервере перед обновлением пул для группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="2c230-192">При сбое всех данных из зеркального отображения на узел участника, открыв Скайп для консоли Business Server и введя следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="2c230-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="2c230-p121">Повторно выполните этот командлет для каждого типа баз данных в пуле. Для поиска всех типов баз данных, хранящихся в пуле, можно выполнить следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="2c230-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="2c230-195">С помощью построителя топологий отключите зеркальное отображение баз данных из пула.</span><span class="sxs-lookup"><span data-stu-id="2c230-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="2c230-196">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2c230-196">Open Topology Builder.</span></span> <span data-ttu-id="2c230-197">В данной топологии разверните узел **Пулы переднего плана Enterprise Edition**, щелкните имя пула правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2c230-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="2c230-198">Для каждого типа хранилищ SQL в пуле снимите флажок, **разрешающий зеркальное отображение хранилищ SQL Store Mirroring**.</span><span class="sxs-lookup"><span data-stu-id="2c230-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="2c230-p123">Опубликуйте измененную топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="2c230-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="2c230-202">С помощью Microsoft SQL Server Management Studio отключите зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="2c230-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="2c230-p124">Откройте SQL Server Management Studio, перейдите к базам данных, щелкните **Задачи** правой кнопкой мыши и выберите **Зеркало**. Затем щелкните **Отключить отображение** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="2c230-205">Повторите эти шаги для всех баз данных в пул, в котором будут преобразованы в группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="2c230-206">Настройка отказоустойчивой кластеризации Windows Server на всех серверах базы данных, которые будут частью группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-207">На каждом сервере выполните указанные ниже</span><span class="sxs-lookup"><span data-stu-id="2c230-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="2c230-208">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="2c230-p126">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="2c230-211">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="2c230-212">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2c230-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="2c230-213">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="2c230-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="2c230-214">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="2c230-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="2c230-215">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="2c230-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="2c230-216">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-217">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="2c230-218">В окне "**Сводка** " Проверьте все ошибки, которые мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="2c230-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="2c230-219">Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="2c230-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="2c230-p128">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="2c230-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="2c230-223">Создайте кластер.</span><span class="sxs-lookup"><span data-stu-id="2c230-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="2c230-224">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="2c230-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="2c230-225">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-p129">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-228">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-229">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2c230-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="2c230-p130">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2c230-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="2c230-232">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="2c230-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="2c230-233">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="2c230-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="2c230-234">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="2c230-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="2c230-235">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-236">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="2c230-237">На каждом сервере в кластере включите режим "Всегда включено" в диспетчере конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="2c230-p131">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="2c230-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="2c230-p132">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="2c230-242">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="2c230-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="2c230-243">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="2c230-p133">В обозревателе объектов разверните папку **Высокий уровень доступности AlwaysOn**. Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="2c230-246">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="2c230-247">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="2c230-248">На странице Выбор базы данных выберите базы данных, которые необходимо включить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-249">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="2c230-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="2c230-250">Не включайте **ReportServer**, **ReportServerTempDB**или Persistent Chat баз данных в группе обеспечения доступности AlwaysOn, как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2c230-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="2c230-251">В группе обеспечения доступности AlwaysOn можно включить все Скайп для сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-252">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="2c230-p136">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="2c230-255">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="2c230-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="2c230-p137">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="2c230-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="2c230-258">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="2c230-p138">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="2c230-p139">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="2c230-263">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="2c230-264">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="2c230-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="2c230-265">Создайте новое хранилище, указав прослушиватель группы обеспечения доступности AlwaysOn, а субъекта старой зеркальной как основной узел группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-266">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2c230-266">Open Topology Builder.</span></span> <span data-ttu-id="2c230-267">В данной топологии разверните узел **Общие компоненты**, щелкните **Хранилища SQL Server** правой кнопкой мыши и выберите **Создать хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c230-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="2c230-268">На странице **Определение нового хранилища SQL Server** сначала установите флажок **Параметры высокого уровня доступности**, затем убедитесь в том, что в раскрывающемся списке отображаются группы доступности SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="2c230-269">В поле **Полное доменное имя прослушивателя группы доступности SQL Server** введите полное доменное имя прослушивателя, созданного в процессе создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="2c230-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="2c230-270">В поле **Полное доменное имя SQL Server** введите полное доменное имя основного узла группы обеспечения доступности AlwaysOn и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="2c230-271">Это должен быть субъекта старый зеркала для этого хранилища.</span><span class="sxs-lookup"><span data-stu-id="2c230-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="2c230-272">Связывайте создания группы обеспечения доступности AlwaysOn с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2c230-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="2c230-273">В построителе топологий щелкните правой кнопкой мыши пул для связи с группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2c230-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="2c230-274">В разделе **связи**в поле **Хранилища SQL Server** выберите группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-275">Выберите ту же группу для других баз данных в пуле, который необходимо переместить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-276">Если вы уверены, что все необходимые базы данных находятся в группе обеспечения доступности AlwaysOn, нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="2c230-p143">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="2c230-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="2c230-280">Выполните некоторые окончательный действия, чтобы убедиться, что имена входа SQL на каждой реплики в группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-281">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="2c230-282">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c230-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2c230-283">Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2c230-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="2c230-284">В нижней части страницы в поле **Полное доменное имя SQL Server** измените значение на полное доменное имя прослушивателя группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-p145">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="2c230-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="2c230-289">Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-290">Сбое на вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="2c230-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="2c230-291">Откройте Скайп для Business Server Командная консоль и введите следующий командлет, чтобы создать входы SQL на этом реплики:</span><span class="sxs-lookup"><span data-stu-id="2c230-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="2c230-292">Повторите два предыдущих шага (переключаются в группе, чтобы вторичная реплика, а затем использовать `Install-CsDatabase -Update`) для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="2c230-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="2c230-293">Развертывание группы доступности AlwaysOn в существующем пуле, где не применяется зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="2c230-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="2c230-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="2c230-294"></span></span>

> [!NOTE]
> <span data-ttu-id="2c230-295">При обновлении узлам группы обеспечения доступности AlwaysOn централизованного управления пула хранения для вашей организации, необходимо сначала переместить CMS в другой пул перед обновлением этого пула.</span><span class="sxs-lookup"><span data-stu-id="2c230-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="2c230-296">Используйте командлет Move-CsManagementServer для перемещения в пул.</span><span class="sxs-lookup"><span data-stu-id="2c230-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="2c230-297">Если у вас другой пул в вашей организации, можно временно развертывание сервера Standard Edition и переместить CMS на этом сервере перед обновлением пул для группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="2c230-298">Настройка отказоустойчивой кластеризации Windows Server на всех серверах базы данных, которые будут частью группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-299">На каждом сервере выполните указанные ниже</span><span class="sxs-lookup"><span data-stu-id="2c230-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="2c230-300">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="2c230-p149">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="2c230-303">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="2c230-304">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2c230-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="2c230-305">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="2c230-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="2c230-306">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="2c230-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="2c230-307">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="2c230-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="2c230-308">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-309">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="2c230-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="2c230-310">В окне "**Сводка** " Проверьте все ошибки, которые мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="2c230-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="2c230-311">Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="2c230-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="2c230-p151">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="2c230-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="2c230-315">Создайте кластер.</span><span class="sxs-lookup"><span data-stu-id="2c230-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="2c230-316">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="2c230-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="2c230-317">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-p152">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-320">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-321">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2c230-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="2c230-p153">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2c230-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="2c230-324">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="2c230-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="2c230-325">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="2c230-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="2c230-326">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="2c230-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="2c230-327">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-328">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="2c230-329">На каждом сервере в кластере включите режим "Всегда включено" в диспетчере конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="2c230-p154">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="2c230-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="2c230-p155">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="2c230-334">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="2c230-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="2c230-335">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="2c230-p156">В обозревателе объектов разверните папку **Высокий уровень доступности AlwaysOn**. Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="2c230-338">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-339">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-340">На странице Выбор базы данных выберите базы данных, которые необходимо включить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-341">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="2c230-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="2c230-342">Не включайте **ReportServer**, **ReportServerTempDB**или Persistent Chat баз данных в группе обеспечения доступности AlwaysOn, как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2c230-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="2c230-343">В группе обеспечения доступности AlwaysOn можно включить все Скайп для сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="2c230-344">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2c230-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="2c230-p159">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="2c230-347">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="2c230-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="2c230-p160">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="2c230-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="2c230-350">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="2c230-p161">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="2c230-p162">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="2c230-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="2c230-355">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2c230-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="2c230-356">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="2c230-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="2c230-357">Создайте новое хранилище, определяющее прослушиватель группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="2c230-358">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2c230-358">Open Topology Builder.</span></span> <span data-ttu-id="2c230-359">В данной топологии разверните узел **Общие компоненты**, щелкните **Хранилища SQL Server** правой кнопкой мыши и выберите **Создать хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c230-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="2c230-360">На странице **Определение нового хранилища SQL Server** сначала установите флажок **Параметры высокого уровня доступности**, затем убедитесь в том, что в раскрывающемся списке отображаются группы доступности SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="2c230-361">В поле **Полное доменное имя прослушивателя группы доступности SQL Server** введите полное доменное имя прослушивателя, созданного в процессе создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="2c230-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="2c230-362">В поле **Полное доменное имя SQL Server** введите полное доменное имя основного узла группы обеспечения доступности AlwaysOn и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="2c230-363">Связывайте создания группы обеспечения доступности AlwaysOn с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2c230-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="2c230-364">В построителе топологий щелкните правой кнопкой мыши пул для связи с группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2c230-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="2c230-365">В разделе **связи**в поле **Хранилища SQL Server** выберите группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-366">Выберите ту же группу для других баз данных в пуле, который необходимо переместить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="2c230-367">Если вы уверены, что все необходимые базы данных находятся в группе обеспечения доступности AlwaysOn, нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="2c230-p165">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="2c230-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="2c230-371">Выполните некоторые окончательный действия, чтобы убедиться, что имена входа SQL на каждой реплики в группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-372">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c230-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="2c230-373">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c230-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2c230-374">Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и нажмите кнопку ** Изменить свойства **.</span><span class="sxs-lookup"><span data-stu-id="2c230-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="2c230-375">В нижней части страницы в поле **Полное доменное имя SQL Server** измените значение на полное доменное имя прослушивателя группы обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="2c230-p167">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="2c230-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="2c230-380">Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2c230-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2c230-381">Сбое на вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="2c230-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="2c230-382">Откройте Скайп для Business Server Командная консоль и введите следующий командлет, чтобы создать входы SQL на этом реплики:</span><span class="sxs-lookup"><span data-stu-id="2c230-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="2c230-383">Повторите два предыдущих шага (переключаются в группе, чтобы вторичная реплика, а затем использовать `Install-CsDatabase -Update`) для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="2c230-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

