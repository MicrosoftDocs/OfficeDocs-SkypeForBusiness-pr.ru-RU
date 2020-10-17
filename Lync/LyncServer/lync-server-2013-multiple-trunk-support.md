---
title: 'Lync Server 2013: поддержка нескольких магистральных каналов'
description: 'Lync Server 2013: поддержка нескольких магистральных каналов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552425"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="7b87c-103">Поддержка нескольких магистральных каналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b87c-103">Multiple trunk support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b87c-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7b87c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7b87c-105">Lync Server 2013 функциональность поддерживает множественные связи между шлюзами и серверами-посредниками.</span><span class="sxs-lookup"><span data-stu-id="7b87c-105">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="7b87c-106">Эти связи создаются путем определения магистрали, которая является логической связью между пулом серверов-посредника и шлюзом телефонной сети общего пользования (PSTN), пограничным контроллером сеансов (SBC) или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="7b87c-106">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="7b87c-107">С помощью построителя топологий свяжите шлюзы с серверами-посредниками (то есть магистральными каналами).</span><span class="sxs-lookup"><span data-stu-id="7b87c-107">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="7b87c-108">Чтобы назначить или удалить магистраль в Lync Server 2013, необходимо сначала определить магистраль в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="7b87c-108">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="7b87c-109">Магистраль состоит из следующей связи: полное доменное имя сервера-посредника, прослушивающий порт сервера-посредника, полное доменное имя шлюза и прослушивающий порт шлюза.</span><span class="sxs-lookup"><span data-stu-id="7b87c-109">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="7b87c-110">Чтобы настроить несколько магистральных каналов, можно создать несколько связей между одним и тем же шлюзом и сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="7b87c-110">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="7b87c-111">Это обеспечивает дополнительную устойчивость инфраструктуры корпоративной голосовой связи, которая особенно полезна в сценариях взаимодействия с частными филиалами (УАТС).</span><span class="sxs-lookup"><span data-stu-id="7b87c-111">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="7b87c-112">После определения магистрали ее необходимо связать с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="7b87c-112">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="7b87c-113">Чтобы связать магистраль с маршрутом, определите простое имя для магистрали в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="7b87c-113">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="7b87c-114">Это простое имя используется в качестве имени магистрали в панели управления Lync Server, где магистральные линии связи могут быть связаны с маршрутами.</span><span class="sxs-lookup"><span data-stu-id="7b87c-114">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="7b87c-115">Простое имя магистрали используется в качестве имени шлюза в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b87c-115">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="7b87c-116">Администратор должен выбрать магистраль по умолчанию, связанный с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="7b87c-116">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="7b87c-117">В построителе топологий щелкните правой кнопкой мыши связанный сервер-посредник и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7b87c-117">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="7b87c-118">Укажите шлюз по умолчанию для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7b87c-118">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="7b87c-119">На следующей схеме показаны несколько магистральных линий, определенных для каждого сервера-посредника и шлюза.</span><span class="sxs-lookup"><span data-stu-id="7b87c-119">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="7b87c-120">**Маршрутизация магистрали M-N**</span><span class="sxs-lookup"><span data-stu-id="7b87c-120">**M-N Trunk Routing**</span></span>

<span data-ttu-id="7b87c-121">![Несколько назначений магистрали.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Несколько назначений магистрали.")</span><span class="sxs-lookup"><span data-stu-id="7b87c-121">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

