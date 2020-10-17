---
title: Развертывание пилотного пула Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9489db1fef9b836749fe4f381e717a4d406f5938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502976"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="fe5ce-102">Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe5ce-102">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe5ce-103">_**Последнее изменение темы:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="fe5ce-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="fe5ce-104">Один из первых действий, необходимых для перехода на Lync Server 2013, заключается в развертывании пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="fe5ce-105">Пилотный пул заключается в тестировании сосуществования Lync Server 2013 с развертыванием Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="fe5ce-106">Сосуществование — это временное состояние, которое продолжается до тех пор, пока все пользователи и пулы не будут перемещены в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="fe5ce-107">При развертывании пилотной версии пула используется мастер определения нового интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="fe5ce-108">Необходимо развернуть те же функции и рабочие нагрузки в пилотном пуле Lync Server 2013, который вы используете в пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="fe5ce-109">Если вы развернули сервер архивации, сервер мониторинга или System Center Operations Manager для архивации и мониторинга среды Lync Server 2010 и хотите продолжить архивацию или мониторинг во время миграции, необходимо также развернуть эти функции в пилотной среде.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="fe5ce-110">Версия, развернутая для архивации и мониторинга среды Lync Server 2010, не захватывает данные в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe5ce-111">В описании следующей процедуры рассматриваются компоненты и настройки, которые следует использовать в рамках общего процесса развертывания пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="fe5ce-112">В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="fe5ce-113">Подробное описание действий можно найти в руководстве по развертыванию <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="fe5ce-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="fe5ce-114">**Развертывание пилотного пула Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="fe5ce-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="fe5ce-115">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="fe5ce-116">Разверните дерево до тех пор, пока не будет достигнуто **интерфейсных пулов** **Lync Server 2013** Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="fe5ce-117">Щелкните правой кнопкой мыши узел **Пулы переднего плана Enterprise Edition** и выберите команду **Создать пул переднего плана**.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="fe5ce-118">![Подменю выбора пула серверов построителя топологий](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Подменю выбора пула серверов построителя топологий")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="fe5ce-119">Укажите полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-119">Enter the pool FQDN.</span></span> <span data-ttu-id="fe5ce-120">При определении пилотного пула можно развернуть пул переднего плана Enterprise Edition или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="fe5ce-121">В Lync Server 2013 не требуется, чтобы функции пилотного пула точно были развернуты в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fe5ce-122">Полное доменное имя пула или сервера, определенное для пилотного пула, должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="fe5ce-123">Он не может быть сопоставлен с именем развернутого пула Lync Server 2010 или других серверов, развернутых в данный момент.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="fe5ce-124">![Страница определения полного доменного имени мастера создания пула переднего плана](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Страница определения полного доменного имени мастера создания пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="fe5ce-125">На странице **Выбор компонентов** установите флажки рядом с теми компонентами, которые вы хотите добавить в этот интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="fe5ce-126">Например, при развертывании только компонентом службы обмена мгновенными сообщениями и службы присутствия, необходимо установить флажок "Конференц-связь", чтобы разрешить многосторонний обмен мгновенными сообщениями, но не нужно устанавливать флажки "Конференц-связь с телефонным подключением", "Корпоративная голосовая связь" или "Контроль допуска звонков", поскольку они представляют собой компоненты голосовой конференц-связи, видеоконференций и конференц-связи для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="fe5ce-127">Дополнительную информацию по выбору компонентов можно узнать в статье [Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="fe5ce-128">![Страница выбора компонентов пула переднего плана](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Страница выбора компонентов пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="fe5ce-129">На странице **Выбор размещенных ролей сервера** мы рекомендуем совместно использовать сервер-посредник в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="fe5ce-130">При объединении устаревшей топологии с Lync Server 2013 необходимо сначала разместить сервер-посредник по Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="fe5ce-131">После объединения топологий и настройки сервера-посредника Lync Server 2013 вы можете решить, следует ли оставить совмещенный сервер-посредник или изменить его на изолированный сервер при перемещении роли сервера-посредника в Lync Server 2013 позже в процессе развертывания.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="fe5ce-132">![Внешний интерфейсный пул страница выбора размещенных ролей сервера](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Внешний интерфейсный пул страница выбора размещенных ролей сервера")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="fe5ce-p108">В процесс развертывания пилотной версии пула на странице **Связать роли сервера с этим интерфейсным пулом** не следует выбирать параметр **Разрешить использование пограничного пула мультимедиа-компонентом этого интерфейсного пула**. Эта функция включается и активируется на более позднем этапе миграции. Пока не устанавливайте этот флажок.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-p108">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="fe5ce-136">![Сопоставление ролей сервера со страницей интерфейсного пула](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Сопоставление ролей сервера со страницей интерфейсного пула")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="fe5ce-137">На странице **Выбор сервера Office Web Apps** выберите **Создать** и укажите полное доменное имя сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="fe5ce-138">![Определение новых свойств полного доменного имени сервера Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Определение новых свойств полного доменного имени сервера Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="fe5ce-139">На странице **Определение хранилища SQL Server для архивации** при определении хранилища SQL Server для архивации и мониторинга Lync Server выберите экземпляр SQL Server, созданный ранее для lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="fe5ce-140">![Страница определения хранилища сервера архивации SQL Server](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Страница определения хранилища сервера архивации SQL Server")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="fe5ce-141">Чтобы опубликовать топологию, щелкните правой кнопкой мыши узел **Lync Server** и выберите команду **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="fe5ce-142">![Построитель топологий, отображающий настроенную топологию](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Построитель топологий, отображающий настроенную топологию")</span><span class="sxs-lookup"><span data-stu-id="fe5ce-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="fe5ce-143">По завершении процесса публикации нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="fe5ce-144">Чтобы установить локальную копию хранилища конфигурации и запустить необходимые службы, ознакомьтесь со статьей [Настройка серверов переднего плана и интерфейсных пулов для Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fe5ce-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

