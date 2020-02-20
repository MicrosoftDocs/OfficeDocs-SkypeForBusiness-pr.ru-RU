---
title: 'Lync Server 2013: Обзор мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d53d740af9cb0407b0309d858d4a1a85b3b976
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="06f78-102">Обзор мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06f78-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06f78-103">_**Последнее изменение темы:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="06f78-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="06f78-104">В Microsoft Lync Server 2013 мониторинг используется для сбора сведений об использовании и качества взаимодействия (QoE) о сеансах связи, в которых участвуют пользователи.</span><span class="sxs-lookup"><span data-stu-id="06f78-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="06f78-105">Сеанс — это общий термин, который означает пользовательское подключение к следующим элементам:</span><span class="sxs-lookup"><span data-stu-id="06f78-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="06f78-106">Встречи</span><span class="sxs-lookup"><span data-stu-id="06f78-106">Conference</span></span>

  - <span data-ttu-id="06f78-107">Модальность конференции (например, звук и видео или общий доступ к приложениям)</span><span class="sxs-lookup"><span data-stu-id="06f78-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="06f78-108">Другой пользователь через одноранговое общение, например обмен мгновенными сообщениями или аудиовызов</span><span class="sxs-lookup"><span data-stu-id="06f78-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06f78-109">Lync Server 2013 отслеживает сведения о каждом сеансе: кто вызывает пользователя; какие конечные точки использовались в сеансе; время последнего сеанса; что было воспринимаемым качеством сеанса; и т. д.</span><span class="sxs-lookup"><span data-stu-id="06f78-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="06f78-110">Тем не менее, Lync Server не записывает и не сохраняет фактический вызов.</span><span class="sxs-lookup"><span data-stu-id="06f78-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="06f78-111">Кроме того, в том числе сеансы обмена мгновенными сообщениями: Хотя Lync Server записывает сведения о сеансах обмена мгновенными сообщениями, он не ведет записи каждого мгновенного сообщения, отправленного во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="06f78-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="06f78-112">Сведения о вызовах, собранные Lync Server, можно использовать для любого количества применений, в том числе:</span><span class="sxs-lookup"><span data-stu-id="06f78-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="06f78-113">**Рентабельность инвестиций**.</span><span class="sxs-lookup"><span data-stu-id="06f78-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="06f78-114">Администраторы могут сравнить сведения об использовании, собранные сервером мониторинга, с похожими данными, собранными для предыдущей системы телефонной связи, чтобы показать экономию расходов и обеспечить выравнивание развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06f78-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="06f78-p104">**Инвентаризация устройств**. Сведения по управлению активами позволяют администраторам определять старые устройства, которые все еще используются, хотя должны быть заменены, а также определять дорогостоящие устройства, которые не применяются в соответствии с их назначением или возможностями.</span><span class="sxs-lookup"><span data-stu-id="06f78-p104">**Device Inventory Management**. Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="06f78-117">Служба технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="06f78-117">Help Desk.</span></span> <span data-ttu-id="06f78-118">Устранение неполадок, связанных с данными, позволяет специалистам поддержки определять причину сбоя вызова абонента без сбора журналов на стороне сервера или клиента.</span><span class="sxs-lookup"><span data-stu-id="06f78-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="06f78-119">Эти сведения могут быть легко доступны и понятны сотрудникам службы поддержки, у которых нет глубоких технических знаний о Microsoft Lync 2013 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06f78-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="06f78-p106">**Устранение системных неполадок.**. Администраторы могут определять серьезные неполадки, которые приведут к невозможности выполнения базовых задач пользователями, например присоединяться к конференции, выполнять вызов или отправлять мгновенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="06f78-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="06f78-122">В дополнение к этим основным сведениям о вызовах сервер мониторинга также предоставляет механизм, который позволяет конечным точкам SIP (таким как Lync 2013) предоставлять сведения об устранении неполадок, которые не имеют доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="06f78-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="06f78-p107">**Показатели мультимедиа, влияющие на качество**. Эти метрики связаны с фактической передачей самого вызова; они обеспечивают сортировку журнала, а также отслеживают прохождение вызова по сети. Эти показатели (которые включают такие данные, как потеря пакетов, дрожание и время полного обхода) содержат сведения о том, что случилось с вызовом с момента оставления им конечной точки до момента прибытия на конечную точку другого абонента.</span><span class="sxs-lookup"><span data-stu-id="06f78-p107">**Media Metrics that Impact Quality**. These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network. These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="06f78-126">**Ошибки, о которых было сообщено пользователю**.</span><span class="sxs-lookup"><span data-stu-id="06f78-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="06f78-127">К этим показателям относятся уведомления низкого качества, которые Lync 2013 предоставляет конечным пользователям в случаях, когда они слишком далеко от микрофона, слишком тихо, плохо подключен к сети или имеют низкое качество, так как другая программа на компьютере использование доступных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="06f78-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="06f78-p109">**Сведения о среде**. Сюда входят показатели, которые описывают факторы качества связи, такие как используемый тип микрофона и динамиков, подключается ли пользователь через VPN, используется ли беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="06f78-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="06f78-p110">В конце каждого вызова конечные точки, совместимые с SIP, автоматически передают эти сведения на интерфейсный сервер, который обрабатывал вызов. Нет необходимости предпринимать какие-либо действия для передачи этих сведений с конечных точек, так как подобное поведение характерно для протокола SIP. Однако если необходимо собрать и сохранить эти данные, необходимо установить и включить возможность мониторинга. В этом случае сведения о вызовах будет собираться агентами, работающими на интерфейсном сервере, и заноситься в две базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06f78-p110">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call. You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol. However, if you want to collect and store that information, then you need to install and enable monitoring. If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="06f78-134">Обратите внимание на то, что процесс установки и настройки мониторинга упрощен в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06f78-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="06f78-135">В предыдущих версиях для мониторинга была необходима отдельная роль сервера мониторинга, что, как правило, означало необходимость использования для мониторинга отдельного компьютера.</span><span class="sxs-lookup"><span data-stu-id="06f78-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="06f78-136">Однако в Lync Server 2013 роль сервера мониторинга удалена.</span><span class="sxs-lookup"><span data-stu-id="06f78-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="06f78-137">Вместо нее используется служба мониторинга (в виде "единых агентов по сбору данных"), которая совмещена с интерфейсными серверами.</span><span class="sxs-lookup"><span data-stu-id="06f78-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="06f78-138">Это имеет как минимум два значительных преимущества.</span><span class="sxs-lookup"><span data-stu-id="06f78-138">This has at least two major benefits.</span></span> <span data-ttu-id="06f78-139">Совмещение службы мониторинга:</span><span class="sxs-lookup"><span data-stu-id="06f78-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="06f78-140">Уменьшает количество ролей сервера, необходимых при внедрении Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06f78-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="06f78-141">Исключение из развертывания роли сервера мониторинга также позволяет снизить затраты путем устранения необходимости поддержки серверов, выделенных специально для мониторинга.</span><span class="sxs-lookup"><span data-stu-id="06f78-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="06f78-142">Сокращает сложность установки и администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06f78-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="06f78-143">Совмещение служб мониторинга с интерфейсными серверами устраняет необходимость в установке, настройке и управлении ролью сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="06f78-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="06f78-144">Для получения дополнительных сведений ознакомьтесь с разделом [развертывание мониторинга в Lync server 2013](lync-server-2013-deploying-monitoring.md) в руководстве по развертыванию lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="06f78-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

