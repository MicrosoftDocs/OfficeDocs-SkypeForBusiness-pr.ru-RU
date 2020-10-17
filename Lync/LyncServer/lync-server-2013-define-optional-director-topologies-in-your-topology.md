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
ms.openlocfilehash: e53512d2d3c0bd99c4d5b23d20f21859ec974415
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504576"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="da3e0-102">Определение дополнительных топологий директоров в топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da3e0-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da3e0-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="da3e0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="da3e0-104">Менеджеры Lync Server 2013 могут быть серверами с одним экземпляром или могут устанавливаться как пул с балансировкой нагрузки нескольких директоров для обеспечения высокой доступности и емкости.</span><span class="sxs-lookup"><span data-stu-id="da3e0-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="da3e0-105">Поддерживается аппаратная балансировка нагрузки и балансировка нагрузки службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="da3e0-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="da3e0-106">В этом разделе объясняется, как настроить балансировку нагрузки на DNS для пулов директоров.</span><span class="sxs-lookup"><span data-stu-id="da3e0-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="da3e0-107">Чтобы успешно публиковать, включать или отключать топологию при добавлении или удалении серверной роли, необходимо войти от имени пользователя, являющегося членом групп **RTCUniversalServerAdmins** и **Domain Admins**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="da3e0-108">Можно также делегировать соответствующие административные права и разрешения для добавления серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="da3e0-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="da3e0-109">Для получения дополнительных сведений обратитесь к разделу [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию сервера Standard Edition или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="da3e0-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="da3e0-110">Для других изменений конфигурации достаточно членства в группе **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="da3e0-111">В этом разделе описываются действия по определению и публикации топологии для двух топологий директоров:</span><span class="sxs-lookup"><span data-stu-id="da3e0-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="da3e0-112">по определению Директора (единственный экземпляр);</span><span class="sxs-lookup"><span data-stu-id="da3e0-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="da3e0-113">по определению Директора (пул из нескольких Директоров).</span><span class="sxs-lookup"><span data-stu-id="da3e0-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="da3e0-114">Определение Директора (единственный экземпляр)</span><span class="sxs-lookup"><span data-stu-id="da3e0-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="da3e0-115">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="da3e0-116">На странице приветствия нажмите **Download Topology from Existing Deployment (Загрузить топологию из существующего развертывания)**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="da3e0-117">В диалоговом окне **Save Topology As (Сохранить топологию как)** введите имя и расположение для локальной копии существующей топологии, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="da3e0-118">Разверните узел, в который планируется добавить Директор, щелкните правой кнопкой мыши пункт **Director pools (Пулы Директоров)**, а затем выберите команду **New Director Pool (Создать пул Директоров)**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="da3e0-119">В диалоговом окне **Define the Director pool FQDN (Определение полного доменного имени пула Директоров)** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="da3e0-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="da3e0-120">В поле **Pool FQDN (Полное доменное имя пула)** введите полное доменное имя для пула Директоров.</span><span class="sxs-lookup"><span data-stu-id="da3e0-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="da3e0-121">Выберите **Single computer pool (Пул с одним компьютером)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="da3e0-122">В диалоговом окне **Define the file share (Определение общей папки)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="da3e0-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="da3e0-123">Чтобы использовать существующую общую папку, выберите **Use a previously defined file share (Использовать существующую общую папку)**, выберите общую папку из списка и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="da3e0-124">Чтобы создать новую общую папку, нажмите **Define a new file share (Задать новую общую папку)**, введите полное доменное имя для расположения этой папки в поле **File Server FQDN (Полное доменное имя файлового сервера)**, введите имя общей папки в поле **File Share (Общая папка)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="da3e0-125">Общая папка, которая была указана или создана в этом действии, должна уже существовать, или ее необходимо создать до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="da3e0-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="da3e0-126">Назначенная Директору общая папка в действительности не используется, поэтому можно назначить общую папку из любого пула в организации.</span><span class="sxs-lookup"><span data-stu-id="da3e0-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="da3e0-127">В диалоговом окне **Specify the Web Services URL (Указание URL-адреса веб-служб)** в поле **External Base URL (Внешний базовый URL-адрес)** укажите полное доменное имя для Директоров и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="da3e0-128">Это имя должно быть разрешаемо из Интернет-серверов доменных имен и указывать на общедоступный IP адрес обратного прокси-сервера, который прослушивает запросы HTTP/HTTPS на этот URL-адрес и представляет их в виртуальном каталоге внешних веб-служб в этом Директоре.</span><span class="sxs-lookup"><span data-stu-id="da3e0-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="da3e0-129">Если у вас больше одного интерфейсного пула или сервера переднего плана, полное доменное имя внешних веб-служб должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="da3e0-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="da3e0-130">Например, если вы определили полное доменное имя внешних веб-служб для сервера переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="da3e0-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="da3e0-131">Если вы также развертываете директоров, то полное доменное имя внешних веб-служб, определенное для любого директора или пула директоров, должно быть уникальным в любом другом директоре или пуле, а также в любом пуле переднего плана или сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="da3e0-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="da3e0-132">Если решено переопределить внутренние веб-службы с самоопределенным полным доменным именем, каждое полное доменное имя должно быть уникальным в любом другом интерфейсном пуле, директоре или в пуле директоров.</span><span class="sxs-lookup"><span data-stu-id="da3e0-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="da3e0-133">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="da3e0-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="da3e0-134">Определение Директора (пул из нескольких Директоров)</span><span class="sxs-lookup"><span data-stu-id="da3e0-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="da3e0-135">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="da3e0-136">На странице приветствия нажмите **Download Topology from Existing Deployment (Загрузить топологию из существующего развертывания)**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="da3e0-137">В диалоговом окне **Save Topology As (Сохранить топологию как)** введите имя и расположение для локальной копии существующей топологии, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="da3e0-138">Разверните узел, в который планируется добавить Директор, щелкните правой кнопкой мыши пункт **Director pools (Пулы Директоров)**, а затем выберите команду **New Director Pool (Создать пул Директоров)**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="da3e0-139">В диалоговом окне **Define the Director pool FQDN (Определение полного доменного имени пула Директоров)** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="da3e0-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="da3e0-140">В поле **Pool FQDN (Полное доменное имя пула)** введите полное доменное имя для пула Директоров.</span><span class="sxs-lookup"><span data-stu-id="da3e0-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="da3e0-141">Выберите **Multiple computer pool (Пул с несколькими компьютерами)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="da3e0-142">В диалоговом окне **Define the computers in this pool (Указание компьютеров в пуле)** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="da3e0-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="da3e0-143">Укажите полное доменное имя компьютера, который будет первым членом пула, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="da3e0-p104">Повторите предыдущее действие для каждого компьютера, который требуется добавить. Закончив, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="da3e0-146">В диалоговом окне **Define the file share (Определение общей папки)** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="da3e0-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="da3e0-147">Чтобы использовать существующую общую папку, выберите **Use a previously defined file share (Использовать существующую общую папку)**, выберите общую папку из списка и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="da3e0-148">Чтобы создать новую общую папку, нажмите **Define a new file share (Задать новую общую папку)**, введите полное доменное имя для расположения этой папки в поле **File Server FQDN (Полное доменное имя файлового сервера)**, введите имя общей папки в поле **File Share (Общая папка)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="da3e0-149">Общая папка, которая была указана или создана в этом действии, должна уже существовать, или ее необходимо создать до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="da3e0-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="da3e0-150">Назначенная Директору общая папка в действительности не используется, поэтому можно назначить общую папку из любого пула в организации.</span><span class="sxs-lookup"><span data-stu-id="da3e0-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="da3e0-151">В диалоговом окне **Specify the Web Services URL (Указание URL-адреса веб-служб)** в поле **External Base URL (Внешний базовый URL-адрес)** укажите полное доменное имя для Директоров и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="da3e0-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="da3e0-152">Это имя должно быть разрешаемо из Интернет-серверов доменных имен и указывать на общедоступный IP адрес обратного прокси-сервера, который прослушивает запросы HTTP/HTTPS, отправленные на этот URL-адрес, и представляет их в виртуальном каталоге внешних веб-служб в этом Директоре.</span><span class="sxs-lookup"><span data-stu-id="da3e0-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="da3e0-153">Если у вас больше одного интерфейсного пула или сервера переднего плана, полное доменное имя внешних веб-служб должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="da3e0-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="da3e0-154">Например, если вы определили полное доменное имя внешних веб-служб для сервера переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="da3e0-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="da3e0-155">Если вы также развертываете директоров, то полное доменное имя внешних веб-служб, определенное для любого директора или пула директоров, должно быть уникальным в любом другом директоре или пуле, а также в любом пуле переднего плана или сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="da3e0-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="da3e0-156">Если решено переопределить внутренние веб-службы с самоопределенным полным доменным именем, каждое полное доменное имя должно быть уникальным в любом другом интерфейсном пуле, директоре или в пуле директоров.</span><span class="sxs-lookup"><span data-stu-id="da3e0-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="da3e0-157">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="da3e0-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

