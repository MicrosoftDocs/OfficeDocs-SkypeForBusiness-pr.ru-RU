---
title: 'Lync Server 2013: Настройка магистральных каналов'
description: 'Lync Server 2013: Настройка магистральных каналов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07d9503cd38419a7145796a6edf8484a14cdeb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544155"
---
# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="46021-103">Настройка магистральных линий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-103">Configuring trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46021-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="46021-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="46021-105">При развертывании корпоративной голосовой связи вы можете настроить магистраль между сервером-посредником и одним или несколькими из следующих одноранговых узлов, чтобы обеспечить подключение к телефонной сети общего пользования (PSTN) для клиентов и устройств корпоративной голосовой связи в Организации:</span><span class="sxs-lookup"><span data-stu-id="46021-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="46021-106">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="46021-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="46021-107">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="46021-107">PSTN gateway</span></span>

  - <span data-ttu-id="46021-108">УАТС</span><span class="sxs-lookup"><span data-stu-id="46021-108">Private branch exchange (PBX)</span></span>

<span data-ttu-id="46021-109">Дополнительные сведения приведены в статье [Планирование подключения PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="46021-109">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46021-110">Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="46021-110">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="46021-111">Дополнительные сведения приведены в разделе <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">определение шлюза в построителе топологий в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="46021-111">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="46021-112">В рамках настройки магистрали можно включить функцию обхода сервера-посредника Lync Server 2013, что позволяет мультимедиа обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="46021-112">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="46021-113">Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="46021-113">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="46021-114">Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-media-bypass.md">Планирование обхода сервера мультимедиа в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="46021-114">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="46021-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="46021-115">In This Section</span></span>

  - [<span data-ttu-id="46021-116">Поддержка нескольких магистральных каналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-116">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="46021-117">Маршрутизация между магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-117">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="46021-118">Просмотр сведений о конфигурации магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-118">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="46021-119">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-119">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="46021-120">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-120">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="46021-121">Создание новой коллекции параметров конфигурации магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-121">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="46021-122">Удаление существующей коллекции параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-122">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="46021-123">Изменение параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-123">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="46021-124">Проверка параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-124">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="46021-125">Просмотр сведений об отдельных магистральных магистральных каналах SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-125">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46021-126">См. также</span><span class="sxs-lookup"><span data-stu-id="46021-126">See Also</span></span>


[<span data-ttu-id="46021-127">Определение шлюза в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-127">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="46021-128">Планирование подключения по протоколу PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-128">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="46021-129">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46021-129">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

