---
title: 'Lync Server 2013: проектирование топологии с помощью средства планирования'
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
ms.openlocfilehash: 590bfae33e12cca2e2305eab9d842f0e2f105838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="797a4-102">Проектирование топологии для Lync Server 2013 с помощью средства планирования</span><span class="sxs-lookup"><span data-stu-id="797a4-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="797a4-103">_**Тема последнего изменения:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="797a4-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="797a4-104">Приложение Microsoft Lync Server 2013, планирование — это мастер, на основе которого будет заинтересовать вопросы о топологии Lync Server 2013, которые вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="797a4-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="797a4-105">В средстве планирования используются предоставленные сведения, которые связаны с предпочтительными методиками проектирования и мощности топологии, чтобы представить рекомендуемую топологию на основе предоставленных ответов.</span><span class="sxs-lookup"><span data-stu-id="797a4-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="797a4-106">Вы можете скачать средство планирования из центра загрузки Майкрософт ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span><span class="sxs-lookup"><span data-stu-id="797a4-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="797a4-107">В конечном итоге, цель средства планирования — облегчить создание полной топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="797a4-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="797a4-108">Это средство также предоставляет контекстные ссылки на внутреннюю документацию по планированию и развертыванию при условии, что доступно подключение к сети Интернет для доступа на веб-сайт TechNet корпорации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="797a4-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="797a4-109">После настройки топологии с помощью TCP/IP-адресов инфраструктуры и полных доменных имен (FQDN) средство планирования предоставляет доступ к сериям отчетов, которые охватывают имена DNS, правила брандмауэра, сертификаты и многое другое.</span><span class="sxs-lookup"><span data-stu-id="797a4-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="797a4-110">Средство планирования также предоставляет возможность экспорта данных в двух форматах:</span><span class="sxs-lookup"><span data-stu-id="797a4-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="797a4-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="797a4-111">Microsoft Excel</span></span>

  - <span data-ttu-id="797a4-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="797a4-112">Microsoft Visio</span></span>

<span data-ttu-id="797a4-113">В следующих разделах описаны и подробные сведения о средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="797a4-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="797a4-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="797a4-114">In This Section</span></span>

  - [<span data-ttu-id="797a4-115">Установка средства планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="797a4-116">Установка дополнительного программного обеспечения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="797a4-117">Навигация в инструменте "планирование" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="797a4-118">Создание начальной структуры топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="797a4-119">Просмотр отчетов администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="797a4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="797a4-120">See Also</span></span>


[<span data-ttu-id="797a4-121">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="797a4-122">Планирование для серверов переднего плана, обмена мгновенными сообщениями и сведениями о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797a4-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

