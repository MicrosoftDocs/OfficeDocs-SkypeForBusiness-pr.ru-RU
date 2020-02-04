---
title: Развертывание пула Lync Server 2013 Pilot
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
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="3538c-102">Развертывание пула Lync Server 2013 Pilot</span><span class="sxs-lookup"><span data-stu-id="3538c-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3538c-103">_**Тема последнего изменения:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="3538c-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="3538c-104">Один из первых шагов, необходимых для перехода на Lync Server 2013, — это развертывание пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="3538c-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="3538c-105">Пилотный пул — это проверка сосуществования Lync Server 2013 с развертыванием Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3538c-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="3538c-106">Сосуществование — это временное состояние, которое продолжается до тех пор, пока вы не переместит всех пользователей и пулы на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3538c-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="3538c-107">При развертывании пилотного пула вы используете мастер определения нового пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3538c-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="3538c-108">Вы должны развернуть те же функции и рабочие нагрузки в пуле Lync Server 2013 Pilot, который находится в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3538c-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="3538c-109">Если вы развернули сервер архивации, сервер мониторинга или System Center Operations Manager для архивации или наблюдения в среде Office Communications Server 2007 R2 и хотите продолжить архивирование и мониторинг во время миграции, необходимо выполнить указанные выше действия. также развертывайте эти функции в среде пилотной программы.</span><span class="sxs-lookup"><span data-stu-id="3538c-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="3538c-110">Версия, развернутая для архивации или наблюдения за вашей средой Office Communications Server 2007 R2, не захватывает данные в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3538c-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3538c-111">В приведенной ниже процедуре описаны возможности и параметры, которые следует рассмотреть в рамках всего процесса развертывания пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="3538c-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="3538c-112">В этом разделе выделены только ключевые моменты, которые следует принимать во время развертывания пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="3538c-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="3538c-113">Подробные инструкции можно найти в руководстве <A href="lync-server-2013-deploying-lync-server.md">развертывание Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="3538c-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="3538c-114">**Развертывание пула Lync Server 2013 Pilot**</span><span class="sxs-lookup"><span data-stu-id="3538c-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="3538c-115">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3538c-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3538c-116">Откройте построитель топологии и выберите Создание новой топологии.</span><span class="sxs-lookup"><span data-stu-id="3538c-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="3538c-117">Введите основной домен SIP.</span><span class="sxs-lookup"><span data-stu-id="3538c-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="3538c-118">![Создание новой топологии, определение основной страницы домена](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Создание новой топологии, определение основной страницы домена")</span><span class="sxs-lookup"><span data-stu-id="3538c-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="3538c-119">Продолжайте работу с мастером, пока не дойдете до мастера **Определение нового пула переднего плана** .</span><span class="sxs-lookup"><span data-stu-id="3538c-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="3538c-120">Нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="3538c-120">Click Next.</span></span>

5.  <span data-ttu-id="3538c-121">Введите полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="3538c-121">Enter the pool FQDN.</span></span> <span data-ttu-id="3538c-122">При определении пилотного пула вы можете выбрать развертывание пула переднего плана Enterprise Edition или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3538c-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="3538c-123">Для Lync Server 2013 не требуется, чтобы функции пилотного пула соответствовали развернутым в пуле старого.</span><span class="sxs-lookup"><span data-stu-id="3538c-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3538c-124">Полное доменное имя (FQDN) для пула, которое вы определяете для пилотного пула, должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="3538c-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="3538c-125">Оно не может совпадать с именем развернутого пула Office Communications Server 2007 R2 или других серверов, развернутых в данный момент.</span><span class="sxs-lookup"><span data-stu-id="3538c-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="3538c-126">![Страница определения полного доменного имени пула переднего плана](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Страница определения полного доменного имени пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="3538c-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="3538c-127">Определите компьютер, который будет добавляться в пул.</span><span class="sxs-lookup"><span data-stu-id="3538c-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="3538c-128">![Диалоговое окно определения нового пула интерфейса пользователя](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Диалоговое окно определения нового пула интерфейса пользователя")</span><span class="sxs-lookup"><span data-stu-id="3538c-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="3538c-129">На странице " **Выбор компонентов** " установите флажки для нужных функций в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3538c-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="3538c-130">Например, если вы разворачиваете только возможности обмена мгновенными сообщениями и сведения о присутствии, установите флажок Конференц-связь, чтобы разрешить многофакторный обмен мгновенными сообщениями, но не устанавливайте флажки конференции для коммутируемого подключения, корпоративной голосовой связи и управления допуском звонков. так как они представляют собой голосовую, видеосвязь и возможности совместной конференции.</span><span class="sxs-lookup"><span data-stu-id="3538c-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="3538c-131">Дополнительные сведения о выборе функций можно найти в разделе [Определение и Настройка внешнего пула и сервера Standard Edition в Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3538c-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="3538c-132">![Страница выбора компонентов в пуле интерфейса пользователя](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Страница выбора компонентов в пуле интерфейса пользователя")</span><span class="sxs-lookup"><span data-stu-id="3538c-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="3538c-133">На странице **Выбор размещенных ролей сервера** мы рекомендуем вам разделять сервер-посредник в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3538c-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="3538c-134">При объединении устаревшей топологии с Lync Server 2013 необходимо сначала выписать сервер Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3538c-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="3538c-135">После слияния топологий и настройки сервера-исправления Lync Server 2013 вы можете решить, нужно ли сохранять Объединенный сервер или изменить его на отдельный сервер при перемещении роли сервера-посредника на Lync Server 2013 позже в развертывании процесса.</span><span class="sxs-lookup"><span data-stu-id="3538c-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="3538c-136">![Пул переднего плана выберите страницу "размещенные роли сервера"](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Пул переднего плана выберите страницу "размещенные роли сервера"")</span><span class="sxs-lookup"><span data-stu-id="3538c-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="3538c-137">**В процессе** развертывания пилотного пула не выбирайте **пул краев, который будет использоваться компонентом мультимедиа для этого параметра пула переднего плана** .</span><span class="sxs-lookup"><span data-stu-id="3538c-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="3538c-138">Это функция, которую вы сможете включить и подключить к Интернету на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="3538c-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="3538c-139">Не Запусти этот параметр, пока не будет снят флажок.</span><span class="sxs-lookup"><span data-stu-id="3538c-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="3538c-140">![Связывание ролей сервера со страницей пула переднего плана](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Связывание ролей сервера со страницей пула переднего плана")</span><span class="sxs-lookup"><span data-stu-id="3538c-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="3538c-141">На странице **выберите сервер Office Web Apps** нажмите кнопку **создать**и укажите полное доменное имя сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="3538c-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="3538c-142">![Определение новых свойств полного доменного имени сервера Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Определение новых свойств полного доменного имени сервера Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="3538c-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="3538c-143">На странице **Определение хранилища SQL Server для архивации** выберите экземпляр SQL Server, созданный ранее для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3538c-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="3538c-144">![Страница "определение архива SQL Server — хранилище"](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Страница "определение архива SQL Server — хранилище"")</span><span class="sxs-lookup"><span data-stu-id="3538c-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="3538c-145">На странице **Определение хранилища SQL** Server в хранилище выберите экземпляр SQL Server, созданный ранее для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3538c-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="3538c-146">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3538c-146">Click **Finish**.</span></span>

13. <span data-ttu-id="3538c-147">На верхнем узле построителя топологии щелкните правой кнопкой мыши на **Lync Server** и выберите пункт **изменить свойства.**</span><span class="sxs-lookup"><span data-stu-id="3538c-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="3538c-148">Щелкните **простые URL-адреса**.</span><span class="sxs-lookup"><span data-stu-id="3538c-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="3538c-149">Обновите **URL-адрес для административного доступа**.</span><span class="sxs-lookup"><span data-stu-id="3538c-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="3538c-150">![Изменение свойств, простая страница URL-адресов](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Изменение свойств, простая страница URL-адресов")</span><span class="sxs-lookup"><span data-stu-id="3538c-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="3538c-151">Дополнительные сведения об простых URL-адресах можно найти в разделе [изменение или Настройка простых URL-адресов в Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3538c-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="3538c-152">В **диалоговом окне Изменение свойств**выберите пункт **центральный сервер управления**.</span><span class="sxs-lookup"><span data-stu-id="3538c-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="3538c-153">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3538c-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="3538c-154">![Изменение свойств, страница сервера центрального управления](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Изменение свойств, страница сервера центрального управления")</span><span class="sxs-lookup"><span data-stu-id="3538c-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="3538c-155">Нажмите кнопку ОК, чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="3538c-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="3538c-156">В меню **действий** выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="3538c-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="3538c-157">После завершения процесса публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3538c-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="3538c-158">Вернувшись к мастеру развертывания Lync Server 2013, нажмите **установить или обновить систему Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3538c-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="3538c-159">![Мастер развертывания Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Мастер развертывания Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="3538c-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="3538c-160">Чтобы установить локальную копию хранилища конфигурации и запустить необходимые службы, ознакомьтесь со сведениями [о настройке внешних серверов и пулов интерфейсов для Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3538c-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

