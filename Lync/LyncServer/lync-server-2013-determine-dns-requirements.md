---
title: 'Lync Server 2013: определение требований DNS'
description: 'Lync Server 2013: определение требований DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a4bfe682314fa4f91826f4bf85f8eac36ea91d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550915"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="1b848-103">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b848-103">Determine DNS requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b848-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1b848-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1b848-105">Для получения сведений о требованиях к службе доменных имен (DNS) используйте следующую блок-схему.</span><span class="sxs-lookup"><span data-stu-id="1b848-105">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="1b848-106">Изменения накопительных обновлений для Lync Server 2013:2013 февраля указаны там, где они применяются.</span><span class="sxs-lookup"><span data-stu-id="1b848-106">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1b848-107">Microsoft Lync Server 2013 поддерживает использование IPv6-адресов.</span><span class="sxs-lookup"><span data-stu-id="1b848-107">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="1b848-108">Для использования IPv6-адресов вам потребуется настроить DNS для поддержки протокола IP версии 6, а также настроить DNS-записи AAAA (также называемые "четыре A").</span><span class="sxs-lookup"><span data-stu-id="1b848-108">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="1b848-109">При наличии развертываний, в которых совместно используются IPv4- и IPv6-адреса, рекомендуется настроить как записи A для IP версии 4, так и записи AAAA для IP версии 6.</span><span class="sxs-lookup"><span data-stu-id="1b848-109">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="1b848-110">Даже если развертывание полностью переведено на протокол IP версии 6, DNS-записи IP версии 4 могут потребоваться в случае, если внешние пользователи используют протокол IP версии 4.</span><span class="sxs-lookup"><span data-stu-id="1b848-110">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="1b848-111">**Определение последовательности требований DNS**</span><span class="sxs-lookup"><span data-stu-id="1b848-111">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="1b848-112">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="1b848-112">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1b848-113">По умолчанию имя компьютера, который не присоединен к домену, является именем узла, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="1b848-113">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1b848-114">В построителе топологий используются полные доменные имена, а не имена узлов.</span><span class="sxs-lookup"><span data-stu-id="1b848-114">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="1b848-115">Поэтому необходимо настроить суффикс DNS имени компьютера для развертывания в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="1b848-115">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1b848-116"><STRONG>Используйте только стандартные символы </STRONG> (включая A-Z, a-z, 0-9 и дефисы) при назначении полных доменных имен серверов Lync, пограничных серверов и пулов.</span><span class="sxs-lookup"><span data-stu-id="1b848-116"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="1b848-117">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="1b848-117">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1b848-118">Нестандартные символы, включенные в полное доменное имя, часто не поддерживаются внешними системами DNS и открытыми центрами сертификации (например, когда полное доменное имя необходимо назначить SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="1b848-118">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="1b848-119">Дополнительные сведения см. в статье <A href="lync-server-2013-configure-dns-host-records.md">Настройка записей узла DNS для Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="1b848-119">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="1b848-120">Обнаружение служб клиентами Lync</span><span class="sxs-lookup"><span data-stu-id="1b848-120">How Lync Clients Locate Services</span></span>

<span data-ttu-id="1b848-121">Microsoft Lync 2010, Lync 2013 и Lync Mobile аналогичны тем, как клиент находит и получает доступ к службам в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b848-121">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="1b848-122">Важным исключением является приложение Lync в магазине Windows, в котором используется другой процесс размещения службы.</span><span class="sxs-lookup"><span data-stu-id="1b848-122">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="1b848-123">В этом разделе описывается два сценария, в которых клиенты находят службы, сначала традиционный метод с использованием ряда записей SRV и Host, второй с использованием только записей службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="1b848-123">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="1b848-124">Накопительные пакеты обновления для настольных клиентов изменяют процесс размещения DNS-имен с Lync Server 2010 для всех клиентов, процесс запроса DNS продолжается до тех пор, пока не будет возвращен успешный запрос или не будет исчерпан список возможных DNS-записей, а клиенту возвращается последняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="1b848-124">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="1b848-125">Для всех клиентов, **Кроме** приложения Lync Windows в магазине при поиске DNS, записи SRV запрашиваются и возвращаются клиенту в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="1b848-125">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="1b848-126">lyncdiscoverinternal. \<domain\>     Запись (узла) для службы автообнаружения во внутренних веб-службах</span><span class="sxs-lookup"><span data-stu-id="1b848-126">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="1b848-127">lyncdiscover. \<domain\>     Запись (узла) для службы автообнаружения во внешних веб-службах</span><span class="sxs-lookup"><span data-stu-id="1b848-127">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="1b848-128">\_сипинтерналтлс. \_ TCP. \<domain\>     Запись SRV (локатор служб) для внутренних подключений TLS</span><span class="sxs-lookup"><span data-stu-id="1b848-128">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="1b848-129">\_сипинтернал. \_ TCP. \<domain\>     Запись SRV (локатор служб) для внутренних подключений TCP (выполняется только в том случае, если разрешен протокол TCP)</span><span class="sxs-lookup"><span data-stu-id="1b848-129">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="1b848-130">\_SIP. \_ TLS. \<domain\>     Запись SRV (Locator службы) для внешних подключений TLS</span><span class="sxs-lookup"><span data-stu-id="1b848-130">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="1b848-131">сипинтернал. \<domain\>     Запись (узла) для внешнего интерфейса пула или директора, разрешаемая только во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="1b848-131">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="1b848-132">SIP. \<domain\>     Запись (узла) для внешнего интерфейса пула или директора во внутренней сети или пограничного сервера доступа, когда клиент является внешним</span><span class="sxs-lookup"><span data-stu-id="1b848-132">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="1b848-133">сипекстернал. \<domain\>     Запись (узла) для службы пограничного доступа, когда клиент является внешним</span><span class="sxs-lookup"><span data-stu-id="1b848-133">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="1b848-134">Приложение Lync Windows Store полностью изменяет процесс, так как использует две записи:</span><span class="sxs-lookup"><span data-stu-id="1b848-134">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="1b848-135">lyncdiscoverinternal. \<domain\>     Запись (узла) для службы автообнаружения во внутренних веб-службах</span><span class="sxs-lookup"><span data-stu-id="1b848-135">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="1b848-136">lyncdiscover. \<domain\>     Запись (узла) для службы автообнаружения во внешних веб-службах</span><span class="sxs-lookup"><span data-stu-id="1b848-136">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="1b848-137">Резервные элементы для других типов записей отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="1b848-137">There is no fallback to the other record types.</span></span>

<span data-ttu-id="1b848-138">Разница между методами, используемыми для новых клиентов, по сравнению с устаревшими клиентами, заключается в том, что служба автообнаружения становится предпочтительным методом обнаружения всех служб.</span><span class="sxs-lookup"><span data-stu-id="1b848-138">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="1b848-139">При успешном завершении подключения служба автообнаружения возвращает все URL-адреса веб-служб для домашнего пула пользователя, включая службу Mobility Service (которая называется MCX виртуальным каталогом, созданным для службы в IIS), Microsoft Lync Web App и URL-адреса веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="1b848-139">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="1b848-140">Однако и внутренний, и внешний URL-адреса службы Mobility Service связаны с внешним полным доменным именем веб-служб.</span><span class="sxs-lookup"><span data-stu-id="1b848-140">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="1b848-141">Следовательно, независимо от того, является ли мобильное устройство внутренним или внешним по отношению к сети, устройство всегда будет подключаться к службе Mobility Service через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="1b848-141">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="1b848-142">При установке накопительных обновлений для Lync Server 2013: Февраль 2013 служба автообнаружения также возвращает ссылки на Internal/UCWA, External/UCWA и UCWA.</span><span class="sxs-lookup"><span data-stu-id="1b848-142">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="1b848-143">UCWA  это веб-компонент Unified Communications Web API.</span><span class="sxs-lookup"><span data-stu-id="1b848-143">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="1b848-144">В настоящее время используется только запись UCWA и предоставляется ссылка на URL-адрес веб-компонента.</span><span class="sxs-lookup"><span data-stu-id="1b848-144">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="1b848-145">UCWA используется мобильными клиентами Lync 2013, а не службой Mobility Service MCX, используемой мобильными клиентами Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="1b848-145">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b848-146">При создании записей SRV важно помнить, что они должны указывать на DNS-записи A и AAAA (при использовании IPv6-адресов) в том же домене, в котором была создана DNS-запись SRV.</span><span class="sxs-lookup"><span data-stu-id="1b848-146">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="1b848-147">Например, если запись SRV находится в contoso.com, то запись A и AAAA (при использовании адресации IPv6) указывает на то, что она не может находиться в fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-147">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="1b848-148">Настройка по умолчанию заключается в том, чтобы направить весь трафик мобильного клиента через внешний сайт.</span><span class="sxs-lookup"><span data-stu-id="1b848-148">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="1b848-149">Вы можете изменить параметры так, чтобы возвращался только внутренний URL-адрес, если это более предпочтительно для ваших требований.</span><span class="sxs-lookup"><span data-stu-id="1b848-149">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="1b848-150">В этой конфигурации пользователи смогут воспользоваться приложениями Lync Mobile на мобильных устройствах только при нахождении в сети организации.</span><span class="sxs-lookup"><span data-stu-id="1b848-150">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="1b848-151">Чтобы определить эту конфигурацию, используйте командлет <STRONG>Set – CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1b848-151">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1b848-152">Несмотря на то, что мобильные приложения также могут подключаться к другим службам Lync Server 2013, таким как служба адресной книги, внутренние веб-запросы мобильных приложений переходить на внешнее полное доменное имя веб-сайта только для службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="1b848-152">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="1b848-153">Для остальных запросов служб, например запросов адресной книги, эта конфигурация не требуется.</span><span class="sxs-lookup"><span data-stu-id="1b848-153">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="1b848-154">Мобильные устройства поддерживают Ручное обнаружение служб.</span><span class="sxs-lookup"><span data-stu-id="1b848-154">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="1b848-155">В этом случае каждому пользователю потребуется настроить параметры мобильного устройства с полным внутренним и внешним универсальными кодами ресурса (URI) службы автообнаружения, включая протокол и путь, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1b848-155">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="1b848-156">https:// \<ExtPoolFQDN\> /autodiscover/autodiscoverservice.svc/root для внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="1b848-156">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="1b848-157">https:// \<IntPoolFQDN\> /autodiscover/Autodiscover.svc/root для внутреннего доступа</span><span class="sxs-lookup"><span data-stu-id="1b848-157">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="1b848-158">Вместо обнаружения вручную Майкрософт рекомендует использовать автоматическое обнаружение.</span><span class="sxs-lookup"><span data-stu-id="1b848-158">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="1b848-159">Однако обнаружение вручную позволяет устранять неполадки подключения мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="1b848-159">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="1b848-160">Настройка Split-Brain DNS с помощью Lync Server</span><span class="sxs-lookup"><span data-stu-id="1b848-160">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="1b848-p112">Разделенную службу доменных имен (DNS) иногда называют комбинированной DNS или расщеплением горизонта DNS. Под этим названием понимают конфигурацию DNS, в которой две зоны DNS имеют одно пространство имен, но при этом одна зона DNS обслуживает только внутренние запросы, а вторая зона DNS — только внешние запросы. Однако при этом большинство записей расположения службы (SRV) и записей A, содержащихся во внутренней DNS, будут отсутствовать во внешней DNS и наоборот. Если одна DNS-запись содержится во внутренней и внешней зоне DNS (например, www.contoso.com), возвращаемый IP-адрес будет зависеть от того, какая зона является источником запроса (внутренняя или внешняя).</span><span class="sxs-lookup"><span data-stu-id="1b848-p112">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS. Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests. However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true. In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1b848-165">В настоящее время Split-Brain DNS не поддерживается для мобильных устройств, или точнее, записи DNS LyncDiscover и LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="1b848-165">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="1b848-166">Запись LyncDiscover должна быть определена на внешнем DNS-сервере, а запись LyncDiscoverInternal — на внутреннем.</span><span class="sxs-lookup"><span data-stu-id="1b848-166">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="1b848-167">В этом разделе будет использоваться термин разделенная DNS.</span><span class="sxs-lookup"><span data-stu-id="1b848-167">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="1b848-168">Ниже приведены сводные данные о типах DNS-записей, требуемых для внутренней и внешней зоны, используемые при настройке разделенной DNS.</span><span class="sxs-lookup"><span data-stu-id="1b848-168">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="1b848-169">Дополнительные сведения см. [в статье сценарии для доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1b848-169">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="1b848-170">**Внутренняя DNS:**</span><span class="sxs-lookup"><span data-stu-id="1b848-170">**Internal DNS:**</span></span>

  - <span data-ttu-id="1b848-171">Содержит доверенную зону DNS contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-171">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="1b848-172">Внутренняя зона contoso.com содержит:</span><span class="sxs-lookup"><span data-stu-id="1b848-172">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="1b848-173">DNS-записи A и AAAA (при использовании IPv6-адресов) и записи SRV для внутренней автоконфигурации Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1b848-173">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="1b848-174">DNS-записи A и AAAA (при использовании IPv6-адресов) или записи CNAME для автоматического обнаружения веб-служб Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1b848-174">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="1b848-175">DNS-записи A и AAAA (при использовании IPv6-адресов) для имени пула переднего плана, директора или директора, а также всех внутренних серверов, на которых работает Lync Server 2013 в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="1b848-175">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="1b848-176">DNS-записи A и AAAA (при использовании IPv6-адресов) для внутреннего внутреннего интерфейса каждого Lync Server 2013, пограничный сервер в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="1b848-176">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="1b848-177">DNS-записи A и AAAA (при использовании IPv6-адресов) для внутреннего интерфейса каждого обратного прокси-сервера в сети периметра (необязательно для управления обратным прокси-сервером).</span><span class="sxs-lookup"><span data-stu-id="1b848-177">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="1b848-178">Все внутренние пограничные интерфейсы Lync Server 2013 для пограничного сервера в сети периметра используют внутреннюю зону DNS для разрешения запросов к contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-178">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="1b848-179">Все серверы Lync Server 2013 и клиенты, работающие под управлением Lync 2013 в корпоративной сети, направляют внутренние DNS-серверы для разрешения запросов к contoso.com или используют файл HOSTs на каждом пограничном сервере, а также список A и AAAA (при использовании IPv6-адресов) для сервера следующего прыжка, а именно для директоров и директоров (при использовании IPv6-виртуального IP-адреса). или Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1b848-179">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="1b848-180">**Внешняя DNS:**</span><span class="sxs-lookup"><span data-stu-id="1b848-180">**External DNS:**</span></span>

  - <span data-ttu-id="1b848-181">Содержит доверенную зону DNS contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-181">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="1b848-182">Внешняя зона contoso.com содержит:</span><span class="sxs-lookup"><span data-stu-id="1b848-182">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="1b848-183">DNS-записи A и AAAA (при использовании IPv6-адресов) и записи SRV для автонастройки клиента Lync Server 2013 (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1b848-183">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="1b848-184">DNS-записи A и AAAA (при использовании IPv6-адресов) или CNAME-записи для автоматического обнаружения веб-служб Lync Server 2013 для использования с мобильным подключением</span><span class="sxs-lookup"><span data-stu-id="1b848-184">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="1b848-185">DNS-записи A и AAAA (при использовании IPv6-адресов) и записи SRV для внешнего интерфейса пограничного внешнего интерфейса каждого Lync Server 2013, пограничный сервер или виртуальный IP-адрес аппаратного балансировщика нагрузки в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="1b848-185">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="1b848-186">DNS-записи A и AAAA (при использовании IPv6-адресов) для внешнего интерфейса обратного прокси-сервера или виртуального IP-адреса пула обратных прокси-серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="1b848-186">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="1b848-187">Автоматическая настройка без разделенной DNS</span><span class="sxs-lookup"><span data-stu-id="1b848-187">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="1b848-188">Используя разделенный DNS, пользователь Lync Server 2013, который подписывается внутренним образом, может воспользоваться преимуществами автоматической настройки, если внутренняя зона DNS содержит объект \_ сипинтерналтлс. \_ запись TCP SRV для каждого домена SIP, который используется.</span><span class="sxs-lookup"><span data-stu-id="1b848-188">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="1b848-189">Тем не менее, если вы не используете разделенный DNS, внутренняя автоматическая настройка клиентов, работающих с Lync, будет недоступна, пока не будет реализован один из способов, описанных далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1b848-189">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="1b848-190">Это связано с тем, что Lync Server 2013 требует URI SIP пользователя в соответствии с доменом пула переднего плана, предназначенного для автоматической настройки.</span><span class="sxs-lookup"><span data-stu-id="1b848-190">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="1b848-191">Это также относится к более ранним версиям Communicator.</span><span class="sxs-lookup"><span data-stu-id="1b848-191">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="1b848-192">Например, при использовании двух доменов SIP потребуются следующие записи службы DNS (SRV):</span><span class="sxs-lookup"><span data-stu-id="1b848-192">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="1b848-193">Если пользователь выполняет вход с учетной записью bob@contoso.com, то для автоматической настройки достаточно добавить следующую запись SRV, поскольку домен SIP пользователя (contoso.com) совпадает с доменом автоматической настройки интерфейсного пула:</span><span class="sxs-lookup"><span data-stu-id="1b848-193">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="1b848-194">\_сипинтерналтлс. \_ tcp.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-194">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="1b848-195">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-195">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="1b848-196">Если пользователь выполняет вход с учетной записью alice@fabrikam.com, то для автоматической настройки второго домена SIP необходимо использовать следующую DNS-запись SRV.</span><span class="sxs-lookup"><span data-stu-id="1b848-196">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="1b848-197">\_сипинтерналтлс. \_ tcp.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-197">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="1b848-198">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1b848-198">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="1b848-199">Для сравнения: если пользователь выполняет вход с учетной записью tim@litwareinc.com, то для автоматической настройки нельзя использовать следующую DNS-запись SRV, поскольку домен SIP клиента (litwareinc.com) не совпадает с доменом, в котором находится пул (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="1b848-199">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="1b848-200">\_сипинтерналтлс. \_ tcp.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-200">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="1b848-201">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1b848-201">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="1b848-202">Если для клиентов, работающих с Lync, необходима автоматическая настройка, выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="1b848-202">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="1b848-203">**Объекты**     групповой политики Используйте объекты групповой политики (GPO), чтобы заполнить правильные значения сервера.</span><span class="sxs-lookup"><span data-stu-id="1b848-203">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b848-204">Этот вариант не включает автоматическую настройку, однако он автоматизирует процесс ручной настройки, поэтому при использовании этого варианта записи SRV, связанные с автоматической настройкой, не требуются.</span><span class="sxs-lookup"><span data-stu-id="1b848-204">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="1b848-205">**Совпадающая Внутренняя зона**     Создайте зону во внутреннем DNS-сервере, которая соответствует внешней зоне DNS (например, contoso.com), и создайте DNS-записи A и AAAA (при использовании IPv6-адресов), соответствующие пулу Lync Server 2013, используемому для автоматической настройки.</span><span class="sxs-lookup"><span data-stu-id="1b848-205">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="1b848-206">Например, если пользователь размещен в pool01.contoso.net, но подписывается в Lync как bob@contoso.com, создайте внутреннюю зону DNS с именем contoso.com и внутри нее, создайте запись DNS A и AAAA (при использовании адресации IPv6) для pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-206">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="1b848-207">**Внутренняя зона**     с точки зрения ПИН-кода Если вы создаете всю зону в внутреннем DNS, вы можете создать зоны ПИН-кодов (то есть выделенные), соответствующие записям SRV, которые необходимы для автоматической настройки, и заполнить эти зоны с помощью dnscmd.exe.</span><span class="sxs-lookup"><span data-stu-id="1b848-207">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="1b848-208">Средство dnscmd.exe является обязательным, поскольку пользовательский интерфейс DNS не поддерживает создание точно заданных зон.</span><span class="sxs-lookup"><span data-stu-id="1b848-208">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="1b848-209">Например, при наличии домена SIP contoso.com и интерфейсного пула pool01, который содержит два сервера переднего плана, вам потребуются следующие точно определенные зоны и записи A во внутренней DNS:</span><span class="sxs-lookup"><span data-stu-id="1b848-209">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="1b848-210">Если ваша среда содержит второй домен SIP (например, fabrikam.com), вам потребуются следующие точно определенные зоны и записи A во внутренней DNS:</span><span class="sxs-lookup"><span data-stu-id="1b848-210">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="1b848-p121">Полное доменное имя интерфейсного пула показано дважды, но с разными IP-адресами. Это связано с использованием балансировки нагрузки на DNS. Однако при использовании аппаратной балансировки нагрузки будет доступна только одна запись интерфейсного пула. Кроме того, значения полных доменных имен интерфейсного пула разные в примерах contoso.com и fabrikam.com, но IP-адреса остаются одинаковыми. Это связано с тем, что пользователи, выполняющие вход с любого домена SIP, используют для автоматической настройки один и тот же интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="1b848-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="1b848-215">Дополнительные сведения см. в статье DMTF Blog, "Автоматическая настройка Communicator и Split-Brain DNS" [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .</span><span class="sxs-lookup"><span data-stu-id="1b848-215">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b848-216">Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="1b848-216">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="1b848-217">Настройка DNS для аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="1b848-217">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="1b848-218">Чтобы настроить DNS для перенаправления веб-трафика Lync Server 2013 в аварийное восстановление и сайты для отработки отказа, необходимо использовать поставщик DNS, поддерживающий GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="1b848-218">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="1b848-219">Вы можете настроить записи DNS для поддержки аварийного восстановления, чтобы функции, использующие веб-службы, продолжали работать даже при отключении всего пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1b848-219">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="1b848-220">Эта функция аварийного восстановления поддерживает простые URL-адреса автообнаружения (URL-адрес Lyncdiscover), собрания и телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="1b848-220">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="1b848-p123">Определите и настройте дополнительные записи узлов DNS (A и AAAA, если используется IPv6) для внутреннего и внешнего разрешения веб-служб у поставщика GeoDNS. В приведенном ниже примере предполагается, что существуют географически разнесенные спаренные пулы и поставщик либо поддерживает GeoDNS с помощью циклического перебора DNS, либо настроен на использование пула Pool1 в качестве основного и пула Pool2 — для отработки отказа в случае потери связи или сбоя оборудования.</span><span class="sxs-lookup"><span data-stu-id="1b848-p123">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b848-223">Запись GeoDNS (пример)</span><span class="sxs-lookup"><span data-stu-id="1b848-223">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="1b848-224">Записи пула (пример)</span><span class="sxs-lookup"><span data-stu-id="1b848-224">Pool records (example)</span></span></th>
<th><span data-ttu-id="1b848-225">Записи CNAME (пример)</span><span class="sxs-lookup"><span data-stu-id="1b848-225">CNAME records (example)</span></span></th>
<th><span data-ttu-id="1b848-226">Параметры DNS (выберите один вариант)</span><span class="sxs-lookup"><span data-stu-id="1b848-226">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b848-227">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-227">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-228">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-228">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-229">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-229">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-230">Псевдоним Meet.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-230">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-231">Псевдоним Meet.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-231">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-232">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-232">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-233">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-233">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b848-234">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-234">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-235">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-235">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-236">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-236">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-237">Псевдоним Meet.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-237">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-238">Псевдоним Meet.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-238">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-239">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-239">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-240">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-240">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b848-241">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-241">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-242">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-242">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-243">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-243">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-244">Псевдоним Dialin.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-244">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-245">Псевдоним Dialin.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-245">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-246">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-246">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-247">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-247">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b848-248">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-248">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-249">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-249">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-250">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-250">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-251">Псевдоним Dialin.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-251">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-252">Псевдоним Dialin.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-252">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-253">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-253">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-254">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-254">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b848-255">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-255">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-256">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-256">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-257">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-257">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-258">Псевдоним Lyncdiscoverinternal.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-258">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-259">Псевдоним Lyncdiscoverinternal.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-259">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-260">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-260">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-261">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-261">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b848-262">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-262">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-263">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-263">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-264">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-264">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-265">Псевдоним Lyncdiscover.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-265">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-266">Псевдоним Lyncdiscover.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-266">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-267">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-267">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-268">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-268">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b848-269">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-269">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-270">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-270">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-271">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-271">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-272">Псевдоним Scheduler.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-272">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-273">Псевдоним Scheduler.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-273">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-274">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-274">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-275">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-275">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b848-276">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-276">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-277">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-277">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-278">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-278">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-279">Псевдоним Scheduler.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-279">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1b848-280">Псевдоним Scheduler.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b848-280">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1b848-281">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="1b848-281">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1b848-282">Используйте основной, в случае сбоя подключитесь к дополнительному</span><span class="sxs-lookup"><span data-stu-id="1b848-282">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="1b848-283">Балансировка нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="1b848-283">DNS Load Balancing</span></span>

<span data-ttu-id="1b848-284">Балансировка нагрузки на DNS обычно реализуется на уровне приложений.</span><span class="sxs-lookup"><span data-stu-id="1b848-284">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="1b848-285">Приложение (например, клиент, на котором запущен Lync) пытается подключиться к серверу в пуле, подключив один из IP-адресов, возвращенных из DNS A и AAAA (если используется IPv6-адресация), для записи полного доменного имени пула (FQDN).</span><span class="sxs-lookup"><span data-stu-id="1b848-285">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="1b848-286">Например, при наличии трех серверов переднего плана в пуле pool01.contoso.com выполняются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1b848-286">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="1b848-287">Клиенты, на которых выполняется Lync Query DNS для pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-287">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="1b848-288">Запрос возвращает 3 IP-адреса и кэширует их следующим образом (не обязательно в этом порядке):</span><span class="sxs-lookup"><span data-stu-id="1b848-288">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="1b848-289">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="1b848-289">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="1b848-290">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="1b848-290">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="1b848-291">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="1b848-291">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="1b848-p126">Клиент пытается установить подключение TCP к одному из IP-адресов. Если не удается установить подключение, клиент берет следующий IP-адрес из кэша.</span><span class="sxs-lookup"><span data-stu-id="1b848-p126">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses. If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="1b848-294">Если подключение TCP успешно установлено, клиент согласует TLS для подключения к основному регистратору на pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1b848-294">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="1b848-295">Если клиент пытается выполнить все кэшированные записи без успешного подключения, пользователь получает уведомление о том, что в данный момент нет доступных серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b848-295">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b848-p127">Балансировка нагрузки на DNS отличается от циклического перебора DNS (DNS RR), который обычно относится к балансировке нагрузки с помощью DNS для обеспечения другого порядка IP-адресов, соответствующих серверам в пуле. Как правило, циклический перебор DNS обеспечивает только распределение нагрузки, но не отработку отказа. Например, если подключение к одному IP-адресу, возвращаемому запросом DNS-записи A и AAAA (при использовании IPv6-адресов), завершается с ошибкой, подключение разрывается. Следовательно, циклический перебор DNS является менее надежным, чем балансировка нагрузки на DNS. Вы можете использовать циклический перебор DNS вместе с балансировкой нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="1b848-p127">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool. Typically DNS RR only enables load distribution, but does not enable failover. For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails. Therefore, DNS round robin by itself is less reliable than DNS-based load balancing. You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="1b848-301">Балансировка нагрузки на DNS используется в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="1b848-301">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="1b848-302">Балансировка нагрузки SIP "сервер-сервер" до пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="1b848-302">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="1b848-303">Приложения балансировки нагрузки Unified Communications Application Services (UCAS), например автосекретарь, группа ответа и парковка. вызовов</span><span class="sxs-lookup"><span data-stu-id="1b848-303">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="1b848-304">Запрет новых подключений к приложениям UCAS (также называемое "сток").</span><span class="sxs-lookup"><span data-stu-id="1b848-304">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="1b848-305">Балансировка нагрузки всего трафика "клиент-сервер" между клиентами и пограничными серверами.</span><span class="sxs-lookup"><span data-stu-id="1b848-305">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="1b848-306">Балансировка нагрузки на DNS не может использоваться для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="1b848-306">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="1b848-307">Веб-трафик "клиент-сервер" до Директора или серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1b848-307">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="1b848-308">Балансировка нагрузки на DNS и федеративный трафик:</span><span class="sxs-lookup"><span data-stu-id="1b848-308">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="1b848-309">Если DNS SRV-запрос возвращает несколько DNS-записей, служба пограничного доступа всегда выбирает запись DNS SRV с наименьшим числовым приоритетом и высшим числовым весом.</span><span class="sxs-lookup"><span data-stu-id="1b848-309">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="1b848-310">Задача по разработке в Интернете принудительно заменяет документ "DNS RR для указания расположения служб (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> указывает на то, что при наличии нескольких записей DNS SRV используется приоритет, сначала используется приоритет, а затем — вес.</span><span class="sxs-lookup"><span data-stu-id="1b848-310">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="1b848-311">Например, запись DNS SRV A имеет вес 20 и приоритет 40, а запись DNS SRV B имеет вес 10 и приоритет 50.</span><span class="sxs-lookup"><span data-stu-id="1b848-311">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="1b848-312">Будет выбрана запись DNS SRV с приоритетом 40.</span><span class="sxs-lookup"><span data-stu-id="1b848-312">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="1b848-313">К выделению записей SRV DNS применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="1b848-313">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="1b848-314">Приоритет считается первым.</span><span class="sxs-lookup"><span data-stu-id="1b848-314">Priority is considered first.</span></span> <span data-ttu-id="1b848-315">Клиент должен попытаться связаться с конечным узлом, определенным DNS SRV-записью с наименьшим порядковым номером, к которому он может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="1b848-315">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="1b848-316">Целевые объекты с одинаковым приоритетом должны быть выполнены в порядке, определенном полем веса.</span><span class="sxs-lookup"><span data-stu-id="1b848-316">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="1b848-317">Поле Weight указывает относительный вес для записей с одинаковым приоритетом.</span><span class="sxs-lookup"><span data-stu-id="1b848-317">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="1b848-318">Более крупные весовые значения должны быть заданы пропорционально высокой вероятности выбора.</span><span class="sxs-lookup"><span data-stu-id="1b848-318">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="1b848-319">Администраторы DNS должны использовать вес 0 при отсутствии выбранных серверов.</span><span class="sxs-lookup"><span data-stu-id="1b848-319">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="1b848-320">При наличии записей, которые имеют значение веса больше 0, для записей с весом 0 необходимо выбрать очень малую вероятность.</span><span class="sxs-lookup"><span data-stu-id="1b848-320">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="1b848-321">При получении нескольких DNS-записей SRV с равным приоритетом и весом пограничная служба доступа выберет запись SRV, которая была получена от DNS-сервера первой.</span><span class="sxs-lookup"><span data-stu-id="1b848-321">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

