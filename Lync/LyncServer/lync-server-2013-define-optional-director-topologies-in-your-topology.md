---
title: 'Lync Server 2013: определение дополнительных топологий директоров в топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f3c78730e8c866e3838f22a1267a57bb3d237b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="e361c-102">Определение дополнительных топологий директоров в топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e361c-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e361c-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e361c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e361c-104">Менеджеры Lync Server 2013 могут быть серверами с одним экземпляром или могут быть установлены в качестве пула балансировки нагрузки нескольких директоров для более высокой доступности и емкости.</span><span class="sxs-lookup"><span data-stu-id="e361c-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="e361c-105">Поддерживается балансировка нагрузки аппаратного обеспечения и служба доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="e361c-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="e361c-106">В этой статье объясняется, как настроить балансировку нагрузки DNS для пулов режиссеров.</span><span class="sxs-lookup"><span data-stu-id="e361c-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="e361c-107">Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, вы должны войти в систему как пользователь, который является членом группы администраторов **рткуниверсалсерверадминс** и **domain** .</span><span class="sxs-lookup"><span data-stu-id="e361c-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="e361c-108">Вы также можете делегировать надлежащие права администратора и разрешения для добавления ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="e361c-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="e361c-109">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию сервера Standard Edition Server или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="e361c-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="e361c-110">Для других изменений конфигурации требуется только членство в группе **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="e361c-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="e361c-111">В этой статье описаны действия, которые необходимо выполнить для определения и публикации топологии двух топологий режиссеров.</span><span class="sxs-lookup"><span data-stu-id="e361c-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="e361c-112">Определение режиссера (один экземпляр)</span><span class="sxs-lookup"><span data-stu-id="e361c-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="e361c-113">Определение режиссера (несколько режиссеров)</span><span class="sxs-lookup"><span data-stu-id="e361c-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="e361c-114">Определение режиссера (один экземпляр)</span><span class="sxs-lookup"><span data-stu-id="e361c-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="e361c-115">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e361c-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e361c-116">На странице приветствия нажмите кнопку **загрузить топологию из существующего развертывания**.</span><span class="sxs-lookup"><span data-stu-id="e361c-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="e361c-117">В диалоговом окне **Сохранение топологии как** введите имя и расположение локальной копии существующей топологии, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e361c-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="e361c-118">Разверните сайт, на который вы хотите добавить режиссера, щелкните правой кнопкой мыши пункт **Пулы**и выберите команду **создать пул каталогов**.</span><span class="sxs-lookup"><span data-stu-id="e361c-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="e361c-119">В диалоговом окне **Определение полного доменного имени режиссера** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e361c-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e361c-120">В поле **полное доменное имя пула**введите полное доменное имя для пула каталогов.</span><span class="sxs-lookup"><span data-stu-id="e361c-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="e361c-121">Выберите **один пул компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e361c-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e361c-122">В диалоговом окне **Определение общей папке** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e361c-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="e361c-123">Чтобы использовать существующую общую файловую группу, выберите **использовать**файловый общий доступ, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e361c-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="e361c-124">Чтобы создать новый файловый ресурс, нажмите кнопку **определить новый файловый ресурс**, введите полное доменное имя для расположения общего файлового **файла в поле** **Общий**доступ к файлам и нажмите кнопку **Next (далее**).</span><span class="sxs-lookup"><span data-stu-id="e361c-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e361c-125">Общие файлы, указанные или созданные в этом шаге, должны существовать или создаваться перед публикацией топологии.</span><span class="sxs-lookup"><span data-stu-id="e361c-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="e361c-126">Файловый общий доступ, назначенный режиссеру, не используется, поэтому вы можете назначить общую файловую группу для любого пула в Организации.</span><span class="sxs-lookup"><span data-stu-id="e361c-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="e361c-127">В диалоговом окне **Определение URL-адреса веб – службы** в поле **Внешний базовый URL-адрес**введите полное доменное имя директора и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e361c-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e361c-128">Имя должно быть разрешено с DNS-серверов Интернета и указывать на общедоступный IP-адрес обратного прокси-сервера, который прослушивает запросы HTTP/HTTPS на этот URL-адрес и попытается использовать их в виртуальном каталоге внешних веб-служб этого директора.</span><span class="sxs-lookup"><span data-stu-id="e361c-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e361c-129">Если у вас более одного пула переднего плана или сервера переднего плана, полное доменное имя внешней веб-службы должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="e361c-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e361c-130">Например, если вы определяете полное доменное имя внешней веб-службы на сервере переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e361c-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="e361c-131">Если вы также разворачиваете директоров, то полные доменные имена внешних веб-служб, определенные для любого режиссера или режиссера, должны быть уникальными из любого другого директора или пула и внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="e361c-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="e361c-132">Если вы решите переопределить внутренние веб-службы с помощью самоопределенного полного доменного имени, каждое полное доменное имя должно быть уникальным из любого другого пула переднего плана, режиссера или директора пула.</span><span class="sxs-lookup"><span data-stu-id="e361c-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="e361c-133">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="e361c-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="e361c-134">Определение режиссера (несколько режиссеров)</span><span class="sxs-lookup"><span data-stu-id="e361c-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="e361c-135">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e361c-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e361c-136">На странице приветствия нажмите кнопку **загрузить топологию из существующего развертывания**.</span><span class="sxs-lookup"><span data-stu-id="e361c-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="e361c-137">В диалоговом окне **Сохранение топологии как** введите имя и расположение локальной копии существующей топологии, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e361c-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="e361c-138">Разверните сайт, на который вы хотите добавить режиссера, щелкните правой кнопкой мыши пункт **Пулы**и выберите команду **создать пул каталогов**.</span><span class="sxs-lookup"><span data-stu-id="e361c-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="e361c-139">В диалоговом окне **Определение полного доменного имени режиссера** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e361c-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e361c-140">В поле **полное доменное имя пула**введите полное доменное имя для пула каталогов.</span><span class="sxs-lookup"><span data-stu-id="e361c-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="e361c-141">Выберите пункт **несколько групп компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e361c-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e361c-142">В диалоговом окне **Определение компьютеров в этом пуле** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e361c-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e361c-143">Укажите полное доменное имя компьютера первого участника пула и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e361c-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="e361c-144">Повторите предыдущий шаг для каждого компьютера, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="e361c-144">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="e361c-145">Когда все будет готово, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e361c-145">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="e361c-146">В диалоговом окне **Определение общей папке** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e361c-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="e361c-147">Чтобы использовать существующую общую файловую группу, выберите **использовать**файловый общий доступ, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e361c-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="e361c-148">Чтобы создать новый файловый ресурс, нажмите кнопку **определить новый файловый ресурс**, введите полное доменное имя для расположения общего файлового **файла в поле** **Общий**доступ к файлам и нажмите кнопку **Next (далее**).</span><span class="sxs-lookup"><span data-stu-id="e361c-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e361c-149">Общие файлы, указанные или созданные в этом шаге, должны существовать или создаваться перед публикацией топологии.</span><span class="sxs-lookup"><span data-stu-id="e361c-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="e361c-150">Файловый общий доступ, назначенный режиссеру, не используется, поэтому вы можете назначить общую файловую группу для любого пула в Организации.</span><span class="sxs-lookup"><span data-stu-id="e361c-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="e361c-151">В диалоговом окне **Определение URL-адреса веб – службы** в поле **Внешний базовый URL-адрес**введите полное доменное имя директора и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e361c-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e361c-152">Это имя должно быть разрешено с DNS-серверов Интернета и указывать на общедоступный IP-адрес обратного прокси-сервера, который прослушивает запросы HTTP/HTTPS, отправленные на этот URL-адрес, и прокси-сервером во внешнем виртуальном каталоге служб.</span><span class="sxs-lookup"><span data-stu-id="e361c-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e361c-153">Если у вас более одного пула переднего плана или сервера переднего плана, полное доменное имя внешней веб-службы должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="e361c-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e361c-154">Например, если вы определяете полное доменное имя внешней веб-службы на сервере переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e361c-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="e361c-155">Если вы также разворачиваете директоров, то полные доменные имена внешних веб-служб, определенные для любого режиссера или режиссера, должны быть уникальными из любого другого директора или пула и внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="e361c-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="e361c-156">Если вы решите переопределить внутренние веб-службы с помощью самоопределенного полного доменного имени, каждое полное доменное имя должно быть уникальным из любого другого пула переднего плана, режиссера или директора пула.</span><span class="sxs-lookup"><span data-stu-id="e361c-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="e361c-157">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="e361c-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

