---
title: 'Lync Server 2013: требования к службе автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec6c3ada06312f816a75f5539593336addc8d2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="9a9ba-102">Требования к службе автообнаружения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a9ba-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a9ba-103">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="9a9ba-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="9a9ba-104">Служба автообнаружения Microsoft Lync Server 2013 выполняется на серверах директоров и интерфейсных серверах пула, и при публикации в службе DNS мобильные устройства, работающие с Lync Mobile, могут использовать мобильные устройства для обнаружения служб Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="9a9ba-105">Прежде чем мобильные устройства, работающие с Lync Mobile, смогут использовать функцию автоматического обнаружения, необходимо изменить списки альтернативных имен субъектов сертификата на любом директоре и сервере переднего плана, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="9a9ba-106">Кроме того, может потребоваться изменить списки альтернативных имен субъектов для сертификатов, используемых для правил публикации внешних веб-служб на обратных прокси-серверах.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="9a9ba-107">Дополнительные сведения о записях альтернативного имени субъекта, которые необходимы для директоров, серверов переднего плана и обратных прокси-серверов, приведены в статье [технические требования к мобильности в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) в статье Планирование мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="9a9ba-108">Решение об использовании списков альтернативных имен субъектов на обратных прокси-серверах основано на том, публикуете ли вы службу автоматического обнаружения через порт 80 или через порт 443:</span><span class="sxs-lookup"><span data-stu-id="9a9ba-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="9a9ba-109">**Опубликовано на порте 80**   изменения сертификатов не требуются, если исходный запрос к службе автообнаружения проходит через порт 80.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="9a9ba-110">Это связано с тем, что мобильные устройства, работающие с Lync, обращаются к обратному прокси-серверу через порт 80 извне, а затем перенаправляются на директор или сервер переднего плана через внутренний порт 8080.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="9a9ba-111">Дополнительные сведения см. в подразделе «Начальный процесс автоматического обнаружения через порт 80» ниже.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="9a9ba-112">**Опубликовано на порте 443**   список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб, должен содержать *lyncdiscover.\< запись\> sipdomain* для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="9a9ba-113">Повторная выдача сертификатов с использованием внутреннего центра сертификации обычно не вызывает трудностей, но для общих сертификатов, используемых для правила публикации внешних веб-служб, добавление нескольких записей альтернативных имен субъектов может оказаться дорогостоящим.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="9a9ba-114">Чтобы обойти эту проблему, мы поддерживаем начальное подключение автоматического обнаружения через порт 80, который затем перенаправляется на порт 8080 на директоре или сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="9a9ba-115">Например, предположим, что мобильный клиент, на котором работает Lync Mobile, настроен для входа в Lync Server 2013 с помощью функции автоматического обнаружения, использующей HTTP для первоначального запроса.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="9a9ba-116">Первоначальный процесс автообнаружения для мобильных устройств с помощью порта 80</span><span class="sxs-lookup"><span data-stu-id="9a9ba-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="9a9ba-117">Мобильное устройство, на котором работает Lync Mobile, ищет lyncdiscover.contoso.com с помощью DNS, где есть запись A.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="9a9ba-118">Внешняя служба DNS возвращает клиенту IP-адрес внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="9a9ba-119">Мобильное устройство, на котором работает http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com Lync Mobile, отправляет запрос обратному прокси-серверу</span><span class="sxs-lookup"><span data-stu-id="9a9ba-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="9a9ba-120">Правило веб-публикации отправляет запрос через порт 80 извне на порт 8080, который затем перенаправляет его на сервер переднего плана или на сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="9a9ba-121">Поскольку запрос использует протокол HTTP, а не HTTPS, внесение изменений в сертификат для правила публикации внешних веб-служб для обеспечения поддержки службы автоматического обнаружения не требуется.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="9a9ba-122">Служба автоматического обнаружения возвращает URL-адреса внешних веб-служб (в формате HTTPS).</span><span class="sxs-lookup"><span data-stu-id="9a9ba-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="9a9ba-123">Мобильное устройство, на котором работает Lync Mobile, может повторно подключиться к обратному прокси-серверу на порте 443 и перенаправляться на 4443 в службу Mobility Service, запущенную в домашнем пуле пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="9a9ba-124">Поскольку HTTPS-запрос выполняется по URL-адресу внешних веб-служб для URL-адреса службы автообнаружения, он завершается успешно, так как сертификат уже содержит записи альтернативных имен субъектов для полных доменных имен внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="9a9ba-125">В данном сценарии для поддержки мобильности изменения сертификата не требуются.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a9ba-126">Если целевой веб-сервер имеет сертификат, у которого нет соответствующего значения для lyncdiscover.contoso.com в качестве значения списка альтернативных имен субъектов:</span><span class="sxs-lookup"><span data-stu-id="9a9ba-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="9a9ba-127">&nbsp;сервер реагирует на ответ "Server Hello" и не имеет&nbsp;&nbsp;сертификата.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="9a9ba-128">b.&nbsp;&nbsp;&nbsp;мобильное устройство, на котором работает Lync Mobile, немедленно завершает сеанс.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="9a9ba-129">Если целевой веб-сервер имеет сертификат, который включается в себя lyncdiscover.contoso.com в качестве значения списка альтернативных имен субъектов:</span><span class="sxs-lookup"><span data-stu-id="9a9ba-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="9a9ba-130">&nbsp;сервер реагирует на ответ "сервер Hello" и&nbsp;&nbsp;сертификат.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="9a9ba-131">b.&nbsp;&nbsp;&nbsp;мобильное устройство, на котором работает Lync Mobile, проверяет сертификат и завершает подтверждение.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="9a9ba-132">Чтобы обеспечить поддержку начального подключения к службе автоматического обнаружения с использованием порта 80 на обратном прокси-сервере, вы можете создать правило публикации HTTP, аналогичное данному примеру правила веб-публикации для обратного прокси-сервера Forefront Threat Management Gateway 2010:</span><span class="sxs-lookup"><span data-stu-id="9a9ba-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="9a9ba-133">Создайте новое правило веб-публикации (например, **Lync Server Autodiscover (HTTP)**).</span><span class="sxs-lookup"><span data-stu-id="9a9ba-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="9a9ba-134">В поле **Public Name** (Общедоступное имя) введите значение lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="9a9ba-135">На вкладке **Использование моста** выберите только параметр передачи запросов с порта 80 на порт 8080.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="9a9ba-136">На вкладке **Проверка подлинности** выберите **Без проверки подлинности** и **Клиент не может выполнять проверку подлинности напрямую**.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="9a9ba-137">Фиксация изменений и перемещение правила в начало списка правил Lync (первый в порядке обработки).</span><span class="sxs-lookup"><span data-stu-id="9a9ba-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="9a9ba-138">Мобильность для развертывания разделенного домена</span><span class="sxs-lookup"><span data-stu-id="9a9ba-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="9a9ba-139">Общее адресное пространство SIP, которое также называется *разделенным доменом* или *гибридным развертыванием*, представляет собой конфигурацию, в которой пользователи развертываются в локальном развертывании и в сетевой среде.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="9a9ba-140">Цель такого подхода заключается в том, чтобы пользователи могли выполнять вход в развертывание для перенаправления к расположению их домашнего сервера независимо от того, где этот домашний сервер расположен (локально или в сети).</span><span class="sxs-lookup"><span data-stu-id="9a9ba-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="9a9ba-141">Для этого используется функция автообнаружения Microsoft Lync Server 2013 для перенаправления интерактивного пользователя в сетевую топологию.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="9a9ba-142">Для этого необходимо настроить URL-адрес автообнаружения с помощью командной консоли Lync Server и командлетов **Get-CsHostingProvider** и **Set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="9a9ba-143">Вам потребуется собрать и записать следующие развернутые атрибуты:</span><span class="sxs-lookup"><span data-stu-id="9a9ba-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="9a9ba-144">В командной консоли Lync Server введите</span><span class="sxs-lookup"><span data-stu-id="9a9ba-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="9a9ba-p105">В результатах найдите сетевого поставщика с атрибутом **ProxyFQDN**. Например, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-p105">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="9a9ba-147">Запишите значение ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="9a9ba-148">Включение Федерации на локальной панели управления Lync Server, разрешение Федерации с помощью веб-поставщика</span><span class="sxs-lookup"><span data-stu-id="9a9ba-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="9a9ba-p106">Включите федерацию для этого сетевого поставщика. По умолчанию все пользователи в сети могут использовать федерацию доменов и взаимодействовать со всеми доменами.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-p106">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="9a9ba-151">Если вы зададите заблокированные и разрешенные домены, определите домены, которые хотите явным образом разрешить или запретить.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="9a9ba-152">Для сетевой федерации вы должны спланировать исключения брандмауэра, сертификаты и записи узлов DNS (A или AAAA, если используется IPv6).</span><span class="sxs-lookup"><span data-stu-id="9a9ba-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="9a9ba-153">Кроме того, следует настроить политики федерации.</span><span class="sxs-lookup"><span data-stu-id="9a9ba-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="9a9ba-154">Дополнительные сведения см. в статье [планирование для интеграции Lync server 2013 и Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="9a9ba-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

