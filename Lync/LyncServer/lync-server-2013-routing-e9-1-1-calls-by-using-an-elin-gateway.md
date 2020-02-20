---
title: 'Lync Server 2013: Маршрутизация вызовов E9 – 1 – 1 с помощью шлюза ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e2e3bf94175f2f0ec3f4f7528cc969fe19529c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="2580d-102">Маршрутизация вызовов E9 – 1 – 1 с помощью шлюза ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2580d-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2580d-103">_**Последнее изменение темы:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="2580d-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="2580d-104">Некоторые партнеры по программе открытого взаимодействия для объединенных коммуникаций Майкрософт предоставляют шлюзы, поддерживающие номера ELIN, которые могут служить альтернативой магистральной линии SIP до поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2580d-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="2580d-105">Шлюзы ELIN поддерживают подключения ISDN и CAMA к службам E9-1-1 в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="2580d-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="2580d-106">Сведения о партнерах, предоставляющих шлюзы ELIN и ссылки на документацию, [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425)можно узнать в статье.</span><span class="sxs-lookup"><span data-stu-id="2580d-106">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="2580d-107">Подобно магистральным подключениям SIP к поставщикам услуг E9-1-1, шлюзы ELIN также предоставляют средства для маршрутизации экстренных вызовов в наиболее подходящий общедоступную точку безопасности ответа вызывающего абонента (PSAP), но эти шлюзы используют ELIN в качестве идентификатора расположения.</span><span class="sxs-lookup"><span data-stu-id="2580d-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="2580d-108">Вы определяете Elin для каждого местоположения аварийного реагирования (пэр) в Организации (Дополнительные сведения см. [в статье Управление расположениями для ШЛЮЗОВ Elin в Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="2580d-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="2580d-109">При использовании шлюза ELIN для экстренных вызовов используется та же инфраструктура Lync Server E9 – 1, которая используется для подключения к магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="2580d-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="2580d-110">То есть, база данных службы сведений о местоположении предоставляет расположение для клиента Lync Server, а политика расположения включает функцию и определяет маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="2580d-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="2580d-111">Тем не менее, с шлюзом ELIN необходимо добавить Elin в базу данных службы сведений о расположении и помещать его в базу данных автоматического определения расположения (ALI).</span><span class="sxs-lookup"><span data-stu-id="2580d-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="2580d-112">Когда клиент Lync получает свое расположение из службы сведений о местоположении, расположение включает ELIN.</span><span class="sxs-lookup"><span data-stu-id="2580d-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="2580d-113">Во время экстренного вызова номер ELIN включается в расположение, отправляемое на шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="2580d-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="2580d-114">Шлюз ELIN определяет вызов как экстренный и заменяет номер вызывающей стороны на номер ELIN.</span><span class="sxs-lookup"><span data-stu-id="2580d-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="2580d-115">Затем шлюз ELIN маршрутизирует вызов, используя номер ELIN как номер вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="2580d-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="2580d-116">Поставщик E9-1-1 в ТСОП проверяет номер ELIN по базе данных ALI, которая является сопроводительной базой данных по отношению к базе данных MSAG.</span><span class="sxs-lookup"><span data-stu-id="2580d-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="2580d-117">Затем ТСОП передает вызов на подходящий пункт реагирования, основываясь на результатах, возвращенных базой данных ALI, а пункт реагирования отправляет первые пакеты в расположение вызывающего абонента также по результатам опроса базы данных ALI.</span><span class="sxs-lookup"><span data-stu-id="2580d-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="2580d-118">Вызывающий номер кэшируется на шлюзе ELIN в течение предварительно заданного времени для приема обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="2580d-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="2580d-119">Во время обратного вызова пункт реагирования вызывает шлюз ELIN, который меняет номер ELIN на прямой входной номер абонента.</span><span class="sxs-lookup"><span data-stu-id="2580d-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="2580d-120">Шлюзы ELIN поддерживают экстренные вызовы только из сети организации.</span><span class="sxs-lookup"><span data-stu-id="2580d-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="2580d-121">Если экстренный вызов выполнен из-за пределов сети, шлюз его не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="2580d-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2580d-122">Для получения дополнительных сведений об использовании магистрального подключения SIP для экстренных вызовов, обратитесь к разделу <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Маршрутизация вызовов E9 – 1 – 1 с помощью МАГИСТРАЛИ SIP в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2580d-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2580d-123">На следующей схеме показано, как экстренные вызовы направляются из Lync Server в PSAP при использовании шлюза ELIN.</span><span class="sxs-lookup"><span data-stu-id="2580d-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="2580d-124">**Маршрутизация вызовов E9-1-1 с помощью шлюза ELIN**</span><span class="sxs-lookup"><span data-stu-id="2580d-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="2580d-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="2580d-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="2580d-126">ПРИГЛАШЕНИЕ SIP, содержащее расположение, номер обратного вызова вызывающего абонента, и URL-адрес уведомления (необязательно) и номер обратного вызова конференции направляются на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2580d-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="2580d-127">Lync Server соответствует номеру для экстренного реагирования, а затем направляет вызов (на основе значения **использования PSTN** , определенного в соответствующей политике расположения) на сервер-посредник и из него в шлюз Elin.</span><span class="sxs-lookup"><span data-stu-id="2580d-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="2580d-128">Шлюз ELIN маршрутизирует вызов через магистраль ISDN или CAMA в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="2580d-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="2580d-p106">ТСОП определяет вызов как экстренный и маршрутизирует его на селекторный маршрутизатор E9-1-1 в своей сети. Селекторный маршрутизатор E9-1-1 проверяет номер вызывающего абонента по базе данных ALI для получения географического расположения. Селекторный маршрутизатор E9-1-1 отправляет вызов на подходящий пункт реагирования на основе сведений о расположении, полученных из базы данных ALI.</span><span class="sxs-lookup"><span data-stu-id="2580d-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="2580d-132">Если вы настроили политику расположения для уведомлений, одному или нескольким должностным лицам Организации по обеспечению безопасности отправляется специальное мгновенное сообщение Lync.</span><span class="sxs-lookup"><span data-stu-id="2580d-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="2580d-133">Это сообщение всегда выводится на экран руководителей безопасности и содержит имя звонящего, номер телефона, время и расположение, позволяя сотрудникам системы безопасности быстро реагировать на вызывающий абонент с помощью мгновенного сообщения или голоса.</span><span class="sxs-lookup"><span data-stu-id="2580d-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="2580d-p108">Если вызов прерывается раньше времени, пункт реагирования использует номер ELIN для прямой связи с вызывавшим абонентом. Шлюз ELIN заменяет номер ELIN на прямой входной номер абонента.</span><span class="sxs-lookup"><span data-stu-id="2580d-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

