---
title: 'Lync Server 2013: обзор E9 – 1 – 1'
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
ms.openlocfilehash: 67a1f0a5e36b4905cab14fd0aa320d7c8f5c606c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="c8fa0-102">Общие сведения о E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8fa0-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8fa0-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c8fa0-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c8fa0-104">Microsoft Lync Server 2013 поддерживает вызовы расширенных 9-1-1 (E9-1-1) от клиентов Lync и устройств Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="c8fa0-105">При настройке Lync Server для E9-1-1 экстренные вызовы, размещенные в Lync 2013 или Lync Phone Edition, включают сведения о расположении аварийного ответа (пэр) из базы данных службы сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="c8fa0-106">Сведения о местоположении для экстренных служб включают официальный адрес (т. е. улицу) и другие сведения, которые помогают более точно определить местонахождение в офисных строениях и других помещениях, занимаемых несколькими арендаторами.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="c8fa0-107">Когда пользователь выполняет экстренные вызовы, Lync Server направляет звук звонка, а также сведения о расположении и ответном вызове через сервер-посредник к поставщику услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="c8fa0-108">Поставщик услуг E9-1-1 использует официальный адрес звонящего для маршрутизации звонка в пункт реагирования экстренной службы (PSAP), обслуживающий местоположение звонящего, и отправляет ключ запроса для экстренной службы (ESQK), который используется телефонным центром экстренной службы для определения сведений о местоположении звонящего.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="c8fa0-109">Lync Server поддерживает два метода для маршрутизации экстренных вызовов поставщику услуг E9 – 1 – 1:</span><span class="sxs-lookup"><span data-stu-id="c8fa0-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="c8fa0-110">Подключение через магистраль SIP к уполномоченному поставщику услуг E9-1-1</span><span class="sxs-lookup"><span data-stu-id="c8fa0-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="c8fa0-111">Шлюз ELIN к поставщику услуг E9-1-1 на основе ТСОП</span><span class="sxs-lookup"><span data-stu-id="c8fa0-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="c8fa0-112">При использовании поставщика услуг SIP магистральной E9-1-1 вы добавляете Erl в базу данных службы сведений о расположении, а затем проверяете расположения на соответствие главному руководству по адресам (MSAG), поддерживаемому поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="c8fa0-113">Если поставщик услуг E9-1-1 получает звонок, который не содержит сведений о местонахождении или содержит сведения, которые не были проверены на соответствие главному руководству по адресам, поставщик услуг E9-1-1 маршрутизирует звонок в телефонный центр экстренных служб национального или регионального уровня (ECRC), в котором работают специально обученные сотрудники, устно получающие сведения о местоположении от звонящего, если возможно, и вручную маршрутизирующие звонок в соответствующий пункт реагирования экстренной службы.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="c8fa0-114">(Некоторые поставщики услуг E9-1-1, работающие на основе магистрали SIP, также предоставляют клиентам номер для прямого соединения с внутренними абонентами ТСОП, маршрутизируемый в телефонный центр экстренных служб, что является альтернативным способом маршрутизации звонков 9-1-1, если магистраль SIP не работает по какой-либо причине.)</span><span class="sxs-lookup"><span data-stu-id="c8fa0-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="c8fa0-115">В отличие от мультиплексирования деления времени (TDM) и телефон УАТС с фиксированными расположениями, конечная точка Lync может быть очень мобильной.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="c8fa0-116">При развертывании компонента E9-1-1 Lync Server помогает убедиться, что в сети, где находится вызывающий абонент, неважно, что вызов может маршрутизироваться в PSAP, который обслуживает расположение вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="c8fa0-117">Например, если главный офис пользователя расположен в городе Рэдмонде штата Вашингтон, но пользователь совершает звонок в экстренную службу с компьютера филиала, расположенного в городе Уичито штата Канзас, то поставщик услуг E9-1-1 на основе магистрали SIP или ТСОП будет маршрутизировать звонок в пункт реагирования экстренной службы города Уичито, а не Рэдмонда.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="c8fa0-118">При использовании шлюза ELIN вы также добавляете Erl в базу данных службы сведений о расположении, но вы также включаете номер ELIN для каждого расположения.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="c8fa0-119">Номер ELIN становится номером для экстренных вызовов во время совершения звонков в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="c8fa0-120">После добавления сведений в базу данных администратор должен проверить, что поставщик ТСОП отправляет ELIN в базу данных автоматического определения местонахождения (ALI).</span><span class="sxs-lookup"><span data-stu-id="c8fa0-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8fa0-121">Аналоговые устройства, подключенные к Lync, не могут получать сведения о расположении от службы сведений о расположении или расположения для передачи поставщику услуг E9 – 1 – 1.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="c8fa0-122">Если используется поставщик услуг E9-1-1, работающий через магистраль SIP, и требуется поддержка E9-1-1 на аналоговых телефонах, есть два варианта действий:</span><span class="sxs-lookup"><span data-stu-id="c8fa0-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c8fa0-123"><STRONG>Традиционный</STRONG>&nbsp;&nbsp;вариант&nbsp;PS-Ali если у вас есть локальные шлюзы PSTN на каждом сайте, где развернуты аналоговые телефоны и у каждого аналогового телефона есть, то расположение аналогового устройства можно предоставить непосредственно с помощью поставщика услуг частного коммутатора или кода автоматического определения расположения (PS-Ali).</span><span class="sxs-lookup"><span data-stu-id="c8fa0-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="c8fa0-124">В этом случае администратор настраивает специальные политики голосовой связи Lync и назначает их объектам контактов аналоговых устройств, чтобы звонки E9-1-1 с этих телефонов маршрутизировались напрямую через локальный шлюз поставщику ТСОП, обслуживающему офис (вместо маршрутизации звонка в магистраль SIP поставщика услуг E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="c8fa0-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="c8fa0-125">Когда совершается звонок в экстренную службу, база данных у поставщика PS-ALI, связанная с магистралью ТСОП, сопоставляет номер для прямого соединения с внутренними абонентами каждого аналогового телефона с физическим местоположением и предоставляет это местоположение в пункт реагирования экстренной службы.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="c8fa0-126">Эти записи должны обновляться у поставщика услуг PS-ALI каждый раз при перемещении телефонов в другие местоположения.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="c8fa0-127"><STRONG>E9-1-1 поставщик</STRONG>&nbsp;&nbsp;&nbsp;услуг вы можете зарегистрировать аналоговое телефонное номера и соответствующие Erl в поставщике услуг E9-1-1, если он поддерживается поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="c8fa0-128">Если поставщик получает вызов с сервера Lync Server, который не содержит данные PIDF, поставщик может проверить, есть ли в номере вызываемого абонента согласованность базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="c8fa0-129">С помощью сведений о местоположении для экстренных служб, полученных из своей базы данных, поставщик может автоматически маршрутизировать экстренный вызов в соответствующий пункт реагирования экстренной службы, который в свою очередь получит номер для прямого соединения с внутренними абонентами аналогового устройства и запись ESQK, позволяющие диспетчеру найти местоположение звонящего.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="c8fa0-p108">Если используется вариант со шлюзом ELIN и требуется поддержка E9-1-1 с аналоговых телефонов, администратор может предоставить сведений об аналоговых устройствах напрямую с помощью поставщика PS-ALI, как описано выше в первом варианте.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="c8fa0-131">С точки зрения сервера Lync процесс E9 – 1 – 1 можно разделить на два этапа:</span><span class="sxs-lookup"><span data-stu-id="c8fa0-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="c8fa0-132">Этап 1: получение сведений о местоположении</span><span class="sxs-lookup"><span data-stu-id="c8fa0-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="c8fa0-133">Этап 2: маршрутизация экстренного вызова поставщику услуг E9-1-1</span><span class="sxs-lookup"><span data-stu-id="c8fa0-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="c8fa0-134">В данном разделе описано, как работают эти этапы.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-134">This section describes how these stages work.</span></span>

<span data-ttu-id="c8fa0-135">Если планируется настроить инфраструктуру для автоматического детектирования местоположения клиента, сначала необходимо решить, какие элементы сети будут использоваться для сопоставления местоположений звонящих.</span><span class="sxs-lookup"><span data-stu-id="c8fa0-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="c8fa0-136">Дополнительные сведения о возможных параметрах приведены [в статье Определение сетевых элементов, используемых для определения расположения в Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="c8fa0-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8fa0-137">Содержание</span><span class="sxs-lookup"><span data-stu-id="c8fa0-137">In This Section</span></span>

  - [<span data-ttu-id="c8fa0-138">Получение расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8fa0-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="c8fa0-139">Маршрутизация вызовов E9 – 1 – 1 с помощью магистральной линии SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8fa0-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="c8fa0-140">Маршрутизация вызовов E9 – 1 – 1 с помощью шлюза ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8fa0-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

