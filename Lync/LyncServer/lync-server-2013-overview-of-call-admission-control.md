---
title: 'Lync Server 2013: Общие сведения об управлении допуском звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cba1a83ce64fa575cf5de724d5dd215fcb459c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="8f8da-102">Общие сведения об управлении допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8da-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f8da-103">_**Тема последнего изменения:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="8f8da-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="8f8da-104">Связь в реальном времени важна для задержки и потери пакетов, которые могут возникать в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="8f8da-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="8f8da-105">Контроль допуска звонков (CAC) на основе доступной пропускной способности сети определяет, следует ли разрешать установку сеансов связи в режиме реального времени, таких как голосовые или видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="8f8da-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="8f8da-106">Модель CAC в Lync Server 2013 содержит четыре основных атрибута:</span><span class="sxs-lookup"><span data-stu-id="8f8da-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="8f8da-107">Простота развертывания и управления без необходимости дополнительного оборудования, например специально настроенных маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="8f8da-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="8f8da-p102">Разрешаются критические случаи использования объединенных коммуникаций, такие как перемещающиеся пользователи или несколько точек подключения. Политики контроля допуска звонков осуществляются в соответствии с тем, где располагается конечная точка, а не с тем, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="8f8da-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="8f8da-110">Помимо голосовых вызовов, контроль допуска звонков может применяться к другому трафику, такому как видеовызовы и сеансы аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="8f8da-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="8f8da-111">Обеспечивает гибкость, позволяющую представление разных видов сетевых топологий.</span><span class="sxs-lookup"><span data-stu-id="8f8da-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="8f8da-112">Примеры можно найти [в разделе компоненты и топологии для CAC в Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="8f8da-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="8f8da-113">Если новый аудио- или видеосеанс превышает ограничения пропускной способности, установленные в сети WAN, то этот сеанс либо блокируется, либо (только в случае телефонных вызовов) перенаправляется в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8f8da-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="8f8da-p104">Контроль допуска звонков управляет трафиком в режиме реального времени только для звука и видео. Он не управляет трафиком данных.</span><span class="sxs-lookup"><span data-stu-id="8f8da-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="8f8da-116">Администраторы определяют политики CAC, которые принудительно применяются службой политики пропускной способности, установленной с каждым пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8f8da-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="8f8da-117">Параметры CAC автоматически распространяются на все серверы переднего плана Lync Server в сети.</span><span class="sxs-lookup"><span data-stu-id="8f8da-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="8f8da-118">Для вызовов, завершившихся неудачно из-за политик CAC, очередность перенаправления вызова выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8f8da-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="8f8da-119">Интернет</span><span class="sxs-lookup"><span data-stu-id="8f8da-119">Internet</span></span>

2.  <span data-ttu-id="8f8da-120">ТСОП</span><span class="sxs-lookup"><span data-stu-id="8f8da-120">PSTN</span></span>

3.  <span data-ttu-id="8f8da-121">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="8f8da-121">Voice mail</span></span>

<span data-ttu-id="8f8da-p106">Регистрация вызовов (CDR) захватывает сведения о вызовах, которые перенаправляются в ТСОП или в голосовую почту. CDR не захватывает сведения о вызовах, которые перенаправляются в Интернет, поскольку Интернет воспринимается скорее как альтернативный путь, а не как дополнительный вариант.</span><span class="sxs-lookup"><span data-stu-id="8f8da-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f8da-124">Вложения голосовой почты не будут отклоняться из-за ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="8f8da-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="8f8da-p107">Служба политик пропускной способности создает два типа файлов журналов в формате с разделением запятыми (CSV). **Журнал ошибок команд CHECK** заполняется, когда отклоняются запросы пропускной способности. **Файл журнала использования линий связи** регистрирует снимок топологии сети и использование полосы пропускания WAN-канала. Оба эти журнала могут помочь вам при тонкой настройке политик контроля допуска звонков на основе использования.</span><span class="sxs-lookup"><span data-stu-id="8f8da-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="8f8da-129">Аспекты контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="8f8da-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="8f8da-130">Администратор выбирает установку службы политик пропускной способности в первом пуле, настроенном на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="8f8da-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="8f8da-131">Поскольку в каждом сетевом регионе имеется один центральный сайт, то в этом регионе имеется только одна служба политик пропускной способности, управляющая политикой пропускной способности для этого региона, связанными с нею сайтами и ссылками на эти сайты.</span><span class="sxs-lookup"><span data-stu-id="8f8da-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="8f8da-132">Служба политики пропускной способности работает как часть серверного переднего плана, поэтому в этом пуле есть высокий уровень доступности.</span><span class="sxs-lookup"><span data-stu-id="8f8da-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="8f8da-133">Служба политики пропускной способности, запущенная на каждом сервере переднего плана, синхронизируется каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="8f8da-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="8f8da-134">Если пул переднего плана завершается сбоем, политики CAC больше не применяются для этого сайта, пока не будет удалена служба политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="8f8da-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="8f8da-135">Это означает, что все время неработоспособности службы политик пропускной способности будут проходить все звонки.</span><span class="sxs-lookup"><span data-stu-id="8f8da-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="8f8da-136">Следовательно, существует возможность превышения лимита пропускной способности в течение этого периода.</span><span class="sxs-lookup"><span data-stu-id="8f8da-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="8f8da-137">Служба политики пропускной способности обеспечивает высокий уровень доступности в пуле переднего плана; Однако он не обеспечивает избыточность среди интерфейсных пулов.</span><span class="sxs-lookup"><span data-stu-id="8f8da-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="8f8da-138">Служба политики пропускной способности не может отработки отказа с одного пула переднего интерфейса на другой.</span><span class="sxs-lookup"><span data-stu-id="8f8da-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="8f8da-139">После восстановления службы для пула переднего плана служба политики пропускной способности возобновляет работу и может принудительно применять проверку политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="8f8da-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="8f8da-140">Сетевые аспекты</span><span class="sxs-lookup"><span data-stu-id="8f8da-140">Network Considerations</span></span>

<span data-ttu-id="8f8da-141">Несмотря на то, что для голосовой связи и видеосвязи применяются ограничения пропускной способности в службе политики пропускной способности в Lync Server 2013, это ограничение не применяется на маршрутизаторе сети (Layer 2 и 3).</span><span class="sxs-lookup"><span data-stu-id="8f8da-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="8f8da-142">Lync Server 2010 CAC не может предотвратить использование приложением для обработки данных всей пропускной способности сети, включая пропускную способность, зарезервированную для аудио-и видеосвязи в соответствии с политикой CAC.</span><span class="sxs-lookup"><span data-stu-id="8f8da-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="8f8da-143">Чтобы защитить необходимую пропускную способность в сети, вы можете развернуть протокол качества обслуживания (QoS), такой как приоритизированные службы (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="8f8da-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="8f8da-144">Поэтому рекомендуется согласовывать определяемые вами политики пропускной способности контроля допуска звонков со всеми параметрами QoS, которые вы можете развернуть.</span><span class="sxs-lookup"><span data-stu-id="8f8da-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="8f8da-145">Пути передачи мультимедиа и сигналов через VPN</span><span class="sxs-lookup"><span data-stu-id="8f8da-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="8f8da-p111">Если ваше предприятие поддерживает передачу мультимедиа через VPN, убедитесь, что как поток мультимедиа, так и поток сигналов проходят через VPN или маршрутизируются через Интернет. По умолчанию потоки мультимедиа и сигналов проходят через VPN-туннель.</span><span class="sxs-lookup"><span data-stu-id="8f8da-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="8f8da-148">Контроль допуска звонков внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8f8da-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="8f8da-149">Управление допуском звонков не применяется для удаленных пользователей, в которых сетевой трафик проходит через Интернет.</span><span class="sxs-lookup"><span data-stu-id="8f8da-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="8f8da-150">Поскольку трафик мультимедиа проходит через Интернет, а не управляется приложением Lync Server, нельзя применять CAC.</span><span class="sxs-lookup"><span data-stu-id="8f8da-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="8f8da-151">Однако проверка CAC будет проводиться в той части звонка, которая проходит через корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="8f8da-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="8f8da-152">Контроль допуска звонков для подключений ТСОП</span><span class="sxs-lookup"><span data-stu-id="8f8da-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="8f8da-153">Управление допуском звонков обеспечивается на сервере-посреднике, независимо от того, подключено ли оно к IP-или УАТС, шлюзу PSTN или магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="8f8da-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="8f8da-154">Поскольку сервер-посредник является пользовательским агентом (B2BUA), он завершает работу мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8f8da-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="8f8da-155">У него есть две стороны соединения: сторона, подключенная к Lync Server и сторона шлюза, которая соединена с шлюзами PSTN, IP/PBX или SIP-магистрали.</span><span class="sxs-lookup"><span data-stu-id="8f8da-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="8f8da-156">Подробнее об использовании PSTN можно узнать [в разделе Планирование подключений PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8f8da-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="8f8da-157">CAC можно применять на обеих сторонах сервера, если не включена функция обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8f8da-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="8f8da-158">Если режим обхода мультимедиа включен, трафик мультимедиа не передается на сервер по умолчанию, а прямо между клиентом Lync и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="8f8da-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="8f8da-159">В этом случае контроль допуска звонков не требуется.</span><span class="sxs-lookup"><span data-stu-id="8f8da-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="8f8da-160">Подробности можно найти [в разделе Планирование обхода мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="8f8da-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="8f8da-161">На следующем рисунке показано, как осуществляется контроль допуска звонков в подключениях ТСОП с включенным обходом сервера-посредника и без него.</span><span class="sxs-lookup"><span data-stu-id="8f8da-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="8f8da-162">**Осуществление контроля допуска звонков в подключениях ТСОП**</span><span class="sxs-lookup"><span data-stu-id="8f8da-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="8f8da-163">![Обход принудительного подключения мультимедиа с использованием голосовой почты] (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Обход принудительного подключения мультимедиа с использованием голосовой почты")</span><span class="sxs-lookup"><span data-stu-id="8f8da-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="8f8da-164">Совместимость управления допуском звонков с более ранними версиями Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="8f8da-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="8f8da-165">Управление допуском звонков может быть включено только для конечных точек, включенных для Lync Server 2010 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8f8da-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="8f8da-166">Не удается включить управление допуском звонков для конечных точек, использующих Office Communicator 2007 R2 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="8f8da-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="8f8da-167">**Приложение CAC на разных версиях Lync Server**</span><span class="sxs-lookup"><span data-stu-id="8f8da-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="8f8da-168">![Схема сравнения версий голосовой связи] (images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Схема сравнения версий голосовой связи")</span><span class="sxs-lookup"><span data-stu-id="8f8da-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

