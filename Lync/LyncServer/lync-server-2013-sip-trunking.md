---
title: 'Lync Server 2013: магистральная линия SIP'
description: 'Lync Server 2013: магистральная линия SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60b68d9d0400c87de2832d7fe7bdabe4057ec47a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559015"
---
# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="5347e-103">Распределение каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5347e-103">SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5347e-104">_**Последнее изменение темы:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="5347e-104">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="5347e-p101">С помощью протокола SIP инициируются и управляются сеансы связи по протоколу VoIP для базовой телефонной связи и для многих дополнительных коммуникационных услуг в режиме реального времени, таких как обмен мгновенными сообщениями, конференц-связь, обнаружение присутствия и мультимедиа. В этом разделе предоставляются сведения по планированию для реализации *каналов SIP*, разновидности подключения SIP, которое распространяется за пределы локальной сети.</span><span class="sxs-lookup"><span data-stu-id="5347e-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="5347e-107">Что такое распределение каналов SIP?</span><span class="sxs-lookup"><span data-stu-id="5347e-107">What is SIP Trunking?</span></span>

<span data-ttu-id="5347e-p102">Распределение каналов SIP — это IP-подключение, которое устанавливает коммуникационную связь SIP между вашей организацией и поставщиком услуг Интернет-телефонии (ITSP) за пределами брандмауэра организации. Обычно канал SIP используется для подключения центрального сайта организации к ITSP. В некоторых случаях вы также можете выбрать использование распределения каналов SIP для подключения к ITSP сайтов филиалов.</span><span class="sxs-lookup"><span data-stu-id="5347e-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="5347e-111">Распределение каналов SIP по сравнению с прямыми подключениями SIP</span><span class="sxs-lookup"><span data-stu-id="5347e-111">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="5347e-112">Термин *канал* пришел из технологии с коммутируемыми каналами.</span><span class="sxs-lookup"><span data-stu-id="5347e-112">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="5347e-113">Он относится к выделенной физической линии, соединяющей телефонное коммутационное оборудование.</span><span class="sxs-lookup"><span data-stu-id="5347e-113">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="5347e-114">Как и их предшественники, магистральные каналы мультиплексирования (TDM), магистральные линии SIP являются подключениями между двумя отдельными сетями SIP — Lync Server 2013 Enterprise и ITSP.</span><span class="sxs-lookup"><span data-stu-id="5347e-114">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="5347e-115">В отличие от коммутируемых каналов, каналы SIP являются виртуальными подключениями, которые могут быть установлены в любых поддерживаемых типах подключений распределения каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="5347e-115">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="5347e-116">Дополнительные сведения о поддерживаемых типах подключений приведены [в статье как реализовать магистральные линии SIP в Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="5347e-116">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="5347e-117">С другой стороны, прямые подключения SIP — это подключения, которые не пересекают границы локальной сети (т.е. они подключаются к шлюзу ТСОП или УАТС во внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="5347e-117">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="5347e-118">Сведения о том, как использовать прямые подключения SIP с Lync Server 2013, можно найти [в разделе Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="5347e-118">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5347e-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="5347e-119">In This Section</span></span>

  - [<span data-ttu-id="5347e-120">Обзор распределения каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5347e-120">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="5347e-121">Как реализовать магистральные линии SIP в Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="5347e-121">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="5347e-122">Компоненты и топологии для распределения каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5347e-122">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="5347e-123">Магистральная линия SIP сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5347e-123">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="5347e-124">Контрольный список развертывания магистрали SIP для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5347e-124">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

