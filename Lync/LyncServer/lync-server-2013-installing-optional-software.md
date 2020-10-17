---
title: 'Lync Server 2013: Установка дополнительного программного обеспечения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f56d856aa0a97125812f68ede9a2bff5b49f036
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498536"
---
# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="f5b21-102">Установка дополнительного программного обеспечения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b21-102">Installing optional software in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5b21-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f5b21-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f5b21-104">Microsoft Lync Server 2013, средство планирования предназначено для экспорта в Microsoft Excel и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="f5b21-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="f5b21-105">Несмотря на то, что эти приложения не требуются для работы средства планирования, они имеют существенные значения для развертывания и документирования проекта.</span><span class="sxs-lookup"><span data-stu-id="f5b21-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="f5b21-106">Дополнительное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="f5b21-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="f5b21-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="f5b21-107">Microsoft Excel</span></span>

<span data-ttu-id="f5b21-108">При экспорте проекта в Microsoft Excel создается отчет, отображающий семь вкладок в электронной таблице:</span><span class="sxs-lookup"><span data-stu-id="f5b21-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="f5b21-109">Сводка — отображает сведения о конфигурации сайта, включая количество пользователей, параметры емкости и сведения о профиле сервера.</span><span class="sxs-lookup"><span data-stu-id="f5b21-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="f5b21-110">Profile (профиль оборудования) — отображает отчет о рекомендуемых конфигурациях оборудования для серверов, указанных в топологии, в том числе ЦП, памяти, диска и сетевого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f5b21-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="f5b21-111">Также включается количество и Рекомендуемые характеристики серверных компонентов.</span><span class="sxs-lookup"><span data-stu-id="f5b21-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="f5b21-112">Кроме того, каждый сервер определяется сайтом для предоставления полного представления серверных требований по сайту.</span><span class="sxs-lookup"><span data-stu-id="f5b21-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="f5b21-113">Требования к портам — отображает отчет обо всех включенных портах и о сопоставлении с балансировкой нагрузки системы доменных имен (DNS) и аппаратной балансировкой нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="f5b21-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="f5b21-114">Этот отчет следует использовать для планирования конфигурации брандмауэра и балансировки нагрузки DNS и HLB.</span><span class="sxs-lookup"><span data-stu-id="f5b21-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="f5b21-115">Сводный отчет — отображает общую сводку по параметрам, необходимым для настройки сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f5b21-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="f5b21-116">Отчет о сертификатах — отображает имя субъекта и альтернативные имена субъекта, необходимые для сертификатов, необходимых для получения запущенных пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="f5b21-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="f5b21-117">Отчет о брандмауэре — отображает исходные и конечные порты и IP-адреса для внешних и внутренних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f5b21-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="f5b21-118">DNS Report — отображает полное доменное имя (FQDN) и IP/IP-адрес, необходимые для каждой создаваемой записи DNS.</span><span class="sxs-lookup"><span data-stu-id="f5b21-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="f5b21-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="f5b21-119">Microsoft Visio</span></span>

<span data-ttu-id="f5b21-120">При экспорте проекта в Microsoft Visio создается схема, используемая в целях вашей документации в настроенной топологии и инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="f5b21-120">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="f5b21-121">Импортированная схема может быть изменена и упорядочена в соответствии с потребностями в документации.</span><span class="sxs-lookup"><span data-stu-id="f5b21-121">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="f5b21-122">Типичная схема Visio будет включать:</span><span class="sxs-lookup"><span data-stu-id="f5b21-122">The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5b21-123">Если ваша структура достаточно велика, чтобы потребовать более трех серверов переднего плана, будет создана дополнительная страница для пула переднего плана, серверов переднего плана, компьютера с SQL Server, IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="f5b21-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="f5b21-124">Глобальная топология — схема настроенных сайтов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b21-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="f5b21-125">Вкладка "имя сайта" — отображает топологию конфигурации сайта с пограничным сервером, брандмауэром, телефонной сетью общего пользования (PSTN) с шлюзами и внутренним развертыванием сервера.</span><span class="sxs-lookup"><span data-stu-id="f5b21-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="f5b21-126">Внутреннее развертывание состоит из настроенных серверов и пулов, в том числе интерфейсных пулов, серверов SQL Server, доменных служб Active Directory, директоров, серверов единой системы обмена сообщениями Exchange, серверов почтовых ящиков Exchange, серверов Office Web Apps, серверов-посредников и серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f5b21-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="f5b21-127">Схема пограничной сети — схема детализации конфигурации пограничного сервера со связанными IP-адресами и полными доменными именами.</span><span class="sxs-lookup"><span data-stu-id="f5b21-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="f5b21-128">Также включается балансировка нагрузки на DNS и аппаратные подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f5b21-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="f5b21-129">Кроме того, отображаются режиссеры и сервер переднего плана или интерфейсный пул с соответствующей службой DNS фунтов или HLB и назначенным IP-адресом (средство планирования поддерживает как IPv4-, так и IPv6-адреса) и полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="f5b21-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5b21-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f5b21-130">See Also</span></span>


[<span data-ttu-id="f5b21-131">Установка средства планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b21-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

