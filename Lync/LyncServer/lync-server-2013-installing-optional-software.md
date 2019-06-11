---
title: 'Lync Server 2013: Установка дополнительного программного обеспечения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="8ae73-102">Установка дополнительного программного обеспечения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ae73-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ae73-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8ae73-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8ae73-104">Microsoft Lync Server 2013, средство планирования предназначено для экспорта в Microsoft Excel и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="8ae73-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="8ae73-105">Несмотря на то, что эти приложения не требуются для работы средства планирования, они добавляют значительные значения в развертывание и документацию проекта.</span><span class="sxs-lookup"><span data-stu-id="8ae73-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="8ae73-106">Дополнительное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="8ae73-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="8ae73-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8ae73-107">Microsoft Excel</span></span>

<span data-ttu-id="8ae73-108">Экспорт проекта в Microsoft Excel приводит к созданию отчета, в котором отображаются семь вкладок в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="8ae73-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="8ae73-109">Сводка – отображает сведения о конфигурации сайта, включая количество пользователей, настройки вместимости и сведения о профиле сервера.</span><span class="sxs-lookup"><span data-stu-id="8ae73-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="8ae73-p102">Профиль оборудования – отображает отчет по рекомендуемым конфигурациям оборудования для серверов, которые указаны в топологии, включая процессор, память, диск и сетевой интерфейс. Также указывается количество и рекомендуемые характеристики для серверных компонентов. Кроме того, определяется сайт для каждого сервера, чтобы обеспечить полное представление требований сервера для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="8ae73-p102">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface. The quantity and recommended specifications for the server components are also included. In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="8ae73-p103">Требования к портам – отображает отчет обо всех включенных портах и связи с балансировкой нагрузки на DNS и аппаратных средствах балансировки нагрузки (HLB). Следует использовать этот отчет для планирования конфигураций брандмауэра, DNS LB и HLB.</span><span class="sxs-lookup"><span data-stu-id="8ae73-p103">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB). You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="8ae73-115">Сводный отчет: Общие сведения о параметрах, которые необходимы для настройки сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8ae73-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="8ae73-116">Отчет о сертификатах — отображает имя субъекта и альтернативные имена субъектов, необходимые для сертификатов, необходимых для получения запущенных пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="8ae73-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="8ae73-117">Отчет по брандмауэру – отображают исходные порты, порты назначения и IP-адреса для внешних и внутренних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8ae73-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="8ae73-118">Отчет DNS – отображает полное доменное имя (FQDN) и адреса IP/VIP, необходимые для каждой создаваемой записи DNS.</span><span class="sxs-lookup"><span data-stu-id="8ae73-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="8ae73-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="8ae73-119">Microsoft Visio</span></span>

<span data-ttu-id="8ae73-p104">Экспорт проекта в Microsoft Visio приводит к созданию схемы для использования в целях документирования настроенной топологии и инфраструктуры. Импортированную схему диаграммы можно редактировать и переупорядочивать для удовлетворения ваших требований в отношении документирования. Стандартная схема Visio будет включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="8ae73-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ae73-123">Если на вашем макете требуется больше трех серверов переднего плана, будет создана дополнительная страница для пула переднего плана, серверов переднего плана, компьютера с SQL Server, IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="8ae73-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="8ae73-124">Глобальная топология: схема настроенных сайтов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ae73-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="8ae73-125">Вкладка "имя сайта" — отображает топологию конфигурации сайта с пограничным сервером, брандмауэром, коммутируемой телефонной сетью (PSTN) с шлюзами и внутренним развертыванием сервера.</span><span class="sxs-lookup"><span data-stu-id="8ae73-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="8ae73-126">Внутреннее развертывание состоит из настроенных серверов и пулов, в том числе интерфейсных пулов, серверов SQL Server, доменных служб Active Directory, режиссеров, серверов единой системы обмена сообщениями Exchange, серверов почтовых ящиков, сервера Exchange Web Apps. Серверы обновлений и сохраняемые серверы чата.</span><span class="sxs-lookup"><span data-stu-id="8ae73-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="8ae73-127">Схема пограничного сетевого графика — схема подробностей настройки пограничного сервера с соответствующими IP-адресами и FQDN.</span><span class="sxs-lookup"><span data-stu-id="8ae73-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="8ae73-128">DNS load balancing and hardware load balancers are also included.</span><span class="sxs-lookup"><span data-stu-id="8ae73-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="8ae73-129">Кроме того, отображаются режиссеры и внешний сервер или пул переднего плана с соответствующей службой DNS фунтов или ХЛБ и назначенным IP-адресом (средство планирования поддерживает оба адреса IPv4 и IPv6) и полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="8ae73-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ae73-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8ae73-130">See Also</span></span>


[<span data-ttu-id="8ae73-131">Установка средства планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ae73-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

