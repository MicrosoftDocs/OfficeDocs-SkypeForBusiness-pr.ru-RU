---
title: Развертывание пилотного пула Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c97ea5304309aaf635ac284e792a73634c5ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="30bee-102">Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30bee-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30bee-103">_**Последнее изменение темы:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="30bee-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="30bee-104">Один из первых действий, необходимых для перехода на Lync Server 2013, заключается в развертывании пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="30bee-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="30bee-105">Пилотный пул заключается в тестировании сосуществования Lync Server 2013 с развертыванием Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30bee-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="30bee-106">Сосуществование — это временное состояние, которое продолжается до тех пор, пока все пользователи и пулы не будут перемещены в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30bee-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="30bee-107">При развертывании пилотной версии пула используется мастер определения нового интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="30bee-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="30bee-108">Необходимо развернуть те же функции и рабочие нагрузки в пилотном пуле Lync Server 2013, который находится в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30bee-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="30bee-109">Если вы развернули сервер архивации, сервер мониторинга или System Center Operations Manager для архивации или мониторинга среды Office Communications Server 2007 R2 и хотите продолжить архивацию или мониторинг во время миграции, необходимо также развертывайте эти функции в пилотной среде.</span><span class="sxs-lookup"><span data-stu-id="30bee-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="30bee-110">Версия, развернутая для архивации или мониторинга среды Office Communications Server 2007 R2, не будет захватывать данные в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30bee-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30bee-111">В описании следующей процедуры рассматриваются компоненты и настройки, которые следует использовать в рамках общего процесса развертывания пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="30bee-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="30bee-112">В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="30bee-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="30bee-113">Подробное описание действий можно найти в руководстве по развертыванию <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="30bee-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="30bee-114">**Развертывание пилотного пула Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="30bee-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="30bee-115">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="30bee-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="30bee-116">Откройте построитель топологий и выберите пункт "Создать новую топологию".</span><span class="sxs-lookup"><span data-stu-id="30bee-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="30bee-117">Укажите основной домен SIP.</span><span class="sxs-lookup"><span data-stu-id="30bee-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="30bee-118">![Создание новой топологии, определение основной страницы домена](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Создание новой топологии, определение основной страницы домена")</span><span class="sxs-lookup"><span data-stu-id="30bee-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="30bee-119">Выполните все шаги мастера, пока не откроется мастер **Определение нового интерфейсного пула**.</span><span class="sxs-lookup"><span data-stu-id="30bee-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="30bee-120">Нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="30bee-120">Click Next.</span></span>

5.  <span data-ttu-id="30bee-121">Укажите полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="30bee-121">Enter the pool FQDN.</span></span> <span data-ttu-id="30bee-122">При определении пилотного пула можно развернуть пул переднего плана Enterprise Edition или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="30bee-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="30bee-123">В Lync Server 2013 не требуется, чтобы функции пилотного пула точно были развернуты в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="30bee-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="30bee-124">Полное доменное имя пула или сервера, определенное для пилотного пула, должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="30bee-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="30bee-125">Он не может быть сопоставлен с именем развернутого пула Office Communications Server 2007 R2 или других серверов, развернутых в данный момент.</span><span class="sxs-lookup"><span data-stu-id="30bee-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="30bee-126">![Страница определения полного доменного имени пула переднего плана](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Страница определения полного доменного имени пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="30bee-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="30bee-127">Определите компьютер, который будет добавлен в пул.</span><span class="sxs-lookup"><span data-stu-id="30bee-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="30bee-128">![Диалоговое окно определения нового пула переднего плана](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Диалоговое окно определения нового пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="30bee-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="30bee-129">На странице **Выбор компонентов** установите флажки рядом с теми компонентами, которые вы хотите добавить в этот интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="30bee-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="30bee-130">Например, при развертывании только компонентом службы обмена мгновенными сообщениями и службы присутствия, необходимо установить флажок "Конференц-связь", чтобы разрешить многосторонний обмен мгновенными сообщениями, но не нужно устанавливать флажки "Конференц-связь с телефонным подключением", "Корпоративная голосовая связь" или "Контроль допуска звонков", поскольку они представляют собой компоненты голосовой конференц-связи, видеоконференций и конференц-связи для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="30bee-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="30bee-131">Дополнительную информацию по выбору компонентов можно узнать в статье [Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="30bee-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="30bee-132">![Страница выбора компонентов пула переднего плана](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Страница выбора компонентов пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="30bee-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="30bee-133">На странице **Выбор размещенных ролей сервера** мы рекомендуем совместно использовать сервер-посредник в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30bee-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="30bee-134">При объединении устаревшей топологии с Lync Server 2013 необходимо сначала разместить сервер-посредник Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30bee-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="30bee-135">После объединения топологий и настройки сервера-посредника Lync Server 2013 вы можете решить, следует ли оставить совмещенный сервер-посредник или изменить его на изолированный сервер при перемещении роли сервера-посредника в Lync Server 2013 позже в развертывании. процесс.</span><span class="sxs-lookup"><span data-stu-id="30bee-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="30bee-136">![Внешний интерфейсный пул страница выбора размещенных ролей сервера](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Внешний интерфейсный пул страница выбора размещенных ролей сервера")</span><span class="sxs-lookup"><span data-stu-id="30bee-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="30bee-p109">В процесс развертывания пилотной версии пула на странице **Связать роли сервера с этим интерфейсным пулом** не следует выбирать параметр **Разрешить использование пограничного пула мультимедиа-компонентом этого интерфейсного пула**. Эта функция включается и активируется на более позднем этапе миграции. Пока не устанавливайте этот флажок.</span><span class="sxs-lookup"><span data-stu-id="30bee-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="30bee-140">![Сопоставление ролей сервера со страницей интерфейсного пула](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Сопоставление ролей сервера со страницей интерфейсного пула")</span><span class="sxs-lookup"><span data-stu-id="30bee-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="30bee-141">На странице **Выбор сервера Office Web Apps** выберите **Создать** и укажите полное доменное имя сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="30bee-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="30bee-142">![Определение новых свойств полного доменного имени сервера Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Определение новых свойств полного доменного имени сервера Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="30bee-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="30bee-143">На странице **Определение хранилища SQL Server для архивации** выберите экземпляр SQL Server, созданный ранее для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30bee-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="30bee-144">![Страница определения хранилища сервера архивации SQL Server](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Страница определения хранилища сервера архивации SQL Server")</span><span class="sxs-lookup"><span data-stu-id="30bee-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="30bee-145">На странице **Определение хранилища SQL** Server для мониторинга выберите экземпляр SQL Server, созданный ранее для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30bee-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="30bee-146">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="30bee-146">Click **Finish**.</span></span>

13. <span data-ttu-id="30bee-p111">На верхнем узле построителя топологий щелкните правой кнопкой мыши **Lync Server** и нажмите **Изменить свойства.** Выберите **Простые URL-адреса**.</span><span class="sxs-lookup"><span data-stu-id="30bee-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="30bee-149">Обновите **URL-адрес для административного доступа**.</span><span class="sxs-lookup"><span data-stu-id="30bee-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="30bee-150">![Страница "изменить свойства", "простые URL-адреса"](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Страница "изменить свойства", "простые URL-адреса"")</span><span class="sxs-lookup"><span data-stu-id="30bee-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="30bee-151">Дополнительные сведения о простых URL-адресах можно найти в статье [изменение или Настройка простых URL-адресов в Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="30bee-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="30bee-152">В разделе **Изменить свойства** нажмите **Сервер централизованного управления**.</span><span class="sxs-lookup"><span data-stu-id="30bee-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="30bee-153">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30bee-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="30bee-154">![Изменение свойств, страница сервера центрального управления](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Изменение свойств, страница сервера центрального управления")</span><span class="sxs-lookup"><span data-stu-id="30bee-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="30bee-155">Нажмите "ОК", чтобы закрыть страницу **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="30bee-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="30bee-156">В меню **Действие** выберите действие **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="30bee-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="30bee-157">По завершении процесса публикации нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="30bee-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="30bee-158">Возврат к мастеру развертывания Lync Server 2013 нажмите **установить или обновить систему Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="30bee-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="30bee-159">![Мастер развертывания Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Мастер развертывания Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="30bee-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="30bee-160">Чтобы установить локальную копию хранилища конфигурации и запустить необходимые службы, ознакомьтесь со статьей [Настройка серверов переднего плана и интерфейсных пулов для Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="30bee-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

