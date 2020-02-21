---
title: 'Lync Server 2013: компоненты VoIP сервера переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 762b7a43343e10fe4d6bec601954474ba3a44b90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="87fff-102">Компоненты VoIP сервера переднего плана для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87fff-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87fff-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="87fff-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="87fff-104">Ниже приведены компоненты VoIP, расположенные на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="87fff-105">служба перевода;</span><span class="sxs-lookup"><span data-stu-id="87fff-105">Translation Service</span></span>

  - <span data-ttu-id="87fff-106">компонент маршрутизации входящих вызовов;</span><span class="sxs-lookup"><span data-stu-id="87fff-106">Inbound Routing component</span></span>

  - <span data-ttu-id="87fff-107">компонент маршрутизации исходящих вызовов;</span><span class="sxs-lookup"><span data-stu-id="87fff-107">Outbound Routing component</span></span>

  - <span data-ttu-id="87fff-108">компонент маршрутизации единой системы обмена сообщениями Exchange;</span><span class="sxs-lookup"><span data-stu-id="87fff-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="87fff-109">компонент маршрутизации между кластерами.</span><span class="sxs-lookup"><span data-stu-id="87fff-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="87fff-110">Компонент сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87fff-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="87fff-111">Служба перевода</span><span class="sxs-lookup"><span data-stu-id="87fff-111">Translation Service</span></span>

<span data-ttu-id="87fff-p101">Служба перевода — это серверный компонент, который отвечает за преобразование набираемого номера в формат E.164 или другой формат согласно правилам нормализации, определенным администратором. Служба перевода может преобразовывать номера и в другие форматы, не только E.164, если ваша организация использует частную систему нумерации или шлюз или УАТС, которые не поддерживают формат E.164.</span><span class="sxs-lookup"><span data-stu-id="87fff-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="87fff-114">Компонент маршрутизации входящих пакетов</span><span class="sxs-lookup"><span data-stu-id="87fff-114">Inbound Routing Component</span></span>

<span data-ttu-id="87fff-115">Компонент маршрутизации входящих вызовов обрабатывает входящие вызовы в основном в соответствии с предпочтениями, указанными пользователями для клиентов корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="87fff-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="87fff-116">Он также осуществляет делегированные и одновременные звонки, если они настроены пользователем.</span><span class="sxs-lookup"><span data-stu-id="87fff-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="87fff-117">Например, пользователи указывают, переадресуются ли неотвеченные вызовы или просто записываются в журнал.</span><span class="sxs-lookup"><span data-stu-id="87fff-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="87fff-118">Если переадресация вызовов включена, пользователи могут указать, следует ли перенаправлять неотвеченные звонки на другой номер или на сервер единой системы обмена сообщениями Exchange, настроенный на предоставление ответа на вызовы.</span><span class="sxs-lookup"><span data-stu-id="87fff-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="87fff-119">Компонент маршрутизации входящих подключений устанавливается по умолчанию на всех серверах Standard Edition и серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="87fff-120">Компонент маршрутизации исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="87fff-120">Outbound Routing Component</span></span>

<span data-ttu-id="87fff-121">Компонент маршрутизации исходящих вызовов направляет вызовы на УАТС или ТСОП.</span><span class="sxs-lookup"><span data-stu-id="87fff-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="87fff-122">Он применяет правила авторизации звонков, заданные политикой голосовой связи пользователя, к вызывающим абонентам и определяет оптимальный шлюз ТСОП для маршрутизации каждого звонка.</span><span class="sxs-lookup"><span data-stu-id="87fff-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="87fff-123">Компонент маршрутизации исходящих подключений устанавливается по умолчанию на всех серверах Standard Edition и серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="87fff-124">Логика маршрутизации, используемая компонентом маршрутизации исходящих вызовов, в значительной степени настраивается сетью или администраторами телефонной связи в соответствии с требованиями организации.</span><span class="sxs-lookup"><span data-stu-id="87fff-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="87fff-125">Компонент маршрутизации единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="87fff-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="87fff-126">Компонент маршрутизации единой системы обмена сообщениями Exchange обрабатывает маршрутизацию между Lync Server и серверами единой системы обмена сообщениями Exchange, чтобы интегрировать Lync Server с функциями единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="87fff-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="87fff-127">Компонент маршрутизации единой системы обмена сообщениями Exchange также обрабатывает перенаправление голосовой почты по протоколу PSTN, если серверы единой системы обмена сообщениями недоступны.</span><span class="sxs-lookup"><span data-stu-id="87fff-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="87fff-128">При наличии пользователей корпоративной голосовой связи на сайтах филиалов, которые не имеют отказоустойчивой глобальной сети на центральном сайте, устройство для обеспечения связи в филиалах, которое развертывается на сайте филиала, обеспечивает бесперебойность голосовой почты для пользователей филиала во время сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="87fff-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="87fff-129">При нарушении WAN-соединения для обеспечения связи в филиалах выполняется следующее:</span><span class="sxs-lookup"><span data-stu-id="87fff-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="87fff-130">переадресует неотвеченные вызовы по ТСОП на сервер единой системы обмена сообщениями Exchange в центральном узле;</span><span class="sxs-lookup"><span data-stu-id="87fff-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="87fff-131">обеспечивает пользователю возможность получения сообщений голосовой почты через ТСОП;</span><span class="sxs-lookup"><span data-stu-id="87fff-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="87fff-132">ставит в очередь уведомления о пропущенных звонках, а затем загружает их на сервер единой системы обмена сообщениями Exchange при восстановлении канала глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="87fff-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="87fff-133">Чтобы включить переадресацию голосовой почты, мы рекомендуем администратору Exchange настроить автосекретарь единой системы обмена сообщениями Exchange для приема только сообщений.</span><span class="sxs-lookup"><span data-stu-id="87fff-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="87fff-134">Подробнее об этих функциях можно узнать [в статье Планирование интеграции единой системы обмена сообщениями Exchange в Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) и [Планирование устойчивости корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)соответственно.</span><span class="sxs-lookup"><span data-stu-id="87fff-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="87fff-135">Компонент маршрутизации между кластерами</span><span class="sxs-lookup"><span data-stu-id="87fff-135">Intercluster Routing Component</span></span>

<span data-ttu-id="87fff-p105">Компонент маршрутизации между кластерами отвечает за маршрутизацию вызовов в основном пуле регистраторов вызываемого абонента. Если это недоступно, компонент перенаправляет вызов на резервный пул регистраторов. Если основной и резервный пулы регистраторов недоступны по сети IP, компонент маршрутизации между кластерами переадресует вызов по ТСОП на номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="87fff-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="87fff-139">Другие компоненты интерфейсных серверов, необходимые для VoIP</span><span class="sxs-lookup"><span data-stu-id="87fff-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="87fff-140">Другие компоненты, размещенные на сервере переднего плана или в директоре, которые обеспечивают важную поддержку VoIP, но сами не являются компонентами VoIP, включают следующее:</span><span class="sxs-lookup"><span data-stu-id="87fff-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="87fff-141">**Пользовательские службы.**</span><span class="sxs-lookup"><span data-stu-id="87fff-141">**User Services.**</span></span> <span data-ttu-id="87fff-142">Выполняют поиск обратного номера для целевого телефонного номера каждого входящего вызова и сопоставляют этот номер с SIP URI конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="87fff-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="87fff-143">С помощью этой информации компонент маршрутизации входящих вызовов направляет вызов зарегистрированным конечным точкам SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="87fff-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="87fff-144">Пользовательские службы — это основной компонент на всех серверах и директорах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="87fff-145">**Репликатор пользователей.**</span><span class="sxs-lookup"><span data-stu-id="87fff-145">**User Replicator.**</span></span> <span data-ttu-id="87fff-146">Извлекает телефонные номера пользователей из доменных служб Active Directory и записывает их в таблицы в базе данных RTC, где они доступны для пользовательских служб и сервера адресной книги.</span><span class="sxs-lookup"><span data-stu-id="87fff-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="87fff-147">Репликатор пользователей — это основной компонент на всех серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="87fff-148">**Сервер адресной книги.**</span><span class="sxs-lookup"><span data-stu-id="87fff-148">**Address Book Server.**</span></span> <span data-ttu-id="87fff-149">Предоставляет глобальные сведения о списке адресов из доменных служб Active Directory клиентам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87fff-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="87fff-150">Он также получает сведения о пользователях и контактных данных из базы данных RTC, записывает их в файлы адресной книги, а затем сохраняет файлы в общей папке, в которой они загружаются клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="87fff-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="87fff-151">Сервер адресной книги записывает сведения в базу данных RTCAb, которая используется службой веб-запросов адресной книги для ответа на поисковые запросы пользователей из Microsoft Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="87fff-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="87fff-152">При необходимости она нормализует номера телефонов пользователей, которые записываются в базу данных RTC для подготовки пользовательских контактов в Lync.</span><span class="sxs-lookup"><span data-stu-id="87fff-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="87fff-153">Служба адресной книги устанавливается по умолчанию на всех серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="87fff-154">Служба веб-запросов адресной книги устанавливается по умолчанию вместе с веб-службами на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="87fff-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

