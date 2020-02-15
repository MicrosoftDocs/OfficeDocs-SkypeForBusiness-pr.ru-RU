---
title: 'Lync Server 2013: Общие сведения о службе автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57dd0158f4a9b6c798d1b968353e5f84b55d46e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="2e5c7-102">Общие сведения о службе автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5c7-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e5c7-103">_**Последнее изменение темы:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="2e5c7-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="2e5c7-104">Служба автообнаружения Lync Server 2013 — это функция, изначально появившаяся в Microsoft Lync Server 2010 в составе накопительного пакета обновления для Lync Server 2010: Ноябрь 2011 г.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="2e5c7-105">В дополнение к исправлениям это накопительное обновление доставляет поддержку для клиентов Lync Mobile и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="2e5c7-106">В Lync Server 2013 служба автообнаружения является неотъемлемой частью работы внешних и внутренних мобильных клиентов, а автообнаружение также расширено до новых клиентов, например недавно появившегося приложения Lync Windows Store для Windows 8.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="2e5c7-107">Автообнаружение также используется клиентами Lync 2013 для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="2e5c7-108">Служба автообнаружения в Lync Server распознается требуемыми записями DNS (Domain Name System) \*\*lyncdiscover.\< Domain\> \*\* и **lyncdiscoverinternal.\< Domain\>(домен**).</span><span class="sxs-lookup"><span data-stu-id="2e5c7-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="2e5c7-109">Кроме того, в новых версиях Lync 2010 и Lync 2013 для настольных компьютеров предпочтительнее выполнять обнаружение через записи DNS SRV, используя DNS SRV-записи только в том случае, если lyncdiscover. \<Domain\> или lyncdiscoverinternal. \<домен\> не отвечает или не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="2e5c7-110">Приложение Lync в магазине Windows для Windows 8 и Lync Mobile использует только службу автообнаружения и не будет ссылаться на традиционные DNS SRV-записи.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="2e5c7-111">В Lync Server 2013 служба автообнаружения расширяется для связи с клиентом, какие элементы, функции и методы связи доступны клиенту.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="2e5c7-112">Информация передается через запрос, отправляемый клиентом, а веб-службы Lync Server — в ответ с четким определенным ответом, который называет доступ к клиенту и как обращаться к этим функциям в формате автообнаружения. Документ ответа.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="2e5c7-113">Лучший способ получить представление о документе ответа автообнаружения, в том числе о том, как веб-службы обмениваются функциями с помощью этого документа, — это диссект и определять каждую строку в типичном ответе из документа ответа на автообнаружение веб-службы Lync.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2e5c7-114">В приведенных ниже сведениях пользователь уже прошел проверку подлинности на основном сервере, отвечая на запрос проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2e5c7-115">Веб-служба автообнаружения Lync определена в разделе <STRONG>протоколы Microsoft Office</STRONG> в разделе <STRONG>Open спецификации</STRONG> библиотеки <STRONG>Microsoft Developer Network</STRONG> (MSDN).</span><span class="sxs-lookup"><span data-stu-id="2e5c7-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="2e5c7-116">Подробные сведения см. в документе с полным описанием "протокол веб-службы автообнаружения Lync" по <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>адресу:.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="2e5c7-117">Подробные сведения о проверке подлинности можно найти в <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>разделе "протокол веб-службы OC Authentication".</span><span class="sxs-lookup"><span data-stu-id="2e5c7-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="2e5c7-118">Отклик автообнаружения веб-службы Lync Server</span><span class="sxs-lookup"><span data-stu-id="2e5c7-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="2e5c7-119">Ответ, возвращенный при отправке запроса автообнаружения, совпадает для внутреннего или внешнего клиента.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="2e5c7-120">Некоторые параметры, которые относятся к расположению, могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="2e5c7-121">Если клиентский запрос получен, но реальный пул отличается от того, к которому был подключен, домашний пул пользователя будет настроен для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="2e5c7-122">Коллега, учетная запись которого находится в другом пуле, но вход в систему с помощью того же Office получит немного иной отклик.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="2e5c7-123">Ответ указывает на правильный сервер переднего плана или пул переднего плана для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="2e5c7-124">Пример документа ответа автообнаружения:</span><span class="sxs-lookup"><span data-stu-id="2e5c7-124">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="2e5c7-125">Сведения о документе ответа автообнаружения</span><span class="sxs-lookup"><span data-stu-id="2e5c7-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="2e5c7-126">Документ ответа автообнаружения может иметь один из двух форматов.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="2e5c7-127">По умолчанию используется формат нотации объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="2e5c7-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="2e5c7-128">Другой формат — XML-документ.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="2e5c7-129">В этом примере используется XML.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-129">The XML is used for this example.</span></span> <span data-ttu-id="2e5c7-130">Запрос и ответ можно предсказать, так как документ имеет определенную схему, определяющую формат.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="2e5c7-131">Строка в документе, описывающая используемую схему, является первой строкой в запросе или ответе:</span><span class="sxs-lookup"><span data-stu-id="2e5c7-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="2e5c7-132">Определение **акцесслокатион = "External"** указывает на то, что запрос был выполнен от внешнего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="2e5c7-133">Сипсерверинтерналакцесс и Сипсерверекстерналакцесс в настоящее время не используются.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="2e5c7-134">Эти записи зарезервированы для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="2e5c7-135">Сипклиентинтерналакцесс и Сипклиентекстерналакцесс описывают полное доменное имя и порт, которые внутренний или внешний клиент будет использовать для доступа к определенному серверу SIP.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="2e5c7-136">Клиент Lync для настольных ПК и приложение Магазина Windows для Lync используют эти записи в зависимости от их расположения (внутреннего или внешнего) для поиска сервера директории или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="2e5c7-137">`Autodiscover` Ссылки содержат точки входа службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="2e5c7-138">Атрибут Token содержит имя службы, а href — это URL-адрес, который определяет клиента, на котором можно найти службу.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="2e5c7-139">Клиенты во внешней сети используют `External/Autodiscover`.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="2e5c7-140">Служба автообнаружения устанавливается в рамках процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="2e5c7-141">`Internal/Autodiscover`в настоящее время не используется и зарезервировано для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="2e5c7-142">`AuthBroker` Ссылки содержат точки входа службы для внутренней и внешней службы посредника проверки подлинности, в данном случае SIP. svc.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="2e5c7-143">Атрибут Token содержит имя службы, а href — это URL-адрес, который определяет клиента, на котором можно найти службу.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="2e5c7-144">Клиенты во внутренней сети с использованием `Internal/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="2e5c7-145">Клиенты во внешней сети используют `External/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="2e5c7-146">Служба Аусброкер устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="2e5c7-147">`WebScheduler` Маркер ссылается на URL-адреса для доступа клиентов к планированию веб-сайта для конференций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="2e5c7-148">В настоящее время используется `External/WebScheduler` только параметр.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="2e5c7-149">Веб-планировщик устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="2e5c7-150">`Internal/Mcx``External/Mcx` — это расположения служб Mobility Services, которые представлены в накопительном пакете обновления для Lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="2e5c7-151">Эти ссылки продолжатся по мере использования Lync 2010 Mobile на всех поддерживаемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="2e5c7-152">Служба MCX устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="2e5c7-153">**Internal/Ucwa**, **External/Ucwa** и **Ucwa** предоставляют клиентам доступ к интерфейсному интерфейсу веб-приложений единой системы обмена сообщениями (API Ucwa или просто Ucwa).</span><span class="sxs-lookup"><span data-stu-id="2e5c7-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="2e5c7-154">`Internal/Ucwa``External/Ucwa` виртуальные каталоги — это точки доступа, зарезервированные для будущего улучшения возможностей, и не используются.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="2e5c7-155">`Ucwa` Виртуальный каталог используется для Microsoft Lync Mobile (в составе lync Server 2013) на всех поддерживаемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="2e5c7-156">Служба UCWA устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="2e5c7-157">`Internal/XFrame`, **Внешние/ксфраме** и **ксфраме** предоставляют доступ к серверным приложениям на основе UCWA.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="2e5c7-158">Ксфраме устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="2e5c7-159">`Self` Маркер ссылается на сведения, характерные для клиента (тип ответа пользователя), который делает запрос.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="2e5c7-160">Клиент, который проводил этот запрос, является внешним, и этот справочник по автообнаружения относится к пользовательской части службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="2e5c7-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e5c7-161">См. также</span><span class="sxs-lookup"><span data-stu-id="2e5c7-161">See Also</span></span>


[<span data-ttu-id="2e5c7-162">Требования к системе для компонентов доступа внешних пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5c7-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="2e5c7-163">Планирование автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5c7-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

