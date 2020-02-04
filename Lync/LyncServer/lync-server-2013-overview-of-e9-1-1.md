---
title: 'Lync Server 2013: обзор E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="97e40-102">Обзор E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e40-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97e40-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="97e40-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="97e40-104">Microsoft Lync Server 2013 поддерживает вызов улучшенных 9-1-1 (E9-1-1) на клиентах Lync и устройствах Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="97e40-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="97e40-105">Когда вы настраиваете Lync Server для E9-1-1, экстренные вызовы, размещенные в Lync 2013 или Lync Phone Edition, включают в себя сведения о местоположении ответа на аварийную информацию (ЕРЛ) из базы данных службы расположения.</span><span class="sxs-lookup"><span data-stu-id="97e40-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="97e40-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span><span class="sxs-lookup"><span data-stu-id="97e40-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="97e40-107">Когда пользователь осуществляет вызов экстренной помощи, Lync Server перенаправляет звук звонка, а также сведения о местоположении и ответном вызове, используя сервер-посредника для поставщика услуг E9 – 1-1.</span><span class="sxs-lookup"><span data-stu-id="97e40-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="97e40-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span><span class="sxs-lookup"><span data-stu-id="97e40-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="97e40-109">Lync Server поддерживает два способа маршрутизации экстренных вызовов в поставщик услуг E9-1-1:</span><span class="sxs-lookup"><span data-stu-id="97e40-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="97e40-110">Подключение через магистраль SIP к уполномоченному поставщику услуг E9-1-1</span><span class="sxs-lookup"><span data-stu-id="97e40-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="97e40-111">Шлюз ELIN к поставщику услуг E9-1-1 на основе ТСОП</span><span class="sxs-lookup"><span data-stu-id="97e40-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="97e40-112">При использовании провайдера услуг магистральной магистрали по протоколу SIP E9-1-1 необходимо добавить Ерлс в базу данных службы сведений о расположении, а затем проверить расположение в соответствии с основным адресом (МСАГ), поддерживаемым поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="97e40-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="97e40-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span><span class="sxs-lookup"><span data-stu-id="97e40-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="97e40-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span><span class="sxs-lookup"><span data-stu-id="97e40-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="97e40-115">В отличие от мультиплексирования деления времени (ТДМ) и VPN-телефонов, использующих ПРОТОКОЛы АТС с фиксированными расположениями, конечная точка Lync может быть на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="97e40-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="97e40-116">Когда вы развертываете функцию E9-1-1, Lync Server помогает убедиться в том, что в какой-то момент, если вызывающий объект находится в сети, вызов экстренной помощи может перенаправляться в ПСАП, который обслуживает расположение вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="97e40-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="97e40-117">Например, если главный офис пользователя расположен в городе Рэдмонд штата Вашингтон, но пользователь совершает звонок в экстренную службу с компьютера филиала, расположенного в городе Уичито штата Канзас, то поставщик услуг E9-1-1 на основе магистрали SIP или ТСОП перенаправит звонок в пункт реагирования общественной безопасности города Уичито, а не Рэдмонда.</span><span class="sxs-lookup"><span data-stu-id="97e40-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="97e40-118">При использовании шлюза Елин вы также добавляете Ерлс в базу данных службы сведений о расположении, но вы также включаете номер Елин для каждого места.</span><span class="sxs-lookup"><span data-stu-id="97e40-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="97e40-119">The ELIN number becomes the emergency calling number during the emergency call.</span><span class="sxs-lookup"><span data-stu-id="97e40-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="97e40-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span><span class="sxs-lookup"><span data-stu-id="97e40-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97e40-121">Устройства, подключенные к Lync, не могут получать сведения о расположении из службы сведений о расположении или передавать расположение поставщику услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="97e40-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="97e40-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span><span class="sxs-lookup"><span data-stu-id="97e40-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="97e40-123"><STRONG>Традиционный</STRONG>&nbsp;&nbsp;способ&nbsp;PS-Ali. Если у вас есть местные шлюзы PSTN на каждом сайте, на котором развернуты аналоговые телефоны, и каждый из аналоговых телефонов сделал это, вы можете подготовить расположение аналогового устройства непосредственно с помощью закрытого коммутатора/автоматического определения расположения (PS-Ali) поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="97e40-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="97e40-124">В этом случае вы настраиваете специально сконструированные политики голосовой связи Lync и назначаете их контактам из аналоговых объектов устройства, так что звонки E9-1-1 с этих телефонов перенаправляются напрямую по локальному шлюзу поставщику PSTN, который будет выполнять обслуживание сайта (вместо маршрутизации Звонок на телефонную магистраль поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="97e40-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="97e40-125">При размещении вызова экстренной службы номер каждого аналогового телефона для прямого соединения с внутренними абонентами сопоставляется с физическим местоположением по базе данных, расположенной у поставщика PS-ALI и связанной с магистралью ТСОП, после чего информация об этом местоположении передается в пункт реагирования общественной безопасности.</span><span class="sxs-lookup"><span data-stu-id="97e40-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="97e40-126">Эти записи должны обновляться у поставщика услуг PS-ALI при каждом перемещении телефонов в другие местоположения.</span><span class="sxs-lookup"><span data-stu-id="97e40-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="97e40-127"><STRONG>E9-1-1 (поставщик услуг)</STRONG>&nbsp;&nbsp;&nbsp;. Вы можете зарегистрировать аналоговые телефонные Дидс и соответствующие им Ерлс с помощью провайдера услуг E9-1-1, если он поддерживается поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="97e40-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="97e40-128">Если поставщик получает вызов с сервера Lync Server, который не содержит ПИДФ данных, поставщик может узнать, совпадает ли соответствие с базой данных на номере вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="97e40-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="97e40-129">С помощью сведений о местоположении чрезвычайной ситуации, полученных из своей базы данных, поставщик может автоматически маршрутизировать экстренный вызов в соответствующий пункт реагирования общественной безопасности, который в свою очередь получит номер для прямого соединения с внутренними абонентами аналогового устройства и запись ESQK, позволяющие диспетчеру найти местоположение звонящего.</span><span class="sxs-lookup"><span data-stu-id="97e40-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="97e40-p108">Если используется вариант со шлюзом ELIN и требуется поддержка E9-1-1 с аналоговых телефонов, администратор может предоставить сведений об аналоговых устройствах напрямую с помощью поставщика PS-ALI, как описано выше в первом варианте.</span><span class="sxs-lookup"><span data-stu-id="97e40-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="97e40-131">С точки зрения сервера Lync процесс E9-1-1 можно разделить на два этапа:</span><span class="sxs-lookup"><span data-stu-id="97e40-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="97e40-132">Этап 1: получение сведений о местоположении</span><span class="sxs-lookup"><span data-stu-id="97e40-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="97e40-133">Этап 2: маршрутизация экстренного вызова поставщику услуг E9-1-1</span><span class="sxs-lookup"><span data-stu-id="97e40-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="97e40-134">В данном разделе описано, как работают эти этапы.</span><span class="sxs-lookup"><span data-stu-id="97e40-134">This section describes how these stages work.</span></span>

<span data-ttu-id="97e40-135">Если планируется настроить инфраструктуру для автоматического обнаружения местоположения клиента, сначала необходимо решить, какие элементы сети будут использоваться для сопоставления расположений абонентов.</span><span class="sxs-lookup"><span data-stu-id="97e40-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="97e40-136">Подробнее об этих параметрах можно узнать [в разделе Определение сетевых элементов, используемых для определения расположения в Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="97e40-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97e40-137">Содержание</span><span class="sxs-lookup"><span data-stu-id="97e40-137">In This Section</span></span>

  - [<span data-ttu-id="97e40-138">Получение сведений о местоположении в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e40-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="97e40-139">Маршрутизация звонков E9-1-1 с использованием магистралей SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e40-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="97e40-140">Маршрутизация звонков E9-1-1 с использованием шлюза ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e40-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

