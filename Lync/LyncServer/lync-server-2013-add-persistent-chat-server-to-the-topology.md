---
title: 'Lync Server 2013: Добавление сервера сохраняемого чата к топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e34643c2a9f838d9a8c66cdfc04698d813db01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="720d4-102">Добавление сервера сохраняемого чата к топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="720d4-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="720d4-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="720d4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="720d4-104">Перед настройкой развертывания для поддержки сервера сохраняемого чата необходимо внедрить в топологию сервер Lync Server 2013, поддержку сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="720d4-105">Сведения в этом разделе описывают, как использовать построитель топологий для добавления поддержки сервера сохраняемого чата в существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="720d4-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="720d4-106">Добавление сервера сохраняемого чата в топологию</span><span class="sxs-lookup"><span data-stu-id="720d4-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="720d4-107">Выполните указанные ниже действия, чтобы установить один пул серверов сохраняемого чата без конфигурации аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="720d4-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="720d4-108">Для настройки растянутого пула серверов сохраняемого чата для обеспечения высокой доступности и аварийного восстановления [в разделе Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="720d4-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="720d4-109">Чтобы развернуть несколько пулов серверов сохраняемого чата, повторите один и тот же процесс для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="720d4-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="720d4-110">На компьютере с Lync Server 2013 или на котором установлены средства администрирования Lync Server Войдите в систему с учетной записью, которая является членом локальной группы "Пользователи" (или учетной записью с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="720d4-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="720d4-111">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но опубликовать топологию, которая необходима для установки сервера Lync Server 2013. необходимо использовать учетную запись, которая является членом группы <STRONG>администраторов домена</STRONG> и группы <STRONG>RTCUniversalServerAdmins</STRONG> , и иметь разрешения на полный доступ (то есть чтение, запись и изменение) в хранилище файлов, которое планируется использовать для хранилища файлов сервера сохраняемого чата (то есть построителю топологий может настраивать требуемые DACL). или учетная запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="720d4-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="720d4-112">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="720d4-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="720d4-113">В дереве консоли перейдите к узлу **Пулы сохраняемого чата** и разверните его, чтобы выбрать пул серверов сохраняемого чата, или щелкните правой кнопкой мыши узел и выберите **создать пул сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="720d4-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="720d4-114">Необходимо определить полное доменное имя пула и указать, будет ли пул содержать один сервер или несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="720d4-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="720d4-115">Можно выбрать **Пул из нескольких компьютеров** или **Пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="720d4-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="720d4-116">Выберите первый вариант, если вы планируете использовать несколько серверов переднего плана сервера сохраняемого чата в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="720d4-117">Сделайте этот выбор сейчас или позднее, потому что после создания пула с одним компьютером вы не сможете добавить в него дополнительные серверы.</span><span class="sxs-lookup"><span data-stu-id="720d4-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="720d4-118">Если выбран пул из нескольких компьютеров, введите имена отдельных серверов переднего плана сервера сохраняемого чата, входящих в пул.</span><span class="sxs-lookup"><span data-stu-id="720d4-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="720d4-119">Если роль сервера сохраняемого чата устанавливается на сервере Lync Server 2013&nbsp;Standard Edition, полное доменное имя должно сопоставлено с полным доменным именем сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="720d4-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="720d4-120">Определение простого **отображаемого имени** для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="720d4-121">Отображаемое имя может использоваться настраиваемыми клиентами, особенно при наличии нескольких пулов серверов сохраняемого чата, чтобы отличать комнаты.</span><span class="sxs-lookup"><span data-stu-id="720d4-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="720d4-122">Определите порт, используемый сервером сохраняемого чата для взаимодействия с серверами переднего плана Lync Server.</span><span class="sxs-lookup"><span data-stu-id="720d4-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="720d4-123">Порт по умолчанию — 5041.</span><span class="sxs-lookup"><span data-stu-id="720d4-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="720d4-124">Если организация должна соблюдать требования, установите флажок **Включить соблюдение требований**.</span><span class="sxs-lookup"><span data-stu-id="720d4-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="720d4-125">Если этот параметр выбран, служба соответствия сервера сохраняемого чата устанавливается на том же компьютере, что и сервер переднего плана сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="720d4-126">Вам будет предложено выбрать сервер внутреннего сервера SQL Server для обеспечения соответствия требованиям сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="720d4-127">Назначьте сходство сайтов для пула сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="720d4-128">Установите флажок **использовать этот пул по умолчанию для \<сайта\> sitename** или **Используйте этот пул по умолчанию для всех сайтов** , чтобы назначить этот пул серверов сохраняемого чата как пул по умолчанию для текущего сайта или для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="720d4-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="720d4-129">Когда клиент Lync 2013 используется для создания комнат и управления ими, пул по умолчанию, связанный с сайтом пользователя, используется для создания и управления комнатами, чтобы он мог маршрутизировать операции по созданию и управлению комнатами для этого пула.</span><span class="sxs-lookup"><span data-stu-id="720d4-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="720d4-130">Это применимо только в том случае, если развернуто несколько пулов серверов сохраняемого чата и вы хотите использовать возможности создания и управления комнатами сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="720d4-131">Функции создания и управления комнатами можно настраивать с помощью пакета SDK сервера сохраняемого чата (SDK).</span><span class="sxs-lookup"><span data-stu-id="720d4-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="720d4-132">Сведения о настройке баз данных резервного копирования SQL Server для аварийного восстановления приведены в статье <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="720d4-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="720d4-133">Определите **хранилище SQL для внутреннего сервера сохраняемого чата (где хранится содержимое комнаты чата)** , выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="720d4-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="720d4-134">Чтобы использовать существующую базу данных SQL Server, в раскрывающемся списке щелкните имя базы данных SQL Server, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="720d4-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="720d4-135">Чтобы указать новую базу данных SQL Server, нажмите кнопку **создать**, а затем в окне **Определение нового хранилища SQL**выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="720d4-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="720d4-136">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера SQL Server, на котором требуется создать новую базу данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="720d4-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="720d4-137">Либо выберите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр, выберите **Именованный экземпляр** и укажите нужный.</span><span class="sxs-lookup"><span data-stu-id="720d4-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="720d4-138">Определите базу данных соответствия SQL Server, если вы включили соответствие.</span><span class="sxs-lookup"><span data-stu-id="720d4-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="720d4-139">Сведения о том, как настроить зеркальные отображения SQL Server для обеспечения высокой доступности базы данных сервера сохраняемого чата и базы данных соответствия сервера сохраняемого чата, приведены в статье <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="720d4-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="720d4-140">Определите хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="720d4-140">Define the file store.</span></span> <span data-ttu-id="720d4-141">Хранилище файлов — это папка, в которой хранится копия любого файла, загруженного в репозиторий файлов, например файлового вложения, отправленного в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="720d4-142">В случае топологии сервера сохраняемого чата с несколькими серверами это должен быть UNC-путь; для односерверной топологии сервера сохраняемого чата это может быть локальный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="720d4-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="720d4-143">Чтобы использовать существующее хранилище файлов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="720d4-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="720d4-144">В поле **Полное доменное имя файлового сервера** укажите полное доменное имя компьютера, на котором следует создать новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="720d4-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="720d4-145">В поле **Файловый ресурс** укажите хранилище файлов, которое следует использовать.</span><span class="sxs-lookup"><span data-stu-id="720d4-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="720d4-146">Вы можете определить хранилище файлов в построителе топологий, прежде чем создавать хранилище файлов, но необходимо создать хранилище файлов в определенном месте, которое необходимо определить перед публикацией топологии.</span><span class="sxs-lookup"><span data-stu-id="720d4-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="720d4-147">Выберите пул серверов переднего плана, который будет использоваться в качестве следующего прыжка для этого пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720d4-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="720d4-148">Это пул серверов переднего плана, который будет выполнять маршрутизацию запросов сервера сохраняемого чата к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="720d4-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="720d4-149">Чтобы сохранить конфигурацию, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="720d4-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="720d4-150">Пул серверов сохраняемого чата отображается в построителе топологий, сопровождаемом вашими параметрами пула.</span><span class="sxs-lookup"><span data-stu-id="720d4-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="720d4-151">Теперь опубликуйте обновленную топологию, на которой вы хотите получить доступ к серверу сохраняемого чата, в документации по развертыванию [опубликована обновленная топология в Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) .</span><span class="sxs-lookup"><span data-stu-id="720d4-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="720d4-152">Если вы уже открыли построитель топологий, вы можете перейти к шагу 3 при <A href="lync-server-2013-publish-the-updated-topology.md">публикации обновленной топологии в Lync Server 2013</A> , чтобы начать публикацию обновленной топологии.</span><span class="sxs-lookup"><span data-stu-id="720d4-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

