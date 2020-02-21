---
title: 'Lync Server 2013: Разработка топологии с помощью средства планирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c519e6b89051dd2034c528a817a34afb9044f1e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="6a76b-102">Разработка топологии для Lync Server 2013 с помощью средства планирования</span><span class="sxs-lookup"><span data-stu-id="6a76b-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a76b-103">_**Последнее изменение темы:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="6a76b-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="6a76b-104">Microsoft Lync Server 2013, средство планирования — это средство, которое управляется мастером, которое запрашивает вопросы о разрабатываемой топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a76b-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="6a76b-105">В средстве планирования используются предоставленные сведения, которые связаны с рекомендуемыми рекомендациями по проектированию и емкости топологии, чтобы представить рекомендуемую топологию на основе предоставленных ответов.</span><span class="sxs-lookup"><span data-stu-id="6a76b-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="6a76b-106">Средство планирования можно скачать в центре загрузки Майкрософт ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span><span class="sxs-lookup"><span data-stu-id="6a76b-106">You can download the Planning Tool from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="6a76b-107">В конечном итоге, цель средства планирования заключается в том, чтобы упростить разработку полной топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a76b-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="6a76b-108">Средство также предоставляет контекстные ссылки на документацию по планированию и развертыванию в средстве, при условии, что подключение к Интернету доступно для подключения к веб-сайту Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="6a76b-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="6a76b-109">После настройки топологии с использованием TCP/IP-адресов и полных доменных имен в инфраструктуре средство планирования предоставляет доступ к ряду отчетов, которые охватывают имена DNS, правила брандмауэра, сертификаты и многое другое.</span><span class="sxs-lookup"><span data-stu-id="6a76b-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="6a76b-110">Средство планирования также предоставляет возможность экспорта данных в двух форматах:</span><span class="sxs-lookup"><span data-stu-id="6a76b-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="6a76b-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="6a76b-111">Microsoft Excel</span></span>

  - <span data-ttu-id="6a76b-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="6a76b-112">Microsoft Visio</span></span>

<span data-ttu-id="6a76b-113">В следующих разделах описываются и подробно рассматриваются средства планирования.</span><span class="sxs-lookup"><span data-stu-id="6a76b-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a76b-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="6a76b-114">In This Section</span></span>

  - [<span data-ttu-id="6a76b-115">Установка средства планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="6a76b-116">Установка дополнительного программного обеспечения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="6a76b-117">Навигация в средстве планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="6a76b-118">Создание первоначальной структуры топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="6a76b-119">Просмотр отчетов администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a76b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6a76b-120">See Also</span></span>


[<span data-ttu-id="6a76b-121">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="6a76b-122">Планирование для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a76b-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

