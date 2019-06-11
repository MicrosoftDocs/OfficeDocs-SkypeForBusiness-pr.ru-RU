---
title: 'Lync Server 2013: настройка сетевых адаптеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3469e9d5fa3f7aeb45bc8f35ff692d97d09b8481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="714bd-102">Настройка сетевых адаптеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="714bd-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="714bd-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="714bd-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="714bd-104">Необходимо назначить один или несколько IP-адресов для внешнего сетевого адаптера и по крайней мере один IP-адрес для адаптера внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="714bd-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="714bd-105">В описанных ниже процедурах сервер, на котором запущен шлюз Forefront Threat Management Gateway (TMG) 2010 или Internet Information Server, использует два сетевых адаптера:</span><span class="sxs-lookup"><span data-stu-id="714bd-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="714bd-106">Общедоступный или внешний сетевой адаптер для клиентов, которые пытаются подключиться к веб-сайту (то есть, обычно через Интернет).</span><span class="sxs-lookup"><span data-stu-id="714bd-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="714bd-107">Частный (внутренний) сетевой интерфейс для внутренних серверов Lync Server, на которых размещены веб-службы.</span><span class="sxs-lookup"><span data-stu-id="714bd-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="714bd-108">Как и пограничные серверы, вы можете указать шлюз по умолчанию только на внешнем сетевом адаптере.</span><span class="sxs-lookup"><span data-stu-id="714bd-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="714bd-109">Шлюзом по умолчанию будет IP-адрес маршрутизатора или внешний брандмауэр, который направляет трафик в Интернет.</span><span class="sxs-lookup"><span data-stu-id="714bd-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="714bd-110">Для трафика, предназначенного для обратного прокси-сервера, на внутреннем сетевом адаптере, подключенном к внутренней сети, необходимо использовать постоянные статические маршруты (такие как команда Route в Windows Server) для всех подсетей, содержащих серверы, на которые ссылается правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="714bd-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="714bd-111">Настройка постоянного маршрута не приводит к тому, что компьютер станет маршрутизатором.</span><span class="sxs-lookup"><span data-stu-id="714bd-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="714bd-112">Если переадресация IP не включена, компьютер работает только с конкретным трафиком, направленным на другую сеть, на соответствующий интерфейс.</span><span class="sxs-lookup"><span data-stu-id="714bd-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="714bd-113">Это заключается в том, что установка двух шлюзов — один по умолчанию, указывающий на внешние сети, и один для трафика, направленного внутреннему интерфейсу, а также маршрутизатору или другой сети.</span><span class="sxs-lookup"><span data-stu-id="714bd-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="714bd-114">Однако создание постоянных маршрутов для всех подсетей может быть недоступно, если маршрутизаторы сети настроены для суммирования маршрутов.</span><span class="sxs-lookup"><span data-stu-id="714bd-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="714bd-115">Создайте постоянный маршрут к сети, в которой определен маршрутизатор, и используйте маршрутизатор в качестве шлюза по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="714bd-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="714bd-116">Если вы не знаете, как настроить конфигурацию сети и хотите узнать, какие постоянные маршруты нужно создать, обратитесь к специалистам сети компании.</span><span class="sxs-lookup"><span data-stu-id="714bd-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="714bd-117">Обратный прокси-сервер должен поддерживать записи DNS Host (A) для внутреннего режиссера, сервера переднего или клиентского доступа и доменных имен следующего прыжка, используемых в правилах веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="714bd-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="714bd-118">Как и пограничные серверы, в целях обеспечения безопасности мы рекомендуем не настраивать обратный прокси для использования DNS-сервера, расположенного во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="714bd-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="714bd-119">Это означает, что вам нужны DNS-серверы в сети периметра, или необходимо, чтобы в обратном прокси-сервере были размещены записи файлов, которые разрешают каждый из этих полных доменных имен на внутренний IP-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="714bd-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="714bd-120">Настройка плат сетевого адаптера на обратном прокси-компьютере</span><span class="sxs-lookup"><span data-stu-id="714bd-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="714bd-121">На сервере Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2, работающем в качестве обратного прокси-сервера, откройте вкладку **изменить параметры адаптера** , нажав кнопку **Пуск**и выбрав пункты **Панель управления**, **сеть. и общий доступ**, а затем щелкните **изменить параметры адаптера**.</span><span class="sxs-lookup"><span data-stu-id="714bd-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="714bd-122">Щелкните правой кнопкой мыши Внешнее сетевое подключение, которое вы хотите использовать для внешнего интерфейса, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="714bd-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="714bd-123">На странице " **Свойства** " откройте вкладку **сеть** , выберите в этом соединении **протокол IP версии 4 (TCP/IPv4)** , в котором используется список **следующие элементы** , и нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="714bd-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="714bd-124">На странице **Свойства Протокол Интернета (TCP/IP)** настройте IP-адреса в соответствии с сетевой подсетью, к которой подключен сетевой адаптер.</span><span class="sxs-lookup"><span data-stu-id="714bd-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="714bd-125">Если обратный прокси уже используется другими приложениями, использующими HTTPS/TCP/443, например для публикации Outlook Web Access, необходимо добавить другой IP-адрес, чтобы можно было опубликовать веб-службы Lync Server 2013 на HTTPS/TCP/443 без помех с помощью существующих правил и веб-прослушивателей или необходимо заменить существующий сертификат на другой, который добавляет к альтернативному имени субъекта новые имена внешних полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="714bd-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="714bd-126">Нажмите кнопку **ОК**, а затем — кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="714bd-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="714bd-127">В окне " **Сетевые подключения**" щелкните правой кнопкой мыши внутреннее сетевое подключение, которое вы хотите использовать для внутреннего интерфейса, и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="714bd-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="714bd-128">Повторите действия 3 – 5, чтобы настроить внутреннее сетевое соединение.</span><span class="sxs-lookup"><span data-stu-id="714bd-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

