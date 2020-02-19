---
title: Просмотр серверных приложений Microsoft SIP Processing Language (MSPL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb195ee5826cbb63f7fc718a038761f10199135
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="05297-102">Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05297-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05297-103">_**Последнее изменение темы:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="05297-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="05297-104">Серверное приложение Microsoft SIP Processing Language (MSPL) — это приложение с поддержкой скриптов, использующее язык сценариев вместо API Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="05297-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="05297-105">MSPL обеспечивает более точное управление фильтрацией и поведением прокси-серверов, а также упрощает передачу сообщений в приложения SIP на основе транзакций.</span><span class="sxs-lookup"><span data-stu-id="05297-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="05297-106">В частности, MSPL используется для фильтрации и маршрутизации сообщений SIP.</span><span class="sxs-lookup"><span data-stu-id="05297-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="05297-107">Приложения MSPL выполняются в том же процессе, что и модуль UserServices, в то время как программа, основанная на API Lync 2010, работает в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="05297-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="05297-108">Вы можете использовать страницу **серверное приложение** в группе **топология** на панели управления Lync Server, чтобы просмотреть список серверных приложений MSPL, работающих на серверах переднего плана в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05297-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="05297-109">В этом списке перечислены сценарии, доступные для каждого пула, а также содержатся сведения об их состоянии (включены или выключены).</span><span class="sxs-lookup"><span data-stu-id="05297-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="05297-110">Сценарии запускаются в том порядке, в котором они указаны в списке.</span><span class="sxs-lookup"><span data-stu-id="05297-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="05297-111">Сценарии содержат следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="05297-111">These scripts include the following:</span></span>

  - <span data-ttu-id="05297-p103">ClientVersionFilter позволяет администратору указывать версии клиентов, поддерживаемые пулом. Фильтр версий клиентов проверяет версию клиента и на основании полученных данных может запретить вход или показать пользователю сообщение об использовании неподдерживаемой версии клиента. В это сообщение можно добавить URL-адрес для загрузки последней версии клиента.</span><span class="sxs-lookup"><span data-stu-id="05297-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="05297-115">TranslationService преобразует номера, вводимые пользователем, в формат E.164 в соответствии с правилами нормализации, заданными администратором.</span><span class="sxs-lookup"><span data-stu-id="05297-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="05297-116">Дополнительные сведения см. [в разделе правила преобразования в Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="05297-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="05297-117">IncomingFederation выполняет принудительную проверку клиентской федерации для межклиентских сообщений и входящих сообщений из внешних развертываний.</span><span class="sxs-lookup"><span data-stu-id="05297-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="05297-p105">UserServices — это регистратор SIP, компонент сведений о присутствии и конференций сервера переднего плана. Он предоставляет интегрированные функции обмена мгновенными сообщениями, сведений о присутствии и конференций, созданные на основе прокси-сервера SIP.</span><span class="sxs-lookup"><span data-stu-id="05297-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="05297-120">InterClusterRouting отвечает за маршрутизацию звонков в основной пул регистратора вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="05297-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="05297-121">Дополнительные сведения: [компоненты VoIP сервера переднего плана для Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="05297-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="05297-122">IIMFilter (интеллектуальный фильтр мгновенных сообщений) блокирует сообщения, которые содержат URL-адреса или могут использоваться для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="05297-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="05297-123">IIMFilter также проверяет версию клиента от имени сервера.</span><span class="sxs-lookup"><span data-stu-id="05297-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="05297-124">Иимфилтер влияет на передачу файлов, инициированных либо с помощью Lync Server, либо с помощью Communicator.</span><span class="sxs-lookup"><span data-stu-id="05297-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="05297-125">По умолчанию для отключения ссылок перед первой буквой ссылки добавляется символ подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="05297-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="05297-126">Администратор может настроить сервер для блокировки передачи сообщений, которые содержат URL-адреса или пытаются передать файлы.</span><span class="sxs-lookup"><span data-stu-id="05297-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="05297-127">Иимфилтер устанавливается на все серверы, на которых работает Lync Server, кроме прокси-серверов и серверов архивации.</span><span class="sxs-lookup"><span data-stu-id="05297-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="05297-128">UserPinService используется для проверки ПИН-кодов пользователей, используемых в конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="05297-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="05297-129">Дефаултраутинг — это приложение маршрутизации по умолчанию для серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05297-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="05297-130">Это приложение включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05297-130">It is enabled by default.</span></span> <span data-ttu-id="05297-131">Приложение маршрутизации устанавливается на все серверы Standard Edition и Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="05297-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="05297-p109">ExumRouting перенаправляет звонки на сервер единой системы обмена сообщениями Exchange Server. ExumRouting определяет подходящий сервер единой системы обмена сообщениями Exchange для маршрутизации звонка при наличии нового сообщения голосовой почты. ExumRouting также обеспечивает некоторые аспекты интеграции единой системы обмена сообщениями Exchange, включая маршрутизацию вызовов автосекретаря и абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="05297-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="05297-p110">OutboundRouting определяет шлюз, который перенаправляет звонок на номер телефона в соответствии с набранным номером и авторизацией набора номера пользователя. OutboundRouting также обрабатывает переадресацию звонков, если шлюзу не удается обработать звонок.</span><span class="sxs-lookup"><span data-stu-id="05297-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="05297-137">QoEAgent получает отчеты о качестве взаимодействия (QoE) от конечных точек с помощью запросов SIP SERVICE и отправляет данные в конечную очередь на сервер мониторинга или сторонним клиентам с помощью метода HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="05297-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="05297-138">Дополнительные сведения см [в разделе Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="05297-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="05297-139">OutgoingFederation выполняет принудительную проверку клиентской федерации для сообщений внешнего развертывания.</span><span class="sxs-lookup"><span data-stu-id="05297-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="05297-140">AcpRouting перенаправляет запросы INVITE, предназначенные для поставщика услуг аудиоконференций, на шлюз поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="05297-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="05297-141">На пограничных серверах запускаются следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="05297-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="05297-142">иимфилтер</span><span class="sxs-lookup"><span data-stu-id="05297-142">IIMFilter</span></span>

  - <span data-ttu-id="05297-143">OptionsHandler отправляет ответы **200 OK** на входящие запросы OPTIONS, если запрос предназначен для текущего сервера.</span><span class="sxs-lookup"><span data-stu-id="05297-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="05297-144">Эти запросы используются для проверки топологии.</span><span class="sxs-lookup"><span data-stu-id="05297-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="05297-145">См. также</span><span class="sxs-lookup"><span data-stu-id="05297-145">See Also</span></span>


[<span data-ttu-id="05297-146">Включение и отключение серверного приложения Microsoft SIP Processing Language (MSPL) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05297-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="05297-147">Помечает приложение Microsoft SIP Process Language (MSPL) как критическое или некритическое в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05297-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

