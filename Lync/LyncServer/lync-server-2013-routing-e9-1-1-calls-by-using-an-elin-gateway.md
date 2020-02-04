---
title: 'Lync Server 2013: маршрутизация звонков E9-1-1 с использованием шлюза ELIN'
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
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="8058b-102">Маршрутизация звонков E9-1-1 с использованием шлюза ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8058b-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8058b-103">_**Тема последнего изменения:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="8058b-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="8058b-104">Некоторые партнеры по программе открытого взаимодействия для объединенных коммуникаций Майкрософт предоставляют шлюзы, поддерживающие номера ELIN, которые могут служить альтернативой магистральной линии SIP до поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8058b-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="8058b-105">Шлюзы ELIN поддерживают подключения ISDN и CAMA к службам E9-1-1 в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8058b-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="8058b-106">Подробные сведения о партнерах, которые предоставляют Елин шлюзы и ссылки на документацию [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425), можно найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="8058b-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="8058b-107">Как и подключения по магистралям SIP к поставщикам услуг E9-1-1, шлюзы ELIN также предоставляют способы маршрутизации экстренных вызовов в приемлемый для вызывающего абонента пункт реагирования общественной безопасности, однако эти шлюзы используют ELIN в качестве идентификатора расположения.</span><span class="sxs-lookup"><span data-stu-id="8058b-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="8058b-108">Вы определяете Елинс для каждого местоположения реагирования на чрезвычайные ситуации (ЕРЛ) в вашей организации (подробные сведения можно найти в разделе [Управление расположениями Елин шлюзов в Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="8058b-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="8058b-109">При использовании шлюза Елин для экстренных вызовов используется та же инфраструктура Lync Server E9-1-1, которую можно использовать для подключения к магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="8058b-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="8058b-110">Это значит, что база данных службы сведений о расположении предоставляет расположение для клиента Lync Server, а политика расположения включает функцию и определяет маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="8058b-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="8058b-111">Тем не менее, с шлюзом Елин необходимо добавить Елинс в базу данных службы сведений о расположении и получить их в базу данных автоматического определения расположения (ALI).</span><span class="sxs-lookup"><span data-stu-id="8058b-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="8058b-112">Когда клиент Lync получает свое расположение из службы сведений о расположении, это расположение включает Елин.</span><span class="sxs-lookup"><span data-stu-id="8058b-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="8058b-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span><span class="sxs-lookup"><span data-stu-id="8058b-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="8058b-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span><span class="sxs-lookup"><span data-stu-id="8058b-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="8058b-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span><span class="sxs-lookup"><span data-stu-id="8058b-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="8058b-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span><span class="sxs-lookup"><span data-stu-id="8058b-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="8058b-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span><span class="sxs-lookup"><span data-stu-id="8058b-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="8058b-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span><span class="sxs-lookup"><span data-stu-id="8058b-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="8058b-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span><span class="sxs-lookup"><span data-stu-id="8058b-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="8058b-120">Шлюзы ELIN поддерживают экстренные вызовы только из сети организации.</span><span class="sxs-lookup"><span data-stu-id="8058b-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="8058b-121">Если экстренный вызов выполнен из-за пределов сети, шлюз его не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="8058b-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8058b-122">Подробнее об использовании магистрального подключения SIP для вызова экстренной помощи можно найти <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">в разделе Маршрутизация E9-1-1 звонков с помощью магистральной МАГИСТРАЛИ SIP в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8058b-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8058b-123">На приведенной ниже схеме показано, как с Lync Server перенаправляется вызов экстренной помощи в ПСАП при использовании шлюза Елин.</span><span class="sxs-lookup"><span data-stu-id="8058b-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="8058b-124">**Маршрутизация вызовов E9-1-1 с помощью шлюза ELIN**</span><span class="sxs-lookup"><span data-stu-id="8058b-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="8058b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="8058b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="8058b-126">ПРИГЛАШЕНИЕ на SIP, содержащее расположение, номер обратного вызова вызывающего абонента и (необязательно) URL-адрес уведомления и номер обратного вызова конференции пересылается на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8058b-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="8058b-127">Lync Server соответствует номеру для экстренного реагирования и перенаправляет звонок (на основе значения **использования PSTN** , определенного в соответствующей политике расположения) на сервер-посредник и из него на шлюзе Елин.</span><span class="sxs-lookup"><span data-stu-id="8058b-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="8058b-128">Шлюз ELIN маршрутизирует вызов через магистраль ISDN или CAMA в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8058b-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="8058b-p106">ТСОП определяет вызов как экстренный и маршрутизирует его на селекторный маршрутизатор E9-1-1 в своей сети. Селекторный маршрутизатор E9-1-1 проверяет номер вызывающего абонента по базе данных ALI для получения географического расположения. Селекторный маршрутизатор E9-1-1 отправляет вызов на подходящий пункт реагирования на основе сведений о расположении, полученных из базы данных ALI. </span><span class="sxs-lookup"><span data-stu-id="8058b-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="8058b-132">Если вы настроили политику расположения для уведомлений, то один или несколько руководителей Организации отправили мгновенное сообщение Lync с помощью специального уведомления.</span><span class="sxs-lookup"><span data-stu-id="8058b-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="8058b-133">Это сообщение всегда появляется на экране руководителей системы безопасности и включает имя вызывающего абонента, номер телефона, время и место, позволяя персоналу безопасности быстро реагировать на него с помощью мгновенного сообщения или голосового звонка.</span><span class="sxs-lookup"><span data-stu-id="8058b-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="8058b-p108">Если вызов прерывается раньше времени, пункт реагирования использует номер ELIN для прямой связи с вызывавшим абонентом. Шлюз ELIN заменяет номер ELIN на прямой входной номер абонента.</span><span class="sxs-lookup"><span data-stu-id="8058b-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

