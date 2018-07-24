---
title: Развертывание всегда на группы обеспечения доступности на сервере заднего плана в Скайп for Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Развертывание развертывания (установить) всегда на группы обеспечения доступности в вашей Скайп для Business Server.
ms.openlocfilehash: 93d27fc86393a28f4c0e546d034cbf9819ecce87
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026734"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="23b0f-103">Развертывание всегда на группы обеспечения доступности на сервере заднего плана в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="23b0f-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="23b0f-104">Развертывание развертывания (установить) всегда на доступность группы (AG) в вашей Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="23b0f-105">Развертыванием AG зависит от того, является ли вы развертываете его в новый пул, существующего пула, который использует зеркальное отображение или существующего пула, который в данный момент находится не высокой доступности для Тыловой базой данных.</span><span class="sxs-lookup"><span data-stu-id="23b0f-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23b0f-106">Использование AG с ролью сервера сохраняемого чата не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="23b0f-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="23b0f-107">Развертывание всегда на группы обеспечения доступности на новый пул переднего плана</span><span class="sxs-lookup"><span data-stu-id="23b0f-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="23b0f-108">Развертывание всегда на группы обеспечения доступности для существующего пула, который использует зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="23b0f-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="23b0f-109">Развертывание всегда на группы обеспечения доступности для существующего пула, который не используется зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="23b0f-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="23b0f-110">Развертывание всегда на группы обеспечения доступности на новый пул переднего плана</span><span class="sxs-lookup"><span data-stu-id="23b0f-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="23b0f-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="23b0f-111"></span></span>

1. <span data-ttu-id="23b0f-112">Активация компонента отказоустойчивый кластер на все серверы базы данных, которые будут частью AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="23b0f-113">На каждом сервере выполните указанные ниже</span><span class="sxs-lookup"><span data-stu-id="23b0f-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="23b0f-114">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="23b0f-p102">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="23b0f-117">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="23b0f-118">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="23b0f-119">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="23b0f-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="23b0f-120">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="23b0f-121">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="23b0f-122">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-123">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="23b0f-124">В окне "**Сводка** " Проверьте все ошибки, которые мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="23b0f-124">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="23b0f-125">Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="23b0f-125">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="23b0f-p104">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="23b0f-129">Создайте отказоустойчивый кластер Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="23b0f-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="23b0f-130">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="23b0f-131">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-p105">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-134">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-135">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="23b0f-p106">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="23b0f-138">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="23b0f-139">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="23b0f-140">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="23b0f-141">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-142">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="23b0f-143">На каждом сервере в кластере включите функцию AG диспетчер конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="23b0f-p107">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="23b0f-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="23b0f-p108">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="23b0f-148">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="23b0f-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="23b0f-149">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="23b0f-150">В обозревателе объектов разверните папку **Всегда высокой доступности** .</span><span class="sxs-lookup"><span data-stu-id="23b0f-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="23b0f-151">Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="23b0f-152">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-153">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-154">На странице Выбор базы данных выберите базы данных, которые необходимо включить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="23b0f-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="23b0f-155">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-155">Then click **Next**.</span></span>
    
    <span data-ttu-id="23b0f-156">Не включайте **ReportServer**, **ReportServerTempDB**или Persistent Chat баз данных в группе обеспечения доступности AlwaysOn, как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="23b0f-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="23b0f-157">В группе обеспечения доступности AlwaysOn можно включить все Скайп для сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="23b0f-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="23b0f-158">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="23b0f-p112">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="23b0f-161">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="23b0f-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="23b0f-p113">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="23b0f-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="23b0f-164">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="23b0f-p114">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="23b0f-p115">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="23b0f-169">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-170">На странице "**Сводка** " Проверьте все параметры и нажмите кнопку Готово.</span><span class="sxs-lookup"><span data-stu-id="23b0f-170">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="23b0f-171">Используйте построитель топологий для создания пула переднего плана, как описано в статье [создания и публикации новой топологии в Скайп для Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="23b0f-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="23b0f-172">В этом случае укажите AG хранилище SQL для пула.</span><span class="sxs-lookup"><span data-stu-id="23b0f-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="23b0f-173">После развертывания пула и AG, выполните некоторые завершающий этап убедитесь, что имена входа SQL на каждой реплики в группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="23b0f-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="23b0f-174">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="23b0f-175">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="23b0f-176">Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="23b0f-177">В нижней части страницы в поле **Полное доменное имя SQL Server** измените значение на полное доменное имя прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="23b0f-p118">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="23b0f-182">Откройте SQL Server Management Studio и перейдите к AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="23b0f-183">Сбое на вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="23b0f-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="23b0f-184">Откройте Скайп для Business Server Командная консоль и введите следующий командлет, чтобы создать входы SQL на этом реплики:</span><span class="sxs-lookup"><span data-stu-id="23b0f-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="23b0f-185">Повторите два предыдущих шага (переключаются в группе, чтобы вторичная реплика, а затем использовать `Install-CsDatabase -Update`) для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="23b0f-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="23b0f-186">Развертывание всегда на группы обеспечения доступности для существующего пула, который использует зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="23b0f-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="23b0f-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="23b0f-187"></span></span>

> [!NOTE]
> <span data-ttu-id="23b0f-188">Если пула, в котором обновлении AG размещается центральное хранилище управления для вашей организации, необходимо сначала переместить CMS в другой пул перед обновлением этого пула.</span><span class="sxs-lookup"><span data-stu-id="23b0f-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="23b0f-189">Используйте командлет Move-CsManagementServer для перемещения в пул.</span><span class="sxs-lookup"><span data-stu-id="23b0f-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="23b0f-190">Если у вас другой пул в вашей организации, можно временно развертывание сервера Standard Edition и переместить CMS на этом сервере перед обновлением до AG пуле.</span><span class="sxs-lookup"><span data-stu-id="23b0f-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="23b0f-191">При сбое всех данных из зеркального отображения на узел участника, открыв Скайп для консоли Business Server и введя следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="23b0f-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="23b0f-p121">Повторно выполните этот командлет для каждого типа баз данных в пуле. Для поиска всех типов баз данных, хранящихся в пуле, можно выполнить следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="23b0f-194">С помощью построителя топологий отключите зеркальное отображение баз данных из пула.</span><span class="sxs-lookup"><span data-stu-id="23b0f-194">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="23b0f-195">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="23b0f-195">Open Topology Builder.</span></span> <span data-ttu-id="23b0f-196">В данной топологии разверните узел **Пулы переднего плана Enterprise Edition**, щелкните имя пула правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="23b0f-197">Для каждого типа хранилищ SQL в пуле снимите флажок, **разрешающий зеркальное отображение хранилищ SQL Store Mirroring**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="23b0f-p123">Опубликуйте измененную топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="23b0f-201">С помощью Microsoft SQL Server Management Studio отключите зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="23b0f-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="23b0f-p124">Откройте SQL Server Management Studio, перейдите к базам данных, щелкните **Задачи** правой кнопкой мыши и выберите **Зеркало**. Затем щелкните **Отключить отображение** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="23b0f-204">Повторите эти шаги для всех баз данных в пуле, который будет преобразован в AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="23b0f-205">Установите средство отказоустойчивости кластера на всех серверах базы данных, которые будут частью AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="23b0f-206">На каждом сервере выполните указанные ниже</span><span class="sxs-lookup"><span data-stu-id="23b0f-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="23b0f-207">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="23b0f-p126">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="23b0f-210">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="23b0f-211">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="23b0f-212">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="23b0f-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="23b0f-213">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="23b0f-214">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="23b0f-215">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-216">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="23b0f-217">В окне "**Сводка** " Проверьте все ошибки, которые мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="23b0f-217">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="23b0f-218">Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="23b0f-218">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="23b0f-p128">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="23b0f-222">Создайте отказоустойчивый кластер Windows Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="23b0f-223">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="23b0f-224">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-p129">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-227">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-228">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="23b0f-p130">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="23b0f-231">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="23b0f-232">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="23b0f-233">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="23b0f-234">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-235">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="23b0f-236">На каждом сервере в кластере включите функцию AG диспетчер конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="23b0f-p131">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="23b0f-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="23b0f-p132">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="23b0f-241">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="23b0f-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="23b0f-242">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="23b0f-243">В обозревателе объектов разверните папку **Всегда высокой доступности** .</span><span class="sxs-lookup"><span data-stu-id="23b0f-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="23b0f-244">Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="23b0f-245">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="23b0f-246">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="23b0f-247">На странице Выбор базы данных выберите базы данных, которые необходимо включить в группу обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="23b0f-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="23b0f-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="23b0f-249">Не включайте **ReportServer**, **ReportServerTempDB**или Persistent Chat баз данных в группе обеспечения доступности AlwaysOn, как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="23b0f-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="23b0f-250">В группе обеспечения доступности AlwaysOn можно включить все Скайп для сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="23b0f-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="23b0f-251">На странице **Указание реплик** перейдите на вкладку **Реплики**. Затем нажмите кнопку **Добавить реплики** и установите соединение со всеми другими экземплярами SQL, присоединенными в качестве узлов отказоустойчивого кластера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="23b0f-p136">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="23b0f-254">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="23b0f-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="23b0f-p137">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="23b0f-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="23b0f-257">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="23b0f-p138">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="23b0f-p139">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="23b0f-262">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="23b0f-263">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="23b0f-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="23b0f-264">Создайте новое хранилище, указав прослушиватель AG, а субъекта старой зеркальной как основной узел AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="23b0f-265">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="23b0f-265">Open Topology Builder.</span></span> <span data-ttu-id="23b0f-266">В данной топологии разверните узел **Общие компоненты**, щелкните **Хранилища SQL Server** правой кнопкой мыши и выберите **Создать хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="23b0f-267">На странице **Определение нового хранилища SQL Server** сначала установите флажок **Параметры высокого уровня доступности**, затем убедитесь в том, что в раскрывающемся списке отображаются группы доступности SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="23b0f-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="23b0f-268">В поле **Полное доменное имя прослушивателя группы доступности SQL Server** введите полное доменное имя прослушивателя, созданного в процессе создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="23b0f-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="23b0f-269">В поле **Полное доменное имя SQL Server** введите полное доменное имя основного узла AG и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="23b0f-270">Это должен быть субъекта старый зеркала для этого хранилища.</span><span class="sxs-lookup"><span data-stu-id="23b0f-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="23b0f-271">Сопоставьте новый AG с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="23b0f-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="23b0f-272">В построителе топологий щелкните правой кнопкой мыши пул для связи с AG и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="23b0f-273">В разделе **связи**в поле **Хранилища SQL Server** выберите AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="23b0f-274">Выберите ту же группу для других баз данных в пуле, который необходимо переместить в AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="23b0f-275">Если вы уверены, что все необходимые базы данных находятся в AG, нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="23b0f-p143">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="23b0f-279">Выполните некоторые окончательный действия, чтобы убедиться, что имена входа SQL на каждой реплики в группе обеспечения доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="23b0f-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="23b0f-280">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="23b0f-281">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="23b0f-282">Щелкните правой кнопкой мыши хранилище SQL новые AG и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="23b0f-283">В нижней части страницы в поле **Полное доменное имя SQL Server** измените значение на полное доменное имя прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="23b0f-p145">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="23b0f-288">Откройте SQL Server Management Studio и перейдите к AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="23b0f-289">Сбое на вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="23b0f-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="23b0f-290">Откройте Скайп для Business Server Командная консоль и введите следующий командлет, чтобы создать входы SQL на этом реплики:</span><span class="sxs-lookup"><span data-stu-id="23b0f-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="23b0f-291">Повторите два предыдущих шага (переключаются в группе, чтобы вторичная реплика, а затем использовать `Install-CsDatabase -Update`) для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="23b0f-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="23b0f-292">Развертывание всегда на группы обеспечения доступности для существующего пула, который не используется зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="23b0f-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="23b0f-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="23b0f-293"></span></span>

> [!NOTE]
> <span data-ttu-id="23b0f-294">Если пула, в котором обновлении AG размещается центральное хранилище управления для вашей организации, необходимо сначала переместить CMS в другой пул перед обновлением этого пула.</span><span class="sxs-lookup"><span data-stu-id="23b0f-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="23b0f-295">Используйте командлет Move-CsManagementServer для перемещения в пул.</span><span class="sxs-lookup"><span data-stu-id="23b0f-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="23b0f-296">Если у вас другой пул в вашей организации, можно временно развертывание сервера Standard Edition и переместить CMS на этом сервере перед обновлением до AG пуле.</span><span class="sxs-lookup"><span data-stu-id="23b0f-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="23b0f-297">Установите средство отказоустойчивости кластера на всех серверах базы данных, которые будут частью AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="23b0f-298">На каждом сервере выполните указанные ниже</span><span class="sxs-lookup"><span data-stu-id="23b0f-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="23b0f-299">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="23b0f-p149">Нажимайте кнопку **Далее** до появления поля **Выбор компонентов**. В этом окне установите флажок **Отказоустойчивость кластеров**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="23b0f-302">В поле **Добавить компоненты, необходимые для Отказоустойчивость кластеров?** щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="23b0f-303">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="23b0f-304">Проверьте конфигурацию кластеров.</span><span class="sxs-lookup"><span data-stu-id="23b0f-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="23b0f-305">В диспетчере серверов щелкните меню **Сервис**, затем пункт **Диспетчер отказоустойчивости кластеров**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="23b0f-306">В разделе **Действия** с правой стороны экрана щелкните **Проверить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="23b0f-307">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-308">Выберите серверы для добавления к кластеру, затем щелкните **Выполнить все тесты**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="23b0f-309">В окне "**Сводка** " Проверьте все ошибки, которые мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="23b0f-309">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="23b0f-310">Затем нажмите кнопку **Готово** для завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="23b0f-310">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="23b0f-p151">В этом поле мастера может отображаться несколько предупреждений, особенно в том случае, если не используется общее хранилище. Пользоваться общим хранилищем не обязательно. Однако при наличии сообщений с заголовком **Ошибка** перед продолжением необходимо устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="23b0f-314">Создайте отказоустойчивый кластер Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="23b0f-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="23b0f-315">В мастере **Средства управления отказоустойчивыми кластерами** щелкните **Средства управления отказоустойчивыми кластерами**, затем выберите **Создание кластера**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="23b0f-316">На странице **Прежде чем приступить к работе** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-p152">Добавьте имя и IP -адрес кластера. После проверки параметров нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-319">На странице "Подтверждение" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-320">После создания кластера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="23b0f-p153">Рекомендуется настроить параметры кворума кластера для работы с файловым ресурсом-свидетелем. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="23b0f-323">Щелкните имя кластера правой кнопкой мыши и выберите **More Actions**, затем **Настройка параметров кворума кластера**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="23b0f-324">На странице **Выбор параметра конфигурации кворума** щелкните **Выбрать свидетель кворума**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="23b0f-325">На странице **Выбор свидетеля кворума** щелкните **Настроить файловый ресурс-свидетель**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="23b0f-326">На странице **Настройка файлового ресурса-свидетеля** введите путь к требуемому общему файловому ресурсу, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-327">На странице **Подтверждение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="23b0f-328">На каждом сервере в кластере включите AG диспетчер конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="23b0f-p154">Откройте диспетчер конфигурации SQL Server. В дереве с левой стороны экрана щелкните **Службы SQL Server**, затем дважды щелкните службу SQL Server. </span><span class="sxs-lookup"><span data-stu-id="23b0f-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="23b0f-p155">В окне **Свойства** перейдите на вкладку **Высокий уровень доступности AlwaysOn**. Установите флажок **Включить группы доступности AlwaysOn**. По запросу перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="23b0f-333">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="23b0f-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="23b0f-334">Откройте Microsoft SQL Server Management Studio и установите соединение с экземпляром SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b0f-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="23b0f-335">В обозревателе объектов разверните папку **Всегда высокой доступности** .</span><span class="sxs-lookup"><span data-stu-id="23b0f-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="23b0f-336">Щелкните папку **Группы доступности** правой кнопкой мыши и выберите **Мастер создания групп доступности**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="23b0f-337">В случае появления страницы **Введение** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-338">На странице **Указание имени группы доступности** введите имя группы доступности, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-339">На странице Выбор базы данных выберите базы данных, которые необходимо включить в AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="23b0f-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-340">Then click **Next**.</span></span>
    
    <span data-ttu-id="23b0f-341">Не включайте **ReportServer**, **ReportServerTempDB**или Persistent Chat баз данных в AG, как они не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="23b0f-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="23b0f-342">Можно добавить другие Скайп для баз данных Business Server AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="23b0f-343">На странице **Определение реплик** перейдите на вкладку **реплики** . Затем нажмите кнопку **Добавить реплики** и подключитесь к других экземпляров SQL, состав как узлы WSFC.</span><span class="sxs-lookup"><span data-stu-id="23b0f-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="23b0f-p159">Для каждого экземпляра выберите режимы **Автоматический переход на другой ресурс** и **Синхронная фиксация**. Не выбирайте режим **Вторичная реплика для чтения**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="23b0f-346">Перейдите на вкладку **Конечные точки** и убедитесь в том, что для параметра **Номер порта** задано значение 5022.</span><span class="sxs-lookup"><span data-stu-id="23b0f-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="23b0f-p160">Откройте вкладку **Прослушиватель** и выберите параметр **Создать прослушиватель группы доступности**. Введите имя прослушивателя и установите в поле **Порт** значение 1433 (этот параметр не поддерживает другие порты).</span><span class="sxs-lookup"><span data-stu-id="23b0f-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="23b0f-349">Нажмите кнопку **Добавить** и введите предпочтительный виртуальный IP‑адрес в поле **IPv4-адрес**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="23b0f-p161">На странице **Выбор начальной синхронизации данных** выберите "Полное" и укажите доступную для реплик папку, запись в которую разрешена учетной записи службы SQL, используемой обеими репликами. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="23b0f-p162">Этот общий файловый ресурс будет временно использоваться при инициализации баз данных. При работе с большими базами данных рекомендуется инициализировать их вручную, если полосы пропускания сети недостаточно для передачи резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="23b0f-354">На странице "Проверка" убедитесь в успешном выполнении всех операций проверки, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="23b0f-355">На странице **Сводка** проверьте значения всех параметров и нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="23b0f-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="23b0f-356">Создайте новое хранилище, определяющее AG прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="23b0f-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="23b0f-357">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="23b0f-357">Open Topology Builder.</span></span> <span data-ttu-id="23b0f-358">В данной топологии разверните узел **Общие компоненты**, щелкните **Хранилища SQL Server** правой кнопкой мыши и выберите **Создать хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="23b0f-359">На странице **Определение нового хранилища SQL Server** сначала установите флажок **Параметры высокого уровня доступности**, затем убедитесь в том, что в раскрывающемся списке отображаются группы доступности SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="23b0f-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="23b0f-360">В поле **Полное доменное имя прослушивателя группы доступности SQL Server** введите полное доменное имя прослушивателя, созданного в процессе создания группы доступности.</span><span class="sxs-lookup"><span data-stu-id="23b0f-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="23b0f-361">В поле **Полное доменное имя SQL Server** введите полное доменное имя основного узла AG и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="23b0f-362">Сопоставьте новый всегда на группы обеспечения доступности с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="23b0f-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="23b0f-363">В построителе топологий щелкните правой кнопкой мыши пул для связи с AG и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="23b0f-364">В разделе **связи**в поле **Хранилища SQL Server** выберите AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="23b0f-365">Выберите ту же группу для других баз данных в пуле, который необходимо переместить в AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="23b0f-366">Если вы уверены, что все необходимые базы данных находятся в AG, нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="23b0f-p165">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="23b0f-370">Выполните некоторые окончательный действия, чтобы убедиться, что имена входа SQL на каждой реплики в AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="23b0f-371">Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="23b0f-372">Разверните Скайп для сервера, топологии и **Хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="23b0f-373">Щелкните правой кнопкой мыши хранилище SQL новые AG и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="23b0f-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="23b0f-374">В нижней части страницы в поле **Полное доменное имя SQL Server** измените значение на полное доменное имя прослушивателя AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="23b0f-p167">Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**. Репликация новой топологии занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="23b0f-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="23b0f-379">Откройте SQL Server Management Studio и перейдите к AG.</span><span class="sxs-lookup"><span data-stu-id="23b0f-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="23b0f-380">Сбое на вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="23b0f-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="23b0f-381">Откройте Скайп для Business Server Командная консоль и введите следующий командлет, чтобы создать входы SQL на этом реплики:</span><span class="sxs-lookup"><span data-stu-id="23b0f-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="23b0f-382">Повторите два предыдущих шага (переключаются в группе, чтобы вторичная реплика, а затем использовать `Install-CsDatabase -Update`) для каждой реплики в группе.</span><span class="sxs-lookup"><span data-stu-id="23b0f-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>