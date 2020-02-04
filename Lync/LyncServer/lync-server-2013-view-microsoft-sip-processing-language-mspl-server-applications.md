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
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="474ee-102">Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474ee-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="474ee-103">_**Тема последнего изменения:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="474ee-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="474ee-104">Серверное приложение Microsoft SIP Language (МСПЛ) — это приложение только для сценария, использующее язык сценариев вместо Microsoft Lync 2010 API.</span><span class="sxs-lookup"><span data-stu-id="474ee-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="474ee-105">МСПЛ обеспечивает более детальное Управление фильтрацией и поведением прокси-сервера в дополнение к средству для отправки определенных сообщений в приложения SIP, основанные на транзакциях.</span><span class="sxs-lookup"><span data-stu-id="474ee-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="474ee-106">МСПЛ используется специально для фильтрации и маршрутизации сообщений SIP.</span><span class="sxs-lookup"><span data-stu-id="474ee-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="474ee-107">МСПЛ приложения выполняются в том же процессе, что и модуль Усерсервицес, в то время как программа, основанная на API Lync 2010, работает в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="474ee-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="474ee-108">Вы можете использовать страницу **серверного приложения** в группе **топология** на панели управления Lync Server, чтобы просмотреть список серверных приложений мспл, которые работают на серверах переднего плана в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="474ee-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="474ee-109">Список содержит сценарии, доступные для каждого пула, а также сведения о том, включены ли они.</span><span class="sxs-lookup"><span data-stu-id="474ee-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="474ee-110">Сценарии выполняются в том порядке, в котором они указаны.</span><span class="sxs-lookup"><span data-stu-id="474ee-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="474ee-111">К этим сценариям относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="474ee-111">These scripts include the following:</span></span>

  - <span data-ttu-id="474ee-112">Клиентверсионфилтер предоставляет администратору способ указать версию клиентов, которые поддерживаются пулом.</span><span class="sxs-lookup"><span data-stu-id="474ee-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="474ee-113">Фильтр клиентской версии проверяет версию клиента и может либо не допустить вход в систему, либо предоставить пользователю сообщение о том, что он использует неподдерживаемый клиент.</span><span class="sxs-lookup"><span data-stu-id="474ee-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="474ee-114">Кроме того, фильтр клиентской версии можно настроить так, чтобы в нем отображалось сообщение пользователя, содержащее URL-адрес последней загружаемой версии клиента.</span><span class="sxs-lookup"><span data-stu-id="474ee-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="474ee-115">Транслатионсервице переводит число, которое пользователь набирает на номер E. 164 в соответствии с правилами нормализации, определенными администратором.</span><span class="sxs-lookup"><span data-stu-id="474ee-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="474ee-116">Подробные сведения можно найти [в разделе правила перевода в Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="474ee-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="474ee-117">Инкомингфедератион применяет проверку Федерации на уровне клиента для взаимодействия с клиентами и входящими сообщениями из внешних развертываний.</span><span class="sxs-lookup"><span data-stu-id="474ee-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="474ee-118">Усерсервицес — компонент регистратора SIP, присутствие и конференц-связь на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="474ee-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="474ee-119">Она предоставляет тесно интегрированные возможности обмена мгновенными сообщениями, сведения о присутствии и конференции, созданные на основе прокси-сервера SIP.</span><span class="sxs-lookup"><span data-stu-id="474ee-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="474ee-120">Интерклустерраутинг отвечает за маршрутизацию звонков в основной пул регистраторов вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="474ee-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="474ee-121">Дополнительные сведения можно найти в разделе [компонент VoIP сервера переднего плана для Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="474ee-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="474ee-122">Иимфилтер (интеллектуальный фильтр мгновенных сообщений) блокирует сообщения, которые содержат URL-адреса, которые можно щелкнуть, или пытаются начать передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="474ee-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="474ee-123">Иимфилтер также проверяет версию клиента от имени сервера.</span><span class="sxs-lookup"><span data-stu-id="474ee-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="474ee-124">Иимфилтер влияет на передачу файлов, которые инициируются либо с помощью Lync Server, либо из Communicator.</span><span class="sxs-lookup"><span data-stu-id="474ee-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="474ee-125">По умолчанию ссылки, которые можно щелкать, не добавляются путем добавления символа подчеркивания перед первым символом ссылки.</span><span class="sxs-lookup"><span data-stu-id="474ee-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="474ee-126">Администратор может изменить это поведение таким образом, чтобы ссылка блокировалась, в которой сообщения, содержащие URL-адреса, и попытка инициировать передачу файлов заблокированы сервером в соответствии с их целевыми адресами.</span><span class="sxs-lookup"><span data-stu-id="474ee-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="474ee-127">Иимфилтер устанавливается на все серверы Lync Server, кроме прокси-серверов и серверов архивации.</span><span class="sxs-lookup"><span data-stu-id="474ee-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="474ee-128">Усерпинсервице используется для проверки персональных идентификационных номеров пользователей (PIN) для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="474ee-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="474ee-129">Дефаултраутинг является приложением маршрутизации по умолчанию для серверов с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="474ee-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="474ee-130">По умолчанию она включена.</span><span class="sxs-lookup"><span data-stu-id="474ee-130">It is enabled by default.</span></span> <span data-ttu-id="474ee-131">Приложение маршрутизации установлено на всех стандартных серверах выпуска и Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="474ee-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="474ee-132">Ексумраутинг направляет вызовы в единую систему обмена сообщениями Exchange Server (UM).</span><span class="sxs-lookup"><span data-stu-id="474ee-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="474ee-133">Ексумраутинг определяет соответствующий сервер Exchange UM, чтобы перенаправлять вызов, когда на него добавляется новое сообщение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="474ee-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="474ee-134">Ексумраутинг также обрабатывает некоторые другие аспекты интеграции Exchange UM, включая маршрутизацию для автосекретаря и абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="474ee-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="474ee-135">Аутбаундраутинг определяет шлюз, который направляет Звонок на номер телефона в соответствии с набираемым номером и авторизацией набора номера пользователя.</span><span class="sxs-lookup"><span data-stu-id="474ee-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="474ee-136">Аутбаундраутинг также обрабатывает перенаправление звонков, если шлюз не может обработать звонок.</span><span class="sxs-lookup"><span data-stu-id="474ee-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="474ee-137">Коеажент получает отчеты с данными о QoS (QoE) из конечных точек через запросы службы SIP и отправляет данные в очередь назначения на сервере мониторинга или сторонних потребителей, использующих HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="474ee-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="474ee-138">Подробные сведения можно найти [в разделе Развертывание мониторинга в Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="474ee-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="474ee-139">Аутгоингфедератион принудительно осуществляет проверку Федерации на уровне клиента для сообщений, отправляемых на целевое внешнее развертывание.</span><span class="sxs-lookup"><span data-stu-id="474ee-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="474ee-140">Акпраутинг прокси-серверы, адресованные поставщику видеоконференций на шлюз поставщика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="474ee-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="474ee-141">Сценарии, запускаемые на пограничных серверах, включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="474ee-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="474ee-142">иимфилтер</span><span class="sxs-lookup"><span data-stu-id="474ee-142">IIMFilter</span></span>

  - <span data-ttu-id="474ee-143">Оптионшандлер отвечает на запросы параметров, отправленные с **200 ОК** , если запрос адресован текущему серверу.</span><span class="sxs-lookup"><span data-stu-id="474ee-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="474ee-144">Используется для проверки топологии.</span><span class="sxs-lookup"><span data-stu-id="474ee-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="474ee-145">См. также</span><span class="sxs-lookup"><span data-stu-id="474ee-145">See Also</span></span>


[<span data-ttu-id="474ee-146">Включение и отключение серверного приложения Microsoft SIP Languageing (МСПЛ) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474ee-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="474ee-147">Пометка приложения на языке обработки Microsoft SIP (МСПЛ) как критическое или некритическое в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474ee-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

