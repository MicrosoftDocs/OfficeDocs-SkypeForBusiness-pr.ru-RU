---
title: 'Lync Server 2013: Настройка DNS для балансировки нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 797a788649edab99852cfec9f83423075b14f742
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="57714-102">Настройка DNS для балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57714-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57714-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="57714-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="57714-104">Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="57714-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="57714-105">Балансировка нагрузки службы доменных имен (DNS) обеспечивает балансировку сетевого трафика, уникального для Lync Server 2013, например трафика SIP и трафика мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="57714-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="57714-106">Функция балансировки нагрузки DNS поддерживается для интерфейсных пулов, пограничных пулов, пулов директоров и автономных пулов-посредников.</span><span class="sxs-lookup"><span data-stu-id="57714-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="57714-107">В пуле, настроенном для использования балансировки нагрузки на DNS, должно быть задано два полных доменных имени (FQDN), которые используются системой балансировки нагрузки на DNS (например, pool1.contoso.com) и которые разрешаются в физические IP-адреса серверов в пуле. и другое полное доменное имя для веб-служб пула (например, web1.contoso.net), которое разрешается в виртуальный IP-адрес пула.</span><span class="sxs-lookup"><span data-stu-id="57714-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="57714-108">Для получения дополнительных сведений о балансировке нагрузки на DNS обратитесь к разделу [Балансировка нагрузки на DNS в Lync Server 2013](lync-server-2013-dns-load-balancing.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="57714-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57714-109">Для HTTPS-трафика с клиента на сервер все еще требуется аппаратная балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="57714-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="57714-110">Прежде чем использовать балансировку нагрузки DNS, следует выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="57714-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="57714-111">Переопределите полное доменное имя пула внутренних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="57714-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="57714-112">Если решено переопределить внутренние веб-службы с самоопределенным полным доменным именем, каждое полное доменное имя должно быть уникальным в любом другом интерфейсном пуле, директоре или в пуле директоров.</span><span class="sxs-lookup"><span data-stu-id="57714-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="57714-113">Создать записи узлов A DNS, чтобы разрешать полное доменное имя пула в IP-адреса всех серверов в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="57714-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="57714-114">Включить случайный выбор IP-адресов, а для Windows Server DNS — включить циклическое обслуживание.</span><span class="sxs-lookup"><span data-stu-id="57714-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57714-115">Циклическое обслуживание должно быть включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57714-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="57714-116">Переопределение полного доменного имени внутренних веб-служб</span><span class="sxs-lookup"><span data-stu-id="57714-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="57714-117">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="57714-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="57714-118">В дереве консоли разверните узел интерфейсных пулов Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="57714-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="57714-119">Щелкните пул правой кнопкой мыши и выберите пункт **Изменить свойства**, а затем **Веб-службы**.</span><span class="sxs-lookup"><span data-stu-id="57714-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="57714-120">В области **Internal web services** (Внутренние веб-службы) установите флажок **Override FQDN** (Переопределить полное доменное имя).</span><span class="sxs-lookup"><span data-stu-id="57714-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="57714-121">Введите полное доменное имя пула, которое разрешается  в физические IP-адреса серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="57714-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="57714-122">В области **External web services** (Внешние веб-службы) введите полное доменное имя внешнего пула, которое разрешается в виртуальные IP-адреса этого пула, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="57714-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="57714-123">В дереве консоли выберите **Lync Server 2013**, а затем в области **действия** щелкните **опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="57714-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="57714-124">Создание записи узлов A DNS для всех внутренних серверов пулов</span><span class="sxs-lookup"><span data-stu-id="57714-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="57714-125">Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **DNS**.</span><span class="sxs-lookup"><span data-stu-id="57714-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="57714-126">В окне **Диспетчер DNS** щелкните DNS-сервер, управляющий вашими записями, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="57714-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="57714-127">Щелкните пункт **Зоны прямого просмотра**, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="57714-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="57714-128">Щелкните правой кнопкой DNS-домен, в который требуется добавить записи, а затем щелкните **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="57714-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="57714-129">В поле **имя** введите имя записи узла (имя домена будет добавлено автоматически).</span><span class="sxs-lookup"><span data-stu-id="57714-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="57714-130">В поле "IP-адрес" введите IP-адрес отдельного сервера переднего плана и выберите **Создать соответствующую PTR-запись** или **Разрешать любому прошедшему проверку пользователю обновлять DNS-записи с таким же именем владельца**, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="57714-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="57714-131">продолжайте создавать записи для всех членов серверов переднего плана, которые будут принимать участие в балансировке нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="57714-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="57714-132">Например, если бы у вас был пул с именем pool1.contoso.com и три сервера переднего плана, потребовалось бы создать следующие DNS-записи:</span><span class="sxs-lookup"><span data-stu-id="57714-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="57714-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="57714-133">FQDN</span></span></th>
    <th><span data-ttu-id="57714-134">Тип</span><span class="sxs-lookup"><span data-stu-id="57714-134">Type</span></span></th>
    <th><span data-ttu-id="57714-135">Данные</span><span class="sxs-lookup"><span data-stu-id="57714-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="57714-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57714-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="57714-137">Узел (A)</span><span class="sxs-lookup"><span data-stu-id="57714-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="57714-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="57714-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="57714-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57714-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="57714-140">Узел (A)</span><span class="sxs-lookup"><span data-stu-id="57714-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="57714-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="57714-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="57714-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57714-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="57714-143">Узел (A)</span><span class="sxs-lookup"><span data-stu-id="57714-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="57714-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="57714-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="57714-145">Дополнительные сведения о создании записей узла DNS (A) приведены в разделе [Настройка записей узла DNS для Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="57714-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="57714-146">Включение циклического обслуживания для Windows Server</span><span class="sxs-lookup"><span data-stu-id="57714-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="57714-147">Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **DNS**.</span><span class="sxs-lookup"><span data-stu-id="57714-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="57714-148">Разверните узел **DNS**, щелкните правой кнопкой мыши DNS-сервер, который требуется настроить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="57714-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="57714-149">Откройте вкладку **Дополнительно**, выберите **Включить циклическое обслуживание** и **Включить расстановку по адресу**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="57714-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="57714-150">![Диалоговое окно циклического перебора DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Диалоговое окно циклического перебора DNS")</span><span class="sxs-lookup"><span data-stu-id="57714-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57714-151">Эта возможность должна быть включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57714-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57714-152">См. также</span><span class="sxs-lookup"><span data-stu-id="57714-152">See Also</span></span>


[<span data-ttu-id="57714-153">Балансировка нагрузки на DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57714-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

