---
title: 'Lync Server 2013: сбор данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="cdebb-102">Сбор данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdebb-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdebb-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="cdebb-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="cdebb-104">В коммуникационном программном обеспечении Microsoft Lync Server 2013 вы можете использовать средство Microsoft Lync Server 2013, планирование, не задавая существующие и предложенные IP-адреса и полные доменные имена (FQDN), но значительно сложнее Поэтому, не вынуждая ошибки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cdebb-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="cdebb-105">Например, если сосуществование требуется в течение определенного периода времени, распространенной ошибкой является повторное использование полных доменных имен из существующего развертывания пограничного сервера Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="cdebb-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="cdebb-106">После того как существующие и предложенные IP-адреса и полные доменные имена записываются в электронную таблицу, таблицу или другую визуальную форму, вы помогаете предотвратить проблемы во время установки.</span><span class="sxs-lookup"><span data-stu-id="cdebb-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="cdebb-107">Если вы использовали предыдущие версии средства планирования, возможно, вы использовали это средство для создания топологии и экспортированный документ топологии для использования в построителе топологии для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="cdebb-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="cdebb-108">Возможность экспорта топологии была удалена из средства планирования.</span><span class="sxs-lookup"><span data-stu-id="cdebb-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="cdebb-109">Использование предыдущей версии средства планирования для создания документа топологии для Lync Server 2013 настоятельно не рекомендуется, и это приводит к неожиданным результатам.</span><span class="sxs-lookup"><span data-stu-id="cdebb-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="cdebb-110">Поэтому рекомендуемый подход состоит в использовании следующего шаблона сбора данных, соответствующего топологии пограничного сервера, для сбора различных полных доменных имен и IP-адресов, которые нужно будет вводить в инструмент планирования.</span><span class="sxs-lookup"><span data-stu-id="cdebb-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="cdebb-111">Задокументируйте текущую и предложенную конфигурацию, вы можете разместить значения в правильном контексте для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="cdebb-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="cdebb-112">Вы вынуждены думать о настройке сосуществования и функциональных возможностях, например простых URL-адресов, общих файловых ресурсов и балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cdebb-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="cdebb-113">Для успешного развертывания Microsoft Lync Server 2013 необходимо понимать взаимодействие и зависимость от отдельных компонентов.</span><span class="sxs-lookup"><span data-stu-id="cdebb-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="cdebb-114">Собирая данные из существующей инфраструктуры сети и сервера и применяя руководство по планированию в этих разделах, вы можете интегрировать компоненты сервера Lync Server 2013 Edge Server в инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="cdebb-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="cdebb-115">Введенные в Выбери [топологию в Lync Server 2013](lync-server-2013-choosing-a-topology.md)существуют три основные архитектуры с двумя вариантами, общее количество пяти возможных сценариев развертывания.</span><span class="sxs-lookup"><span data-stu-id="cdebb-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="cdebb-116">Один из этих сценариев будет отправной точкой для сбора данных.</span><span class="sxs-lookup"><span data-stu-id="cdebb-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="cdebb-117">IP-адреса, имена серверов и доменные имена представляют собой примеры, совпадающие с соответствующими сертификатами, брандмауэрами и DNS-схемами, которые подробно изменяют сведения, необходимые для полного решения для планирования.</span><span class="sxs-lookup"><span data-stu-id="cdebb-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="cdebb-118">Эти схемы, а также заполнение необходимых сертификатов, DNS и брандмауэров особенно важны для межгруппового обмена сообщениями, в которых Управление центром сертификации, Настройка брандмауэра и DNS управляются группами, отличными от команды, Планирование развертывания.</span><span class="sxs-lookup"><span data-stu-id="cdebb-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="cdebb-119">На схемах представлены сведения о необходимых компонентах, которые можно использовать для обмена данными о требованиях для совместной работы в разных группах.</span><span class="sxs-lookup"><span data-stu-id="cdebb-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="cdebb-120">Указанные схемы являются преднамеренными, но позволяют получить набор всех нужных данных, которые необходимы для обмена данными о требованиях в рамках межпроектной ситуации, когда сеть, брандмауэр, создание сертификатов и управление ими, сервер развертывание и управление серверами обрабатываются разными группами.</span><span class="sxs-lookup"><span data-stu-id="cdebb-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="cdebb-121">Наличие необходимых сведений о настройке сети, брандмауэрах, портах и протоколах, сертификатах и серверах не является ценным при развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdebb-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="cdebb-122">**Пул пограничного сервера и EDGE**</span><span class="sxs-lookup"><span data-stu-id="cdebb-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="cdebb-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d] (images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="cdebb-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="cdebb-124">**Обратный прокси-сервер**</span><span class="sxs-lookup"><span data-stu-id="cdebb-124">**Reverse Proxy**</span></span>

<span data-ttu-id="cdebb-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb] (images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="cdebb-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="cdebb-126">**Режиссер или режиссер**</span><span class="sxs-lookup"><span data-stu-id="cdebb-126">**Director or Director pool**</span></span>

<span data-ttu-id="cdebb-127">![56ba29ff-1309-4d5d-bf5c-35372169e947] (images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="cdebb-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

