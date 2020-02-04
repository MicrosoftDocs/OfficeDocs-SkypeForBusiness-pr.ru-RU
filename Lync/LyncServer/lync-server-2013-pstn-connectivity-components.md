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
ms.openlocfilehash: 63b5534b817477ea42dbefd5244c974fc70881f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="d8c39-102">Компоненты подключения PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8c39-102">PSTN connectivity components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c39-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d8c39-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d8c39-104">Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="d8c39-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="d8c39-105">Кроме того, при совершении и приеме вызовов пользователи не должны знать об этой базовой технологии.</span><span class="sxs-lookup"><span data-stu-id="d8c39-105">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="d8c39-106">С точки зрения пользователя, Звонок между корпоративной инфраструктурой голосовой связи и PSTN должен казаться всего, как один сеанс SIP.</span><span class="sxs-lookup"><span data-stu-id="d8c39-106">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="d8c39-107">Для ТСОП-соединений вы можете развернуть либо магистраль SIP, либо шлюз ТСОП (вместе с УАТС, также известной как прямой канал SIP, или без УАТС).</span><span class="sxs-lookup"><span data-stu-id="d8c39-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="d8c39-108">Транкинг SIP</span><span class="sxs-lookup"><span data-stu-id="d8c39-108">SIP Trunking</span></span>

<span data-ttu-id="d8c39-109">В качестве альтернативы шлюзам PSTN вы можете подключить корпоративную голосовую связь к сети PSTN с помощью магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="d8c39-109">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="d8c39-110">Организация магистральной сети SIP позволяет реализовать следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="d8c39-110">SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="d8c39-111">Пользователь предприятия за корпоративным брандмауэром или вне его может выполнять местный или дальний (междугородный или международный) вызов, заданный номером, совместимым с форматом E.164, который заканчивается на ТСОП как служба соответствующего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="d8c39-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="d8c39-112">Любой абонент ТСОП может связываться с пользователем предприятия за пределами корпоративного брандмауэра или вне его, набирая номер прямого входящего набора, связанный с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="d8c39-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="d8c39-113">Для использования такого решения по развертыванию необходим поставщик услуг транкинга SIP.</span><span class="sxs-lookup"><span data-stu-id="d8c39-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="d8c39-114">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="d8c39-114">PSTN gateways</span></span>

<span data-ttu-id="d8c39-115">Шлюзы PSTN – это сторонние устройства, которые преобразуют сигналы и носители между корпоративной инфраструктурой голосовой связи и PSTN или УАТС.</span><span class="sxs-lookup"><span data-stu-id="d8c39-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="d8c39-116">Шлюзы PSTN работают с сервером-посредником, чтобы представлять вызов по сети PSTN или УАТС в клиенте голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d8c39-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="d8c39-117">Сервер, на котором выводятся сведения о клиентах, также предоставляет шлюзу PSTN Услуги для маршрутизации в КТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="d8c39-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="d8c39-118">Список партнеров, работающих с корпорацией Майкрософт, для предоставления устройств, которые работают с Lync Server, можно найти на веб-сайте Microsoft [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Unified Communications Partners по адресу.</span><span class="sxs-lookup"><span data-stu-id="d8c39-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="d8c39-119">Станции УАТС</span><span class="sxs-lookup"><span data-stu-id="d8c39-119">Private Branch Exchanges</span></span>

<span data-ttu-id="d8c39-120">Если у вас есть существующая инфраструктура голосовой связи, использующая АТС, вы можете использовать телефонную сеть с голосовой связью Lync Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d8c39-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="d8c39-121">Поддерживаются следующие сценарии интеграции с корпоративной голосовой АТС.</span><span class="sxs-lookup"><span data-stu-id="d8c39-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="d8c39-122">IP-УАТС, поддерживающая обход мультимедиа, для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d8c39-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="d8c39-123">IP-УАТС, которой требуется изолированный шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="d8c39-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="d8c39-124">УАТС с временным мультиплексированием с изолированным шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d8c39-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8c39-125">Функция обхода сервера-посредника взаимодействует не со всеми шлюзами ТСОП, IP-PBX и пограничным контроллером SBC.</span><span class="sxs-lookup"><span data-stu-id="d8c39-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d8c39-126">Корпорация Майкрософт протестировала набор шлюзов ТСОП и контроллеров SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d8c39-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d8c39-127">Обход мультимедиа поддерживается только в том случае, если у вас есть продукты и версии, указанные в едином приложении <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>для взаимодействия с Open Communications — Lync Server на.</span><span class="sxs-lookup"><span data-stu-id="d8c39-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="d8c39-128">Подробные сведения о партнерах, предлагающих корпоративные решения для предприятий, можно найти на веб- [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)сайте Microsoft Unified Communications Partners по адресу.</span><span class="sxs-lookup"><span data-stu-id="d8c39-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="d8c39-129">Сведения о партнерах, предлагающих корпоративные аппаратные решения для предприятий, включая шлюзы PSTN, можно найти на веб [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)-сайте Microsoft Unified Communications Partner.</span><span class="sxs-lookup"><span data-stu-id="d8c39-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

