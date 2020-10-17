---
title: 'Lync Server 2013: Настройка сетевых адаптеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 662ad7425a248148e9e2dde0c8f18ccea5add0c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520566"
---
# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="9436e-102">Настройка сетевых адаптеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9436e-102">Configure network adapters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9436e-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9436e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9436e-104">Необходимо назначить один или несколько IP-адресов внешнему сетевому адаптеру и по крайней мере один IP-адрес внутреннему сетевому адаптеру.</span><span class="sxs-lookup"><span data-stu-id="9436e-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="9436e-105">В следующих процедурах сервер, на котором работает сервер Forefront Threat Management Gateway (TMG) 2010 или Internet Information Server, использует два сетевых адаптера:</span><span class="sxs-lookup"><span data-stu-id="9436e-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="9436e-106">Общедоступный (или внешний) сетевой адаптер для клиентов, которые пытаются подключиться к веб-сайту (это, как правило, осуществляется через Интернет).</span><span class="sxs-lookup"><span data-stu-id="9436e-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="9436e-107">Частный или внутренний сетевой интерфейс для внутренних серверов, на которых работает Lync Server, на которых размещены веб-службы.</span><span class="sxs-lookup"><span data-stu-id="9436e-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9436e-108">Как и пограничные серверы, шлюз по умолчанию устанавливается только на внешнем сетевом адаптере.</span><span class="sxs-lookup"><span data-stu-id="9436e-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="9436e-109">Шлюзом по умолчанию будет IP-адрес маршрутизатора или внешнего брандмауэра, который перенаправляет трафик в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9436e-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="9436e-110">Для трафика, направляемого от обратного прокси-сервера на внутренний сетевой адаптер, необходимо использовать постоянные статические маршруты (например, команду route на сервере Windows Server) для всех подсетей, содержащих серверы, на которые ссылаются правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="9436e-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="9436e-111">Установка постоянного маршрута не приводит к тому, что компьютер становится маршрутизатором.</span><span class="sxs-lookup"><span data-stu-id="9436e-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="9436e-112">Если пересылка IP не включена, компьютер работает только с прямым конкретным трафиком, предназначенным для другой сети, к соответствующему интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="9436e-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="9436e-113">По сути, это настройка двух шлюзов — один по умолчанию, указывающий на внешние сети, а другой — для трафика, направляемого внутреннему интерфейсу и на маршрутизатор или другую сеть.</span><span class="sxs-lookup"><span data-stu-id="9436e-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="9436e-p102">Однако создание постоянных маршрутов для всех подсетей может не потребоваться, если маршрутизаторы сети настроены на суммирования маршрутов. Создайте постоянный маршрут к сети, где задан маршрутизатор, и используйте маршрутизатор в качестве шлюза по умолчанию. Если вы не уверены в том, каким образом настроена ваша сеть, и вам требуются рекомендации относительно того, требуется ли создание постоянных маршрутов, проконсультируйтесь с сетевыми инженерами компании.</span><span class="sxs-lookup"><span data-stu-id="9436e-p102">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes. Create a persistent route to the network where the router is defined and use the router as the default gateway. If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="9436e-117">Обратный прокси-сервер должен иметь возможность разрешать записи узла (A) DNS для внутреннего директора, сервера переднего плана или пула следующего прыжка FQDN, используемого в правилах веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="9436e-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="9436e-118">Как и в случае с пограничными серверами, в целях безопасности не рекомендуется настраивать обратный прокси для использования DNS-сервера, расположенного во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="9436e-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="9436e-119">Это означает, что вам требуются либо серверы DNS в сети периметра, либо записи файлов HOSTS на обратном прокси-сервере, которые разрешают все эти полные доменные имена во внутренний IP-адрес серверов.</span><span class="sxs-lookup"><span data-stu-id="9436e-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="9436e-120">Настройка плат сетевых адаптеров на обратном прокси-сервере</span><span class="sxs-lookup"><span data-stu-id="9436e-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="9436e-121">На сервере Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2, запущенном в качестве обратного прокси-сервера, откройте **Параметры настройки адаптера** , нажав кнопку **Пуск**, выбрав пункт **Панель управления**, затем щелкните **центр управления сетями и общим доступом**, а затем щелкните **изменить параметры адаптера**.</span><span class="sxs-lookup"><span data-stu-id="9436e-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="9436e-122">Щелкните правой кнопкой мыши внешнее сетевое подключение, которое необходимо использовать для внешнего интерфейса, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9436e-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="9436e-123">На странице **Свойства** щелкните **Сетевые подключения**, щелкните **Протокол Интернета версии 4 (TCP/IPv4)** в списке **Компоненты, используемые этим подключением:**, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9436e-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="9436e-124">На странице **Свойства протокола Интернета (TCP/IP)** настройте IP-адреса необходимым образом в соответствии с требованиями подсети, к которой подключается сетевой адаптер.</span><span class="sxs-lookup"><span data-stu-id="9436e-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9436e-125">Если обратный прокси-сервер уже используется другими приложениями, использующими протокол HTTPS/TCP/443, например, для публикации Outlook Web Access необходимо добавить еще один IP-адрес, чтобы можно было опубликовать веб-службы Lync Server 2013 на HTTPS/TCP/443, не нарушая существующие правила и веб-прослушиватели, или заменить существующий сертификат на другой, который добавляет новые внешние имена в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="9436e-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="9436e-126">Щелкните **ОК**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9436e-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="9436e-127">В разделе **Сетевые подключения** щелкните правой кнопкой мыши внутреннее сетевое подключение, которое необходимо использовать для внутреннего интерфейса, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9436e-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="9436e-128">Повторите шаги 3–5 для настройки подключения к внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="9436e-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

