---
title: 'Lync Server 2013: Настройка DNS для поддержки пограничного сервера'
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
ms.openlocfilehash: d7b3dcb9693ed6ab58d2828570e81ef05709867e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="14d0a-102">Настройка DNS для поддержки пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14d0a-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d0a-103">_**Последнее изменение темы:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="14d0a-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="14d0a-104">Необходимо настроить записи службы доменных имен (DNS) для внутренних и внешних пограничных интерфейсов, включая интерфейсы пограничных серверов и интерфейсы обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="14d0a-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="14d0a-105">По умолчанию пограничные серверы не присоединены к домену и не будут иметь полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="14d0a-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="14d0a-106">На пограничный сервер можно ссылаться только по короткому (машинному) имени, а не по полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="14d0a-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="14d0a-107">Однако в построителе топологий используются полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="14d0a-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="14d0a-108">Имя пограничного сервера должно отличаться от полного доменного имени, используемого построителем топологий.</span><span class="sxs-lookup"><span data-stu-id="14d0a-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="14d0a-109">Для этого задается DNS-суффикс, который затем, после объединения с именем компьютера, дает нужное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="14d0a-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="14d0a-110">Чтобы добавить DNS-суффикс к имени компьютера, используйте процедуру, приведенную в разделе “Добавление DNS-суффикса к имени компьютера пограничного сервера, не присоединенного к домену".</span><span class="sxs-lookup"><span data-stu-id="14d0a-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14d0a-111">По умолчанию служба DNS использует алгоритм циклического прокрутки для вращения данных о записях ресурсов, возвращаемых в ответах на запросы, если для запрошенного доменного имени DNS существует несколько записей ресурсов одного типа.</span><span class="sxs-lookup"><span data-stu-id="14d0a-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="14d0a-112">Lync Server 2013 для балансировки нагрузки на DNS зависит от циклического перебора DNS в рамках механизма балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="14d0a-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="14d0a-113">Убедитесь, что параметр циклического перебора отключен.</span><span class="sxs-lookup"><span data-stu-id="14d0a-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="14d0a-114">Если используется DNS-сервер, не работающий под управлением операционной системы Windows, убедитесь, что упорядочение записей ресурсов циклического перебора включено.</span><span class="sxs-lookup"><span data-stu-id="14d0a-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="14d0a-115">Для создания и проверки каждой SRV-записи DNS используйте следующие процедуры в разделе “**Создание SRV-записи DNS**”.</span><span class="sxs-lookup"><span data-stu-id="14d0a-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="14d0a-116">Для задания А-записи DNS, необходимой для доступа внешних пользователей, используйте процедуру в разделе “**Создание А-записи DNS**”.</span><span class="sxs-lookup"><span data-stu-id="14d0a-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="14d0a-117">Для подтверждения, что записи настроены и работают правильно, см. раздел “**Проверка записи DNS**” в этой статье.</span><span class="sxs-lookup"><span data-stu-id="14d0a-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="14d0a-118">Сведения о каждой записи, необходимой для поддержки доступа внешних пользователей, приведены в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14d0a-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="14d0a-119">Добавление DNS-суффикса к имени компьютера пограничного сервера, не присоединенного к домену</span><span class="sxs-lookup"><span data-stu-id="14d0a-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="14d0a-120">Нажмите на компьютере кнопку **Пуск**, щелкните правой кнопкой мыши пункт **Компьютер** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="14d0a-121">В разделе **Имя компьютера, имя домена и параметры рабочей группы** щелкните пункт **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="14d0a-122">На вкладке **Имя компьютера** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="14d0a-123">В разделе **Изменение имени компьютера или домена** нажмите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="14d0a-124">В разделе **DNS-суффикс и NetBIOS-имя компьютера** в поле **Основной DNS-суффикс этого компьютера** ведите имя внутреннего домена (например, corp.contoso.com), а затем трижды нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="14d0a-125">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="14d0a-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="14d0a-126">Создание SRV-записи DNS</span><span class="sxs-lookup"><span data-stu-id="14d0a-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="14d0a-127">На соответствующем DNS-сервере нажмите кнопку **Пуск** и последовательно выберите пункты **Панель управления**, **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14d0a-128">Необходимо настроить DNS таким образом, чтобы: 1) внешние DNS-записи для внешних поисков DNS удаленными пользователями и федеративными партнерами; 2) записи для поиска DNS для пограничных серверов в сети периметра (также известной как DMZ, демилитаризованная зона и экранированная подсеть), включая записи для внутренних серверов, на которых работает Lync Server 2013; и 3) внутренние записи DNS для поиска внутренними клиентами и серверами, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14d0a-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="14d0a-129">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14d0a-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="14d0a-130">Щелкните элемент **Другие новые записи**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="14d0a-131">В поле **Выбор типа записи ресурса** введите **Расположение службы (запись SRV)** и нажмите **Создать запись**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="14d0a-132">Предоставьте все необходимые сведения для SRV-записи DNS.</span><span class="sxs-lookup"><span data-stu-id="14d0a-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="14d0a-133">Создание А-записи DNS</span><span class="sxs-lookup"><span data-stu-id="14d0a-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="14d0a-134">На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Панель управления**, **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="14d0a-135">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14d0a-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="14d0a-136">Щелкните элемент **Создать узел (A)**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="14d0a-137">Предоставьте все необходимые сведения для А-записи DNS.</span><span class="sxs-lookup"><span data-stu-id="14d0a-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="14d0a-138">Проверка записи DNS</span><span class="sxs-lookup"><span data-stu-id="14d0a-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="14d0a-139">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="14d0a-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="14d0a-140">Нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="14d0a-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="14d0a-141">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14d0a-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="14d0a-142">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="14d0a-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14d0a-143">См. также</span><span class="sxs-lookup"><span data-stu-id="14d0a-143">See Also</span></span>


[<span data-ttu-id="14d0a-144">Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="14d0a-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="14d0a-145">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14d0a-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

