---
title: 'Lync Server 2013: обзор контроля допуска звонков'
description: 'Lync Server 2013: обзор контроля допуска звонков.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0fe2fc75ea9bc887709b7dbe1c2128513fcff6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562915"
---
# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="25a21-103">Обзор контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25a21-103">Overview of call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25a21-104">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="25a21-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="25a21-105">Сеансы связи в режиме реального времени чувствительны к задержкам и потерям пакетов, которые могут происходить в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="25a21-105">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="25a21-106">Контроль допуска звонков (CAC) на основе доступной пропускной способности сети определяет, следует ли разрешать установку сеансов связи в режиме реального времени, таких как голосовые или видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="25a21-106">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="25a21-107">Конструкция CAC в Lync Server 2013 предлагает четыре основных атрибута:</span><span class="sxs-lookup"><span data-stu-id="25a21-107">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="25a21-108">Простота развертывания и управления без необходимости дополнительного оборудования, например специально настроенных маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="25a21-108">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="25a21-p102">Разрешаются критические случаи использования объединенных коммуникаций, такие как перемещающиеся пользователи или несколько точек подключения. Политики контроля допуска звонков осуществляются в соответствии с тем, где располагается конечная точка, а не с тем, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="25a21-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="25a21-111">Помимо голосовых вызовов, контроль допуска звонков может применяться к другому трафику, такому как видеовызовы и сеансы аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="25a21-111">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="25a21-112">Обеспечивает гибкость, позволяющую представление разных видов сетевых топологий.</span><span class="sxs-lookup"><span data-stu-id="25a21-112">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="25a21-113">Примеры приведены в статье [компоненты и топологии для CAC в Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="25a21-113">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="25a21-114">Если новый аудио- или видеосеанс превышает ограничения пропускной способности, установленные в сети WAN, то этот сеанс либо блокируется, либо (только в случае телефонных вызовов) перенаправляется в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="25a21-114">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="25a21-p104">Контроль допуска звонков управляет трафиком в режиме реального времени только для звука и видео. Он не управляет трафиком данных.</span><span class="sxs-lookup"><span data-stu-id="25a21-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="25a21-117">Администраторы определяют политики контроля допуска звонков, которые применяются службой политики пропускной способности, установленной с каждым пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="25a21-117">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="25a21-118">Параметры CAC автоматически распространяются на все серверы переднего плана Lync Server в сети.</span><span class="sxs-lookup"><span data-stu-id="25a21-118">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="25a21-119">Для вызовов, завершившихся неудачно из-за политик контроля допуска звонков, очередность перенаправления вызова выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="25a21-119">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="25a21-120">Интернет</span><span class="sxs-lookup"><span data-stu-id="25a21-120">Internet</span></span>

2.  <span data-ttu-id="25a21-121">ТСОП</span><span class="sxs-lookup"><span data-stu-id="25a21-121">PSTN</span></span>

3.  <span data-ttu-id="25a21-122">голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="25a21-122">Voice mail</span></span>

<span data-ttu-id="25a21-p106">Регистрация вызовов (CDR) захватывает сведения о вызовах, которые перенаправляются в ТСОП или в голосовую почту. CDR не захватывает сведения о вызовах, которые перенаправляются в Интернет, поскольку Интернет воспринимается скорее как альтернативный путь, а не как дополнительный вариант.</span><span class="sxs-lookup"><span data-stu-id="25a21-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25a21-125">Вложения голосовой почты не будут отклоняться из-за ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="25a21-125">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="25a21-p107">Служба политик пропускной способности создает два типа файлов журналов в формате с разделением запятыми (CSV). Журнал **ошибок команд CHECK** заполняется, когда отклоняются запросы пропускной способности. Журнал **использования линий связи** регистрирует снимок топологии сети и использование полосы пропускания линии связи WAN. Оба эти журнала могут помочь при тонкой настройке политик контроля допуска звонков на основе использования.</span><span class="sxs-lookup"><span data-stu-id="25a21-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="25a21-130">Аспекты контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="25a21-130">Call Admission Control Considerations</span></span>

<span data-ttu-id="25a21-131">Администратор выбирает установку службы политик пропускной способности в первом пуле, настроенном на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="25a21-131">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="25a21-132">Поскольку в каждой области сети имеется один центральный сайт, то в этой области имеется только одна служба политик пропускной способности, управляющая политикой пропускной способности для этой области, связанными с нею сайтами и ссылками на эти сайты.</span><span class="sxs-lookup"><span data-stu-id="25a21-132">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="25a21-133">Служба политики пропускной способности работает как часть серверов переднего плана, поэтому высокая доступность встроена в этот пул.</span><span class="sxs-lookup"><span data-stu-id="25a21-133">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="25a21-134">Служба политики пропускной способности, работающая на каждом сервере переднего плана, синхронизируется каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="25a21-134">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="25a21-135">Если интерфейсный пул завершается с ошибкой, политики CAC больше не применяются для этого сайта до тех пор, пока пул переднего плана и служба политики пропускной способности не перестанут работать.</span><span class="sxs-lookup"><span data-stu-id="25a21-135">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="25a21-136">Это означает, что все время неработоспособности службы политик пропускной способности будут проходить все звонки.</span><span class="sxs-lookup"><span data-stu-id="25a21-136">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="25a21-137">Следовательно, существует возможность превышения лимита пропускной способности линий связи в течение этого периода.</span><span class="sxs-lookup"><span data-stu-id="25a21-137">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="25a21-138">Служба политики пропускной способности обеспечивает высокий уровень доступности в интерфейсном пуле; Однако он не обеспечивает избыточность между интерфейсными пулами.</span><span class="sxs-lookup"><span data-stu-id="25a21-138">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="25a21-139">Служба политики пропускной способности не может отработки отказа из одного интерфейсного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="25a21-139">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="25a21-140">После восстановления службы в пуле переднего плана служба политики пропускной способности возобновляет работу и может повторно применить проверки политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="25a21-140">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="25a21-141">Сетевые аспекты</span><span class="sxs-lookup"><span data-stu-id="25a21-141">Network Considerations</span></span>

<span data-ttu-id="25a21-142">Хотя ограничение пропускной способности для звука и видео применяется службой политики пропускной способности в Lync Server 2013, это ограничение не применяется на сетевом маршрутизаторе (Layer 2 и 3).</span><span class="sxs-lookup"><span data-stu-id="25a21-142">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="25a21-143">Lync Server 2010 CAC не может предотвратить использование приложением для обработки данных всей пропускной способности сети для глобальной сети, включая пропускную способность, зарезервированную для звука и видео с помощью политики CAC.</span><span class="sxs-lookup"><span data-stu-id="25a21-143">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="25a21-144">Чтобы защитить необходимую пропускную способность в сети, можно развернуть протокол качества обслуживания (QoS), например дифференцированные службы (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="25a21-144">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="25a21-145">Поэтому рекомендуется координировать политики пропускной способности CAC, определенные с помощью любых параметров качества обслуживания, которые вы можете развернуть.</span><span class="sxs-lookup"><span data-stu-id="25a21-145">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="25a21-146">Пути передачи мультимедиа и сигналов через VPN</span><span class="sxs-lookup"><span data-stu-id="25a21-146">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="25a21-p111">Если ваше предприятие поддерживает передачу мультимедиа через VPN, убедитесь, что как поток мультимедиа, так и поток сигналов проходят через VPN или маршрутизируются через Интернет. По умолчанию потоки мультимедиа и сигналов проходят через VPN-туннель.</span><span class="sxs-lookup"><span data-stu-id="25a21-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="25a21-149">Контроль допуска звонков внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="25a21-149">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="25a21-150">Контроль допуска звонков не выполняется для удаленных пользователей, когда сетевой трафик проходит через Интернет.</span><span class="sxs-lookup"><span data-stu-id="25a21-150">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="25a21-151">Так как трафик мультимедиа проходит через Интернет, который не управляется Lync Server, невозможно применять CAC.</span><span class="sxs-lookup"><span data-stu-id="25a21-151">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="25a21-152">Однако проверки контроля допуска звонков будут выполняться в части вызова, которая проходит по сети предприятия.</span><span class="sxs-lookup"><span data-stu-id="25a21-152">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="25a21-153">Контроль допуска звонков подключений ТСОП</span><span class="sxs-lookup"><span data-stu-id="25a21-153">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="25a21-154">Контроль допуска звонков обеспечивается на сервере-посреднике независимо от того, подключена ли он к IP/УАТС, шлюзу PSTN или магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="25a21-154">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="25a21-155">Так как сервер-посредник является агентом пользователя с обратной B2BUA, он завершает носитель.</span><span class="sxs-lookup"><span data-stu-id="25a21-155">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="25a21-156">У него есть две стороны подключения: сторона, подключенная к Lync Server и сторону шлюза, которая подключена к шлюзам PSTN, IP/УАТС или магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="25a21-156">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="25a21-157">Подробные сведения о подключениях PSTN приведены [в статье Планирование подключения PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="25a21-157">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="25a21-158">CAC можно применять на обеих сторонах сервера-посредника, если не включен обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="25a21-158">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="25a21-159">Если обход сервера-посредника включен, трафик мультимедиа не передается на сервер-посредник, а передается напрямую между клиентом Lync и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="25a21-159">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="25a21-160">В этом случае контроль допуска звонков не требуется.</span><span class="sxs-lookup"><span data-stu-id="25a21-160">In this case, CAC is not needed.</span></span> <span data-ttu-id="25a21-161">Дополнительные сведения см [в разделе Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="25a21-161">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="25a21-162">На следующем рисунке показано, как осуществляется контроль допуска звонков в подключениях по ТСОП с включенным обходом сервера-посредника и без него.</span><span class="sxs-lookup"><span data-stu-id="25a21-162">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="25a21-163">**Осуществление контроля допуска звонков в подключениях к ТСОП**</span><span class="sxs-lookup"><span data-stu-id="25a21-163">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="25a21-164">![Режим обхода подключений голосовой связи для передачи голоса](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Режим обхода подключений голосовой связи для передачи голоса")</span><span class="sxs-lookup"><span data-stu-id="25a21-164">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="25a21-165">Совместимость контроля допуска звонков с предыдущими версиями Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="25a21-165">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="25a21-166">Контроль допуска звонков можно включить только для конечных точек, которые включены для Lync Server 2010 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="25a21-166">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="25a21-167">Контроль допуска звонков не может быть включен в конечных точках, использующих Office Communicator 2007 R2 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="25a21-167">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="25a21-168">**Применение контроля допуска звонков в разных версиях Lync Server**</span><span class="sxs-lookup"><span data-stu-id="25a21-168">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="25a21-169">![Схема сравнения версий CAC голосовой связи](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Схема сравнения версий CAC голосовой связи")</span><span class="sxs-lookup"><span data-stu-id="25a21-169">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

