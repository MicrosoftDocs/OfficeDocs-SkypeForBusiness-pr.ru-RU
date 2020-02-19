---
title: 'Lync Server 2013: сбор данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e198ecb80bbe0616422e10e1df18a8778196761
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="428d6-102">Сбор данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="428d6-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="428d6-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="428d6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="428d6-104">В коммуникационном программном обеспечении Microsoft Lync Server 2013 вы можете запустить средство планирования Microsoft Lync Server 2013, не Задокументируйте существующие и предложенные IP-адреса и полные доменные имена пограничных серверов, но значительно сложнее Поэтому, не вызывая ошибок конфигурации.</span><span class="sxs-lookup"><span data-stu-id="428d6-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="428d6-105">Например, если в течение определенного периода времени требуется сосуществование, то распространенной ошибкой является повторное использование FQDN из существующего пограничного развертывания для развертывания Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="428d6-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="428d6-106">Записав текущие и предлагаемые IP-адреса и полные доменные имена в электронную таблицу, обычную таблицу или другую визуальную форму, вы можете избежать ошибок во время установки.</span><span class="sxs-lookup"><span data-stu-id="428d6-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="428d6-107">Если вы использовали предыдущие версии средства планирования, возможно, вы использовали средство для создания топологии и экспортированного документа топологии, который будет использоваться в построителе топологий для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="428d6-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="428d6-108">Возможность экспорта топологии была удалена из средства планирования.</span><span class="sxs-lookup"><span data-stu-id="428d6-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="428d6-109">Использование предыдущей версии средства планирования для создания топологии документа для Lync Server 2013 не рекомендуется и приводит к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="428d6-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="428d6-110">Таким образом, рекомендуемый подход — использовать следующий шаблон сбора данных, соответствующий пограничной топологии, для сбора различных полных доменных имен и IP-адресов, которые необходимо будет ввести в средство планирования.</span><span class="sxs-lookup"><span data-stu-id="428d6-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="428d6-111">Записав текущую и предлагаемую конфигурацию, вы можете разместить значения в нужном контексте для вашей производственной среде.</span><span class="sxs-lookup"><span data-stu-id="428d6-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="428d6-112">Также вы должны подумать о том, как вы будете настроить сосуществование и такие компоненты, как простые URL-адреса, общие файловые ресурсы и балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="428d6-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="428d6-113">Для успешного развертывания Microsoft Lync Server 2013 необходимо знать взаимодействие и зависимость от отдельных компонентов.</span><span class="sxs-lookup"><span data-stu-id="428d6-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="428d6-114">Собирая данные из существующей инфраструктуры сети и сервера и применяя рекомендации по планированию, приведенные в этих разделах, можно интегрировать компоненты пограничного сервера Lync Server 2013 в инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="428d6-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="428d6-115">В [выборе топологии в Lync Server 2013](lync-server-2013-choosing-a-topology.md)существует три основные архитектуры с двумя вариациями, в которых всего пять возможных сценариев развертывания.</span><span class="sxs-lookup"><span data-stu-id="428d6-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="428d6-116">One of these scenarios will be the starting point for your data collection.</span><span class="sxs-lookup"><span data-stu-id="428d6-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="428d6-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span><span class="sxs-lookup"><span data-stu-id="428d6-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="428d6-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span><span class="sxs-lookup"><span data-stu-id="428d6-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="428d6-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span><span class="sxs-lookup"><span data-stu-id="428d6-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="428d6-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span><span class="sxs-lookup"><span data-stu-id="428d6-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="428d6-121">Наличие необходимых сведений о настройке сети, брандмауэрах, портах и протоколах, сертификатах и серверах не является ценным при развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="428d6-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="428d6-122">**Пограничный сервер и пограничный пул**</span><span class="sxs-lookup"><span data-stu-id="428d6-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="428d6-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="428d6-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="428d6-124">**Reverse Proxy**</span><span class="sxs-lookup"><span data-stu-id="428d6-124">**Reverse Proxy**</span></span>

<span data-ttu-id="428d6-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="428d6-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="428d6-126">**директор или пул директоров;**</span><span class="sxs-lookup"><span data-stu-id="428d6-126">**Director or Director pool**</span></span>

<span data-ttu-id="428d6-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="428d6-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

