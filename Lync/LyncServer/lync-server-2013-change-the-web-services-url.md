---
title: 'Lync Server 2013: изменение URL-адреса веб – служб'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="724db-102">Изменение URL-адреса веб – служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="724db-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="724db-103">_**Тема последнего изменения:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="724db-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="724db-104">При настройке пулов интерфейсов и серверов Standard Edition можно настроить полное доменное имя внешней веб-фермы (FQDN) и соответствующие порты.</span><span class="sxs-lookup"><span data-stu-id="724db-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="724db-105">Если вы не настроили этот URL-адрес при выполнении мастера развертывания Lync Server, необходимо настроить эти параметры вручную.</span><span class="sxs-lookup"><span data-stu-id="724db-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="724db-106">Администраторам обычно не требуется изменять эти параметры, так как это рекомендованные и стандартные порты.</span><span class="sxs-lookup"><span data-stu-id="724db-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="724db-107">На следующем снимке экрана предпринята Настройка сервера Standard Edition, поэтому параметр override FQDN отключен.</span><span class="sxs-lookup"><span data-stu-id="724db-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="724db-108">Этот параметр доступен при настройке сервера Enterprise Edition в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="724db-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="724db-109">![Изменение параметров пула веб-служб] (images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Изменение параметров пула веб-служб")</span><span class="sxs-lookup"><span data-stu-id="724db-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="724db-110">Настройка веб-служб</span><span class="sxs-lookup"><span data-stu-id="724db-110">To configure web services</span></span>

1.  <span data-ttu-id="724db-111">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="724db-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="724db-112">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="724db-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="724db-113">В построителе топологии в дереве консоли в разделе **Стандартные серверы переднего плана**, пулы предварительных интерфейсов **Enterprise Edition**и **Пулы каталогов**выберите имя пула.</span><span class="sxs-lookup"><span data-stu-id="724db-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="724db-114">Щелкните имя правой кнопкой мыши, выберите команду **изменить свойства**, а затем — **веб-службы**.</span><span class="sxs-lookup"><span data-stu-id="724db-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="724db-115">Добавьте или измените свое **доменное имя внешней веб-службы**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="724db-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="724db-116">Если у вас более одного пула переднего плана или сервера переднего плана, полное доменное имя внешней веб-службы должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="724db-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="724db-117">Например, если вы определяете полное доменное имя внешней веб-службы на сервере переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="724db-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="724db-118">Если вы также разворачиваете директоров, то полные доменные имена внешних веб-служб, определенные для любого режиссера или режиссера, должны быть уникальными из любого другого директора или пула и внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="724db-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="724db-119">Проверьте, правильно ли настроены прослушивание и опубликованные порты для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="724db-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="724db-120">Повторите эти действия для всех серверов стандартных выпусков, пулов интерфейсов и пулов каталогов в среде.</span><span class="sxs-lookup"><span data-stu-id="724db-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="724db-121">В дереве консоли щелкните **Lync Server 2013**, а затем в области **действия** выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="724db-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="724db-122">При настройке портов для прослушивания и публикации необходимо учитывать несколько требований:</span><span class="sxs-lookup"><span data-stu-id="724db-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="724db-123">Показанные порты прослушивания — это порты, настроенные для сервера IIS на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="724db-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="724db-124">Внутренние и внешние порты для прослушивания должны различаться для IIS.</span><span class="sxs-lookup"><span data-stu-id="724db-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="724db-125">Для внешних портов прослушивания они обычно одинаковы, поскольку один из них представляет балансировщик аппаратной подсистемы балансировки нагрузки внутреннего веб-трафика, а другой — обратный прокси-сервер для внешнего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="724db-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="724db-126">Внутренние веб-службы можно переопределить в пуле переднего плана, режиссере или в пуле и задать свое собственное ДОМЕНное имя.</span><span class="sxs-lookup"><span data-stu-id="724db-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="724db-127">Если вы решите переопределить внутренние веб-службы с помощью самоопределенного полного доменного имени, каждое полное доменное имя должно быть уникальным из любого другого пула переднего плана, режиссера или директора пула.</span><span class="sxs-lookup"><span data-stu-id="724db-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="724db-128">Опубликованные порты должны быть настроены на обратном прокси-сервере или в подсистеме балансировки нагрузки аппаратного обеспечения, как и прослушивающий порт.</span><span class="sxs-lookup"><span data-stu-id="724db-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="724db-129">Для пула переднего плана (не показан в примере) полное доменное имя пула SIP должно отличаться от FQDN для внутренних веб-служб, так как веб-трафик проходит через балансировщик нагрузки на оборудование, а внутренний трафик пула SIP передается через подсистему балансировки нагрузки DNS .</span><span class="sxs-lookup"><span data-stu-id="724db-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="724db-130">Это требование должно быть удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="724db-130">This requirement must be met.</span></span>

  - <span data-ttu-id="724db-131">Развертывание Lync Server Standard Edition не требует и не разрешает переопределение внутренних доменных имен веб-служб, так как этот сервер не может поддерживать балансировку нагрузки.</span><span class="sxs-lookup"><span data-stu-id="724db-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="724db-132">Если у вас есть аппаратная подсистема балансировки нагрузки в вашей среде, используемая для внутреннего SIP и веб-трафика, построитель топологии не может сделать это отличие.</span><span class="sxs-lookup"><span data-stu-id="724db-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="724db-133">Доменные имена веб-служб должны быть легко различы друг с другом. Это помогает обеспечить клиентам точки перенаправления URL-адресов, направленные на соответствующий сервер.</span><span class="sxs-lookup"><span data-stu-id="724db-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="724db-134">Например, если у вас есть два полных доменных имен, вы можете наименовать один meeting.contoso.com и другой conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="724db-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="724db-135">Вы можете столкнуться с проблемами перенаправления, если у вас есть полные доменные имена с более близкими именами, такими как meet1.contoso.com и meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="724db-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="724db-136">Внешние веб-службы работают вместе с обратной прокси-сервером в демилитаризованной зоне.</span><span class="sxs-lookup"><span data-stu-id="724db-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="724db-137">Она предоставляет клиентам внешний доступ с помощью этих веб-служб.</span><span class="sxs-lookup"><span data-stu-id="724db-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="724db-138">Полные доменные имена, настроенные здесь, отправляются клиентам при входе в систему, а также используются для обратного подключения HTTPS к обратному прокси-серверу при удаленном подключении.</span><span class="sxs-lookup"><span data-stu-id="724db-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="724db-139">Прокси-сервер перенаправляет внешнее полное доменное имя веб-службы на внутренний балансировщик аппаратной балансировки нагрузки или непосредственно в пул.</span><span class="sxs-lookup"><span data-stu-id="724db-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="724db-140">Обратный прокси-сервер должен разрешить полное доменное имя внешней веб-службы в IP-адрес внутреннего веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="724db-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="724db-141">Внешние веб-службы ФДКН должны быть разрешимыми в общедоступном Интернете.</span><span class="sxs-lookup"><span data-stu-id="724db-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="724db-142">Если внутренний сервер является сервером стандартных выпусков, внутреннее ДОМЕНное имя — это FQDN сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="724db-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="724db-143">Если внутренний сервер является пулом переднего плана, полное доменное имя — это виртуальный IP-адрес подсистемы балансировки нагрузки, который обеспечивает балансировку нагрузки для внутренних серверов веб-ферм.</span><span class="sxs-lookup"><span data-stu-id="724db-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="724db-144">Аппаратная подсистема балансировки нагрузки требуется в пуле переднего плана с более чем одним сервером выпуска Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="724db-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="724db-145">Подсистема балансировки нагрузки не требуется для сервера Standard Edition или односерверного переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="724db-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

