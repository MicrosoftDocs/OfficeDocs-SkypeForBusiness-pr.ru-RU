---
title: 'Lync Server 2013: добавление сервера сохраняемого чата к топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="dd301-102">Добавление сервера сохраняемого чата к топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd301-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd301-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="dd301-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="dd301-104">Прежде чем вы сможете настроить развертывание для поддержки постоянного сервера чата, необходимо включить в топологию сервер Lync Server 2013, поддержку сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="dd301-105">В этой статье описано, как с помощью Topology Builder добавить в существующую топологию поддержку сервера для работы с сохраняемым чат.</span><span class="sxs-lookup"><span data-stu-id="dd301-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="dd301-106">Добавление сервера сохраняемого чата в топологию</span><span class="sxs-lookup"><span data-stu-id="dd301-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="dd301-107">Выполните описанные ниже действия, чтобы установить один пул серверов для постоянного чата без конфигурации аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="dd301-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="dd301-108">Для настройки подтянутого пула серверов для обеспечения высокой доступности и аварийного восстановления ознакомьтесь с [Разстройкой сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dd301-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="dd301-109">Чтобы развернуть несколько пулов серверов для постоянного чата, повторите один и тот же процесс для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="dd301-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="dd301-110">На компьютере с Lync Server 2013 или на котором установлены средства администрирования Lync Server, войдите в систему с помощью учетной записи, которая является членом локальной группы "Пользователи" (или учетной записи с эквивалентными правами пользователей).</span><span class="sxs-lookup"><span data-stu-id="dd301-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd301-111">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы пользователей, но для публикации топологии, необходимой для установки сервера Lync Server 2013, необходимо использовать учетную запись, которая входит в группу <STRONG>администраторов домена</STRONG> и <STRONG>рткуниверсалс Ерверадминс</STRONG> , и у него есть разрешения на полный доступ (то есть чтение, запись и изменение) в хранилище файлов, которое вы собираетесь использовать для хранения файлов на сервере сохраняемого чата (это значит, что построитель топологии может настроить нужные DACL) или учетную запись. с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="dd301-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="dd301-112">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="dd301-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="dd301-113">В дереве консоли перейдите к узлу **группы постоянного чата** и разверните его, чтобы выбрать пул серверов для сохраняемого чата, или щелкните правой кнопкой мыши и выберите **новый пул сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="dd301-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="dd301-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span><span class="sxs-lookup"><span data-stu-id="dd301-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="dd301-115">Можно выбрать **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="dd301-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="dd301-116">Выберите первый из них, если вы планируете использовать более одного серверного переднего плана в пуле сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="dd301-117">Сделайте этот выбор сейчас или позднее, потому что после создания пула с одним компьютером вы не сможете добавить в него дополнительные серверы.</span><span class="sxs-lookup"><span data-stu-id="dd301-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="dd301-118">Если вы выбрали группу компьютеров с несколькими компьютерами, введите имена отдельных серверных серверов с постоянными разчатами, которые представляют собой пул.</span><span class="sxs-lookup"><span data-stu-id="dd301-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dd301-119">Если роль сервера "сохраняемый чат" устанавливается на сервере Lync Server 2013&nbsp;Standard Edition, полное доменное имя должно совпадать с полным доменным именем сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dd301-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="dd301-120">Определение простого **отображаемого имени** для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="dd301-121">Отображаемое имя можно использовать в настраиваемых клиентах, особенно в том случае, если существует несколько пулов серверов для общения, чтобы отличать комнаты.</span><span class="sxs-lookup"><span data-stu-id="dd301-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="dd301-122">Определите порт, используемый сервером сохраняемого чата для связи с внешними серверами Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd301-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="dd301-123">Порт по умолчанию: 5041.</span><span class="sxs-lookup"><span data-stu-id="dd301-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="dd301-124">Если организация должна соблюдать требования, установите флажок **Включить соответствие**.</span><span class="sxs-lookup"><span data-stu-id="dd301-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="dd301-125">При выборе этого варианта служба соответствия требованиям сервера будет установлена на том же компьютере, что и сервер, на котором установлен сервер постоянного чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="dd301-126">Вам будет предложено выбрать сервер SQL Server для обеспечения соответствия требованиям к серверу для постоянной версии Chat.</span><span class="sxs-lookup"><span data-stu-id="dd301-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="dd301-127">Назначение схожести сайтов для пула сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="dd301-128">Установите флажок **использовать этот пул как по умолчанию \<для\> сайта sitename** или **Используйте этот пул по умолчанию для всех сайтов** , чтобы назначить этот пул сервера сохраняемого чата в качестве пула по умолчанию для текущего сайта или для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="dd301-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="dd301-129">Когда клиент Lync 2013 используется для создания комнат и управления ими, пул по умолчанию, связанный с сайтом пользователя, используется для создания и управления комнатой, чтобы он мог перенаправлять операции создания и управления комнатам в этот пул.</span><span class="sxs-lookup"><span data-stu-id="dd301-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="dd301-130">Это применимо только в том случае, если у вас развернут несколько пулов серверов для чата и вы хотите использовать возможности создания и управления комнат для постоянного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dd301-131">Вы можете настроить возможности создания и управления комнат с помощью пакета SDK для серверного программного обеспечения для постоянного чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="dd301-132">Сведения о том, как настроить резервные копии баз данных SQL Server для аварийного восстановления, приведены в разделе <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dd301-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="dd301-133">Определите **хранилище SQL для сервера сохраняемого чата (в котором хранится содержимое комнаты чата)** , выполнив одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="dd301-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="dd301-134">Чтобы использовать существующую базу данных SQL Server, в раскрывающемся списке выберите имя базы данных SQL Server, которую вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="dd301-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="dd301-135">Чтобы указать новую базу данных SQL Server, нажмите кнопку **создать**, а затем в разделе **Определение нового хранилища SQL**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dd301-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="dd301-136">В **доменном имени SQL Server**укажите полное доменное имя сервера SQL Server, на котором вы хотите создать новую базу данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd301-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="dd301-137">Выберите **Экземпляр по умолчанию**, чтобы использовать экземпляр по умолчанию, или **Именованный экземпляр**, чтобы указать другой экземпляр, и укажите экземпляр, который требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="dd301-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="dd301-138">Укажите базу данных соответствия SQL Server, если вы включили соответствие.</span><span class="sxs-lookup"><span data-stu-id="dd301-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dd301-139">Сведения о том, как настроить зеркальные отображения SQL Server для обеспечения высокой доступности серверной базы данных для работы с сохраняемым чат и базы данных соответствия требованиям сервера для постоянной связи: <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Настройка сервера сохраняемого чата для восстановления с высокой доступностью и аварийным восстановлением в Lync Сервер 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dd301-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="dd301-140">Определите хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="dd301-140">Define the file store.</span></span> <span data-ttu-id="dd301-141">Хранилище файлов — это папка, в которой хранится копия любого файла, загруженного в репозиторий файлов, например файлового вложения, отправленного в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="dd301-142">В случае односерверной топологии сервера сохраняемого чата, это должен быть путь UNC (Universal Naming Convention). и для односерверной топологии сервера единого чата это может быть путь к локальному файлу.</span><span class="sxs-lookup"><span data-stu-id="dd301-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="dd301-143">Чтобы использовать существующее хранилище файлов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dd301-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="dd301-144">В разделе **полное доменное имя файлового сервера**укажите полное доменное имя хранилища файлов, в котором вы хотите создать новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="dd301-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="dd301-145">В поле **Файловый ресурс** укажите хранилище файлов, которое следует использовать.</span><span class="sxs-lookup"><span data-stu-id="dd301-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dd301-146">Вы можете определить хранилище файлов в построителе топологии до создания хранилища файлов, но необходимо создать хранилище файлов в определенном месте, которое вы определили перед публикацией топологии.</span><span class="sxs-lookup"><span data-stu-id="dd301-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="dd301-147">Выберите пул серверов переднего плана, который будет использоваться в качестве следующего прыжка для этого пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="dd301-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="dd301-148">Это пул серверного переднего плана, который сможет перенаправлять запросы сервера для постоянного чата в этот пул.</span><span class="sxs-lookup"><span data-stu-id="dd301-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="dd301-149">Чтобы сохранить конфигурацию, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="dd301-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="dd301-150">Пул серверов сохраняемого чата появляется в построителе топологии, сопровождаемом вашими конкретными параметрами пула.</span><span class="sxs-lookup"><span data-stu-id="dd301-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="dd301-151">Чтобы теперь опубликовать обновленную топологию, в которой вы хотите вести сохраняемый сервер чата, ознакомьтесь со сведениями [Публикация обновленной топологии в Lync server 2013](lync-server-2013-publish-the-updated-topology.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dd301-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd301-152">Если вы уже открыли построитель топологии, вы можете перейти к шагу 3 в <A href="lync-server-2013-publish-the-updated-topology.md">публикации обновленной топологии в Lync Server 2013</A> для начала публикации обновленной топологии.</span><span class="sxs-lookup"><span data-stu-id="dd301-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

