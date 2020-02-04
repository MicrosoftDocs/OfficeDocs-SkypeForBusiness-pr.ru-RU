---
title: 'Lync Server 2013: настройка DNS для поддержки пограничной топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="10faa-102">Настройка DNS для поддержки пограничной топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10faa-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10faa-103">_**Тема последнего изменения:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="10faa-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="10faa-104">Необходимо настроить записи DNS для внутренних и внешних интерфейсов EDGE, включая пограничный сервер и прокси-интерфейсы обратной стороны.</span><span class="sxs-lookup"><span data-stu-id="10faa-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="10faa-105">По умолчанию пограничные серверы не подключены к домену и не имеют полного доменного имени (полного доменного имени).</span><span class="sxs-lookup"><span data-stu-id="10faa-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="10faa-106">Сервер граничного сервера ссылается только на краткое имя (компьютер), а не полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="10faa-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="10faa-107">Однако в построителе топологии используются полные доменные имена, а не короткие.</span><span class="sxs-lookup"><span data-stu-id="10faa-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="10faa-108">Имя пограничного сервера должно совпадать с полным доменным именем, используемым построителем топологии.</span><span class="sxs-lookup"><span data-stu-id="10faa-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="10faa-109">Для этого вы определяете DNS-суффикс, после того как в сочетании с именем компьютера выводятся ожидаемые полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="10faa-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="10faa-110">Используйте описанную ниже процедуру, чтобы добавить DNS-суффикс к имени компьютера и пограничного сервера, который не присоединен к домену, чтобы добавить DNS-суффикс к имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="10faa-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10faa-111">По умолчанию DNS использует алгоритм циклического прокрутки для поворота данных о записи ресурсов, возвращенных в ответах на запросы, в которых для запрашиваемого доменного имени DNS существует несколько записей ресурсов одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="10faa-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="10faa-112">Функция балансировки нагрузки DNS для Lync Server 2013 зависит от того, что циклическая служба DNS является частью механизма балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="10faa-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="10faa-113">Убедитесь, что параметр "циклический перебор" не отключен.</span><span class="sxs-lookup"><span data-stu-id="10faa-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="10faa-114">Если вы используете DNS-сервер, на котором не установлена операционная система Windows, убедитесь, что включен порядок записей в циклической службе.</span><span class="sxs-lookup"><span data-stu-id="10faa-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="10faa-115">Воспользуйтесь приведенными ниже инструкциями **, чтобы создать**и проверить каждую DNS SRV-запись.</span><span class="sxs-lookup"><span data-stu-id="10faa-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="10faa-116">Используйте процедуру, описанную в разделе "**Создание записи DNS a**", чтобы определить DNS a-записи, необходимые для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="10faa-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="10faa-117">Чтобы убедиться в том, что записи настроены и правильно работают, ознакомьтесь с разделом "**Проверка DNS-записей**" в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="10faa-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="10faa-118">Сведения о каждой записи, необходимой для поддержки внешних пользователей, приведены в разделе [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10faa-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="10faa-119">Добавление DNS-суффикса к имени компьютера на пограничном сервере, который не входит в домен</span><span class="sxs-lookup"><span data-stu-id="10faa-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="10faa-120">На компьютере нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт **компьютер**, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="10faa-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="10faa-121">В разделе **имя компьютера, домен и параметры рабочей группы**нажмите кнопку **изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="10faa-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="10faa-122">На вкладке **имя компьютера** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="10faa-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="10faa-123">В окне **изменение имени компьютера или домена**нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="10faa-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="10faa-124">В **DNS-суффиксе и NetBIOS имени компьютера**в **основном DNS-суффиксе компьютера**введите имя своего внутреннего домена (например, Corp.contoso.com), а затем нажмите кнопку **ОК** три значения.</span><span class="sxs-lookup"><span data-stu-id="10faa-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="10faa-125">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="10faa-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="10faa-126">Создание DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="10faa-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="10faa-127">На соответствующем DNS-сервере нажмите кнопку **Пуск**, выберите **Панель управления**, щелкните **Администрирование**и выберите **DNS**.</span><span class="sxs-lookup"><span data-stu-id="10faa-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="10faa-128">Вы должны настроить DNS таким образом, чтобы были доступны: 1) внешние DNS-записи для поиска внешних DNS удаленными пользователями и федеративными партнерами; 2) записи для поиска DNS для использования пограничных серверов в демилитаризованной зоне (также называемой демилитаризованной зоной, ДМЗ и экранированной подсетью), включая записи для внутренних серверов, на которых запущен Lync Server 2013; и 3) внутренние DNS-записи для подстановок внутренних клиентов и серверов с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10faa-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="10faa-129">В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10faa-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="10faa-130">Нажмите кнопку **другие новые записи**.</span><span class="sxs-lookup"><span data-stu-id="10faa-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="10faa-131">В списке **выберите тип записи ресурса**введите **расположение службы (SRV)** и нажмите кнопку **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="10faa-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="10faa-132">Введите все необходимые сведения для DNS SRV-записи.</span><span class="sxs-lookup"><span data-stu-id="10faa-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="10faa-133">Создание записи DNS A</span><span class="sxs-lookup"><span data-stu-id="10faa-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="10faa-134">На DNS-сервере нажмите кнопку **Пуск**, выберите **Панель управления**, щелкните **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="10faa-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="10faa-135">В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**, а затем щелкните правой кнопкой мыши домен, в котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10faa-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="10faa-136">Нажмите кнопку **создать узел (A)**.</span><span class="sxs-lookup"><span data-stu-id="10faa-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="10faa-137">Введите все необходимые сведения для DNS SRV-записи.</span><span class="sxs-lookup"><span data-stu-id="10faa-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="10faa-138">Проверка записи DNS</span><span class="sxs-lookup"><span data-stu-id="10faa-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="10faa-139">Войдите в домен на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="10faa-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="10faa-140">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="10faa-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="10faa-141">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="10faa-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="10faa-142">Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="10faa-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10faa-143">См. также</span><span class="sxs-lookup"><span data-stu-id="10faa-143">See Also</span></span>


[<span data-ttu-id="10faa-144">Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="10faa-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="10faa-145">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10faa-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

