---
title: 'Lync Server 2013: развертывание расширенных функций корпоративной голосовой связи'
description: 'Lync Server 2013: развертывание расширенных функций корпоративной голосовой связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5cab05de60e1df1611a14af1f5239c24402c6d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558585"
---
# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="bcc86-103">Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-103">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcc86-104">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="bcc86-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="bcc86-105">После настройки базовых функций Enterprise Voice для организации можно при необходимости развернуть одну или несколько расширенных функций Enterprise Voice, выполнив процедуры, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bcc86-105">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="bcc86-106">Подробные сведения о расширенных функциях корпоративной голосовой связи можно найти в следующих разделах документации по [планированию Lync Server 2013](lync-server-2013-planning.md) :</span><span class="sxs-lookup"><span data-stu-id="bcc86-106">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="bcc86-107">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="bcc86-108">Планирование экстренных служб (E9-1-1) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="bcc86-109">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="bcc86-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="bcc86-110">In This Section</span></span>

  - [<span data-ttu-id="bcc86-111">Сведения о регионах сети, сайтах и подсетях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-111">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="bcc86-112">Создание или изменение области сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-112">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="bcc86-113">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-113">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="bcc86-114">Связывание подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-114">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="bcc86-115">Настройка контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-115">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="bcc86-116">Настройка расширенного 9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-116">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="bcc86-117">Настройка обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc86-117">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

