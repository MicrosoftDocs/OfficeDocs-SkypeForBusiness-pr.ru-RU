---
title: 'Lync Server 2013: компоненты подключения PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa82336ed96c61315da4c25a0152ba75d15d7b6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531746"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="3cf92-102">Компоненты подключения PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cf92-102">PSTN connectivity components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf92-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3cf92-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3cf92-p101">Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS). Кроме того, пользователи не должны беспокоиться о выбранной технологии, когда размещают или получают вызовы. С точки зрения пользователя, вызовы между инфраструктурой корпоративной голосовой связи и ТСОП должны выглядеть в точности, как любой другой сеанс SIP.</span><span class="sxs-lookup"><span data-stu-id="3cf92-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="3cf92-107">Для подключений ТСОП можно развернуть либо распределение каналов SIP, либо шлюз ТСОП (с УАТС, также называемой прямой связью SIP, или без УАТС).</span><span class="sxs-lookup"><span data-stu-id="3cf92-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="3cf92-108">Распределение каналов SIP</span><span class="sxs-lookup"><span data-stu-id="3cf92-108">SIP Trunking</span></span>

<span data-ttu-id="3cf92-p102">Помимо использования шлюзов ТСОП, решение корпоративной голосовой связи можно подключать к ТСОП путем распределения каналов SIP. Распределение каналов SIP позволяет следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="3cf92-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="3cf92-111">Пользователь предприятия за корпоративным брандмауэром или вне его может выполнять местный или дальний (междугородный или международный) вызов, заданный номером, совместимым с форматом E.164, который заканчивается в ТСОП как служба соответствующего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="3cf92-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="3cf92-112">Любой абонент ТСОП может связываться с пользователем предприятия за пределами корпоративного брандмауэра или вне его, набирая номер прямого входящего набора, связанный с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="3cf92-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="3cf92-113">Для использования такого решения по развертыванию необходим поставщик услуг распределения каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="3cf92-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="3cf92-114">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="3cf92-114">PSTN gateways</span></span>

<span data-ttu-id="3cf92-115">Шлюзы ТСОП — это устройства сторонних производителей, которые передают сигналы и мультимедиа между инфраструктурой корпоративной голосовой связи и ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="3cf92-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="3cf92-116">Шлюзы ТСОП работают с сервером-посредником, чтобы представить вызов ТСОП или УАТС клиенту корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3cf92-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="3cf92-117">Сервер-посредник также представляет вызовы клиентов корпоративной голосовой связи в шлюз ТСОП для маршрутизации в ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="3cf92-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="3cf92-118">Список партнеров, работающих с корпорацией Майкрософт для предоставления устройств, работающих с Lync Server, можно найти на веб-сайте партнеров по Объединенным каналам связи Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="3cf92-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="3cf92-119">Станции УАТС</span><span class="sxs-lookup"><span data-stu-id="3cf92-119">Private Branch Exchanges</span></span>

<span data-ttu-id="3cf92-120">Если у вас есть существующая инфраструктура голосовой связи, использующая УАТС, вы можете использовать УАТС с голосовой связью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3cf92-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="3cf92-121">Поддерживаются следующие сценарии интеграции корпоративной голосовой связи с УАТС:</span><span class="sxs-lookup"><span data-stu-id="3cf92-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="3cf92-122">IP-УАТС, поддерживающий обход сервера-посредника, с сервером-посредником;</span><span class="sxs-lookup"><span data-stu-id="3cf92-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="3cf92-123">IP-УАТС, которому требуется изолированный шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="3cf92-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="3cf92-124">УАТС с временным мультиплексированием с изолированным шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="3cf92-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3cf92-125">Обход сервера-посредника не будет взаимодействовать с каждым шлюзом ТСОП, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="3cf92-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="3cf92-126">Корпорация Майкрософт протестировала ряд шлюзов ТСОП и SBC с сертифицированными партнерами и выполнила некоторые тесты с IP-УАТС компании Cisco.</span><span class="sxs-lookup"><span data-stu-id="3cf92-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3cf92-127">Обход сервера-посредника поддерживается только для продуктов и версий, перечисленных в общедоступной программе для взаимодействия с единой системой обмена сообщениями — Lync Server по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="3cf92-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="3cf92-128">Для получения сведений о партнерах, предоставляющих решения для корпоративной голосовой связи, посетите веб-сайт партнеров по Объединенным партнерам Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="3cf92-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="3cf92-129">Сведения о партнерах, предоставляющих аппаратные решения для корпоративной голосовой связи, в том числе шлюзы PSTN, можно найти на веб-сайте партнеров Объединенных коммуникаций Майкрософт [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="3cf92-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

