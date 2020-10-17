---
title: Подготовка к установке серверов в сети периметра
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e94a12dc44a73c7117ddd21707e95372fae8b69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506906"
---
# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="39fbc-102">Подготовка к установке серверов в сети периметра для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39fbc-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="39fbc-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="39fbc-104">Перед настройкой компонентов пограничного сервера необходимо убедиться, что настраиваемые компьютеры удовлетворяют системным требованиям, и выполнить другие предварительные действия, необходимые для развертывания компонентов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="39fbc-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="39fbc-105">Прежде чем начать, изучите следующие разделы документации по планированию, посвященные эталонной архитектуре, которую требуется развернуть.</span><span class="sxs-lookup"><span data-stu-id="39fbc-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="39fbc-106">Единый консолидированный край с частными IP-адресами и NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="39fbc-107">Единый консолидированный край с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="39fbc-108">Масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами, использующими NAT, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="39fbc-109">Масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="39fbc-110">Масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="39fbc-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="39fbc-111">In This Section</span></span>

  - [<span data-ttu-id="39fbc-112">Настройка DNS для поддержки пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="39fbc-113">Настройка подсистем балансировки нагрузки оборудования для масштабируемых пограничных топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="39fbc-114">Настройка брандмауэров и портов для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="39fbc-115">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="39fbc-116">Запрос сертификатов для пограничных компонентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fbc-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

