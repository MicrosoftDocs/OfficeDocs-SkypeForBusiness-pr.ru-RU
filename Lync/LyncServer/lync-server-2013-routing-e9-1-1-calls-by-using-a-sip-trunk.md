---
title: 'Lync Server 2013: Маршрутизация вызовов E9 – 1 – 1 с помощью магистральной линии SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d58507d72a096cb3fbf6deb0d09cddc542fdc2d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="5d4e0-102">Маршрутизация вызовов E9 – 1 – 1 с помощью магистральной линии SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d4e0-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d4e0-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5d4e0-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5d4e0-104">Использование SIP-магистрали для подключения к квалифицированному поставщику услуг E9-1-1 — лишь один из способов развертывания E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="5d4e0-105">Сведения об использовании шлюза ELIN для подключения к поставщику услуг E9-1-1, основанному на общедоступной телефонной сети (PSTN), приведены в разделе [Маршрутизация вызовов E9-1-1 с помощью шлюза Elin в Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="5d4e0-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="5d4e0-106">На следующей схеме показано, как экстренные вызовы маршрутизируются с Lync Server на общедоступную точку ответа безопасности (PSAP) при использовании магистральной сети SIP и поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="5d4e0-107">**При маршрутизации E9-1-1 вызовы обрабатываются через SIP-магистраль.**</span><span class="sxs-lookup"><span data-stu-id="5d4e0-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="5d4e0-108">![Маршрутизация экстренных вызовов из Lync Server в PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Маршрутизация экстренных вызовов из Lync Server в PSAP")</span><span class="sxs-lookup"><span data-stu-id="5d4e0-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="5d4e0-109">При выполнении экстренного вызова из совместимого клиента Lync Server:</span><span class="sxs-lookup"><span data-stu-id="5d4e0-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="5d4e0-110">ПРИГЛАШЕНИЕ SIP, содержащее расположение, номер обратного вызова абонента и (необязательно) URL-адрес уведомлений и номер обратного вызова конференции, перенаправляется на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="5d4e0-111">Lync Server соответствует номеру экстренного реагирования и направляет вызов (на основе значения **использования PSTN** , определенного в соответствующей политике расположения) на сервер-посредник, а также через магистраль SIP с поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="5d4e0-p102">Поставщик услуг E9-1-1 выполняет маршрутизацию экстренного вызова на соответствующий пункт экстренной связи (ОПЭС) с учетом данных о местоположении, предоставляемых для вызова. Если клиент добавляет проверенное местоположение пункта экстренного реагирования (ПЭР) для экстренного вызова, поставщик автоматически маршрутизирует вызов на соответствующий ОПЭС. Если ПЭР вводится пользователем вручную, то центр обработки экстренных вызовов сначала устно подтверждает точность местоположения звонящего до того, как вызов будет маршрутизирован на ОПЭС.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="5d4e0-115">Если вы настроили политику расположения для уведомлений, одному или нескольким должностным лицам Организации по обеспечению безопасности отправляется специальное мгновенное сообщение Lync.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="5d4e0-116">Это сообщение всегда выводится на экран руководителей безопасности и содержит имя звонящего, номер телефона, время и расположение, позволяя сотрудникам системы безопасности быстро реагировать на вызывающий абонент с помощью мгновенного сообщения или голоса.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="5d4e0-117">Если для конференц-связи настроена политика определения местоположения, которая поддерживается поставщиком услуг E9-1-1, внутренняя служба безопасности подключается к вызову посредством конференц-связи с использованием односторонней или двусторонней звуковой связи.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="5d4e0-118">В случае преждевременного завершения вызова, ОПЭС использует номер ответного звонка для связи непосредственно с вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="5d4e0-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

