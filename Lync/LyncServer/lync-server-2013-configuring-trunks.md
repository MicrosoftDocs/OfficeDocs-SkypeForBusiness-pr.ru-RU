---
title: 'Lync Server 2013: Настройка магистральных каналов'
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
ms.openlocfilehash: 9c2fd4a79937477edbe01f5550a81e92a663d3d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517346"
---
# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="c203a-102">Настройка магистральных линий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-102">Configuring trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c203a-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c203a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c203a-104">При развертывании корпоративной голосовой связи вы можете настроить магистраль между сервером-посредником и одним или несколькими из следующих одноранговых узлов, чтобы обеспечить подключение к телефонной сети общего пользования (PSTN) для клиентов и устройств корпоративной голосовой связи в Организации:</span><span class="sxs-lookup"><span data-stu-id="c203a-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="c203a-105">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="c203a-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="c203a-106">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="c203a-106">PSTN gateway</span></span>

  - <span data-ttu-id="c203a-107">УАТС</span><span class="sxs-lookup"><span data-stu-id="c203a-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="c203a-108">Дополнительные сведения приведены в статье [Планирование подключения PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c203a-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c203a-109">Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c203a-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="c203a-110">Дополнительные сведения приведены в разделе <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">определение шлюза в построителе топологий в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c203a-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c203a-111">В рамках настройки магистрали можно включить функцию обхода сервера-посредника Lync Server 2013, что позволяет мультимедиа обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="c203a-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="c203a-112">Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="c203a-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="c203a-113">Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-media-bypass.md">Планирование обхода сервера мультимедиа в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c203a-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c203a-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="c203a-114">In This Section</span></span>

  - [<span data-ttu-id="c203a-115">Поддержка нескольких магистральных каналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="c203a-116">Маршрутизация между магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="c203a-117">Просмотр сведений о конфигурации магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="c203a-118">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="c203a-119">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="c203a-120">Создание новой коллекции параметров конфигурации магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="c203a-121">Удаление существующей коллекции параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c203a-122">Изменение параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c203a-123">Проверка параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c203a-124">Просмотр сведений об отдельных магистральных магистральных каналах SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c203a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c203a-125">See Also</span></span>


[<span data-ttu-id="c203a-126">Определение шлюза в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="c203a-127">Планирование подключения по протоколу PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="c203a-128">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c203a-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

