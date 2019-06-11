---
title: 'Lync Server 2013: определение требований DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="f7e25-102">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7e25-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7e25-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f7e25-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f7e25-104">Для определения требований к системе доменных имен (DNS) используйте приведенную ниже блок-схему.</span><span class="sxs-lookup"><span data-stu-id="f7e25-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="f7e25-105">Изменения в накопительных обновлениях для Lync Server 2013: Февраль 2013 отмечается в том месте, где они применяются.</span><span class="sxs-lookup"><span data-stu-id="f7e25-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7e25-106">Microsoft Lync Server 2013 поддерживает использование IPv6-адресации.</span><span class="sxs-lookup"><span data-stu-id="f7e25-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="f7e25-107">Для использования IPv6-адресов необходимо также предоставить поддержку DNS для IPv6 и настроить AAAA-запись DNS hosts ("Quad-A").</span><span class="sxs-lookup"><span data-stu-id="f7e25-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="f7e25-108">В средах с использованием IPv4 и IPv6 лучше настроить и поддерживать записи узла A для IPv4 и AAAA для IPv6.</span><span class="sxs-lookup"><span data-stu-id="f7e25-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="f7e25-109">Даже если развертывание полностью перешло на IPv6, записи узлов DNS IPv4 могут потребоваться, если внешние пользователи по-прежнему используют протокол IPv4.</span><span class="sxs-lookup"><span data-stu-id="f7e25-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="f7e25-110">**Определение блок-схемы требований к DNS**</span><span class="sxs-lookup"><span data-stu-id="f7e25-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="f7e25-111">![175782ac-363e-408a-912f-8991bf152970] (images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="f7e25-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7e25-112">По умолчанию имя компьютера, не подключенного к домену, — это имя узла, а не полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f7e25-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="f7e25-113">В построителе топологии используются полные доменные имена, а не названия узлов.</span><span class="sxs-lookup"><span data-stu-id="f7e25-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="f7e25-114">Поэтому для компьютера, развертываемого в качестве пограничного сервера, не присоединенного к домену, потребуется указать DNS-суффикс.</span><span class="sxs-lookup"><span data-stu-id="f7e25-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="f7e25-115"><STRONG>Используйте только стандартные символы</STRONG> (A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам.</span><span class="sxs-lookup"><span data-stu-id="f7e25-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="f7e25-116">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="f7e25-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="f7e25-117">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-серверами и общими центрами сертификации (например, когда полное доменное имя необходимо назначить имени субъекта в сертификате).</span><span class="sxs-lookup"><span data-stu-id="f7e25-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="f7e25-118">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-configure-dns-host-records.md">Настройка записей узлов DNS для Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="f7e25-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="f7e25-119">Как клиенты Lync находят службы</span><span class="sxs-lookup"><span data-stu-id="f7e25-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="f7e25-120">Microsoft Lync 2010, Lync 2013 и Lync Mobile похожи на то, как клиент находит и обращается к службам в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7e25-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="f7e25-121">Примечательным исключением является приложение Lync из Магазина Windows, в котором используется другой процесс размещения служб.</span><span class="sxs-lookup"><span data-stu-id="f7e25-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="f7e25-122">В этом разделе приведены сведения о том, как клиенты размещает службы, сначала используется традиционный метод, использующий серии записей SRV и Host, второй — только записи службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="f7e25-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="f7e25-123">Накопительные обновления для настольных компьютеров изменяют процесс расположения DNS из Lync Server 2010 для всех клиентов, процесс запроса DNS продолжает работу до тех пор, пока не будет возвращен успешный запрос или не будет возвращено Последнее сообщение об ошибке. клиент.</span><span class="sxs-lookup"><span data-stu-id="f7e25-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="f7e25-124">Для всех клиентов, **Кроме** приложения Lync из Магазина Windows, при ПРОСМОТРЕ DNS-записи запрашиваются и возвращаются клиенту в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="f7e25-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="f7e25-125">линкдисковеринтернал. \<запись\> домена A (узла) для службы автообнаружения во внутренних веб-службах</span><span class="sxs-lookup"><span data-stu-id="f7e25-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="f7e25-126">lyncdiscover. \<запись\> домена A (узла) для службы автообнаружения во внешних веб-службах</span><span class="sxs-lookup"><span data-stu-id="f7e25-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="f7e25-127">\_сипинтерналтлс. \_протокол TCP. \<запись\> SRV домена (Локатор службы) для внутренних TLS-подключений</span><span class="sxs-lookup"><span data-stu-id="f7e25-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="f7e25-128">\_сипинтернал. \_протокол TCP. \<запись\> SRV (служба обнаружения служб) для внутренних подключений по протоколу TCP (выполняется только в том случае, если разрешен протокол TCP)</span><span class="sxs-lookup"><span data-stu-id="f7e25-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="f7e25-129">\_Установка. \_TLS. \<запись\> SRV (служба обнаружения служб) для внешних TLS-подключений</span><span class="sxs-lookup"><span data-stu-id="f7e25-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="f7e25-130">сипинтернал. \<запись\> домена A (узла) для пула или режиссера переднего плана, разрешаемые только во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="f7e25-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="f7e25-131">Установка. \<запись\> домена A (узла) для переднего плана пула или режиссера во внутренней сети или служба Edge Access, если клиент является внешним</span><span class="sxs-lookup"><span data-stu-id="f7e25-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="f7e25-132">сипекстернал. \<запись\> домена A (узла) для службы Edge Access, если клиент является внешним</span><span class="sxs-lookup"><span data-stu-id="f7e25-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="f7e25-133">Приложение Lync из Магазина Windows полностью изменяет процесс, поскольку использует две записи:</span><span class="sxs-lookup"><span data-stu-id="f7e25-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="f7e25-134">линкдисковеринтернал. \<запись\> домена A (узла) для службы автообнаружения во внутренних веб-службах</span><span class="sxs-lookup"><span data-stu-id="f7e25-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="f7e25-135">lyncdiscover. \<запись\> домена A (узла) для службы автообнаружения во внешних веб-службах</span><span class="sxs-lookup"><span data-stu-id="f7e25-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="f7e25-136">Резервы для других типов записей не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="f7e25-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="f7e25-137">Различие между методами, используемыми для новых клиентов, по сравнению с более старыми клиентами состоит в том, что служба автообнаружения становится предпочтительнее для поиска всех служб.</span><span class="sxs-lookup"><span data-stu-id="f7e25-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="f7e25-138">Когда соединение завершается успешно, служба автообнаружения возвращает все URL-адреса для домашнего пула пользователей, включая службу Mobility Service (МККС виртуальным каталогом, созданным для службы в IIS), Microsoft Lync Web App и URL-адреса веб – планировщика.</span><span class="sxs-lookup"><span data-stu-id="f7e25-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="f7e25-139">Однако URL-адрес службы внутренних мобильных устройств и внешний URL-адрес службы Mobility Service связан с полным доменным именем внешней веб-службы.</span><span class="sxs-lookup"><span data-stu-id="f7e25-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="f7e25-140">Таким образом, независимо от того, является ли мобильное устройство внутренним или внешним по отношению к сети, устройство всегда подключается к службе Mobility Service извне через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="f7e25-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="f7e25-141">Если установлены накопительные обновления для Lync Server 2013: Февраль 2013, служба автообнаружения также возвращает ссылки на Internal/УКВА, External/УКВА и УКВА.</span><span class="sxs-lookup"><span data-stu-id="f7e25-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="f7e25-142">Эти записи ссылаются на веб-компонент единой системы обмена сообщениями (УКВА).</span><span class="sxs-lookup"><span data-stu-id="f7e25-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="f7e25-143">В настоящее время используется только элемент УКВА, который предоставляет ссылку на URL-адрес для веб – компонента.</span><span class="sxs-lookup"><span data-stu-id="f7e25-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="f7e25-144">УКВА используется мобильными клиентами Lync 2013 вместо службы Mobility МККС, используемой мобильными клиентами Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f7e25-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7e25-145">При создании записей SRV важно помнить, что они должны указывать на DNS A и AAAA (при использовании записи IPv6-адресации) в том же домене, в котором создана DNS SRV-запись.</span><span class="sxs-lookup"><span data-stu-id="f7e25-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="f7e25-146">Например, если запись SRV находится в contoso.com, A и AAAA (если вы используете адресацию IPv6), она указывает на то, что она не может находиться в fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="f7e25-147">Конфигурация по умолчанию — это перенаправлять весь трафик мобильных клиентов на внешний сайт.</span><span class="sxs-lookup"><span data-stu-id="f7e25-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="f7e25-148">Вы можете изменить параметры так, чтобы возвращался только внутренний URL-адрес, если это более предпочтительно для ваших требований.</span><span class="sxs-lookup"><span data-stu-id="f7e25-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="f7e25-149">В этой конфигурации пользователи могут использовать мобильные приложения Lync на мобильных устройствах только в том случае, если они находятся в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="f7e25-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="f7e25-150">Чтобы определить такую конфигурацию, используйте командлет <STRONG>Set-ксмкксконфигуратион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f7e25-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f7e25-151">Несмотря на то, что мобильные приложения также могут подключаться к другим службам Lync Server 2013, таким как служба адресной книги, внутренние веб-запросы мобильных приложений будут переходить на внешнее полное доменное имя сайта только для службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="f7e25-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="f7e25-152">Для других запросов на обслуживание, таких как запросы адресной книги, эта конфигурация не требуется.</span><span class="sxs-lookup"><span data-stu-id="f7e25-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="f7e25-153">Мобильные устройства поддерживают Ручное обнаружение служб.</span><span class="sxs-lookup"><span data-stu-id="f7e25-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="f7e25-154">В этом случае каждый пользователь должен настроить параметры мобильного устройства с помощью полного URI внутренней и внешней службы автообнаружения, включая протокол и путь, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f7e25-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="f7e25-155">https://\<екстпулфкдн\>/аутодисковер/аутодисковерсервице.СВК/Рут для внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="f7e25-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="f7e25-156">https://\<интпулфкдн\>/аутодисковер/аутодисковер.СВК/Рут для внутреннего доступа</span><span class="sxs-lookup"><span data-stu-id="f7e25-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="f7e25-157">Мы рекомендуем использовать автоматическое обнаружение, а не Ручное обнаружение.</span><span class="sxs-lookup"><span data-stu-id="f7e25-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="f7e25-158">Однако параметры, заданные вручную, могут быть полезны при устранении проблем с подключением к мобильным устройствам.</span><span class="sxs-lookup"><span data-stu-id="f7e25-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="f7e25-159">Настройка DNS с разделением для мозгового и Lync Server</span><span class="sxs-lookup"><span data-stu-id="f7e25-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="f7e25-160">Разделение — мозг DNS известен с помощью нескольких имен, например разделенных DNS-или горизонтов расщепления.</span><span class="sxs-lookup"><span data-stu-id="f7e25-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="f7e25-161">Просто она описывает конфигурацию DNS, в которой есть две зоны DNS с одним и тем же пространством имен, но только один из внутренних запросов для зон DNS и другие внешние запросы служб зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="f7e25-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="f7e25-162">Однако многие из DNS SRV и записей, содержащихся в внутреннем DNS-сервере, не будут входить во внешний DNS-сервер, а обратное также верно.</span><span class="sxs-lookup"><span data-stu-id="f7e25-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="f7e25-163">В случаях, когда одна и та же запись DNS существует как во внутренних, так и внешних DNS (например, www.contoso.com), возвращаемый IP-адрес будет отличаться в зависимости от того, где был инициирован запрос (внутренний или внешний).</span><span class="sxs-lookup"><span data-stu-id="f7e25-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7e25-164">В настоящее время DNS с разделением "обработано" не поддерживается для мобильных устройств, а именно для LyncDiscover и Линкдисковеринтернал DNS-записей.</span><span class="sxs-lookup"><span data-stu-id="f7e25-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="f7e25-165">LyncDiscover должно быть определено на внешнем DNS-сервере, а Линкдисковеринтернал необходимо определять на внутреннем DNS-сервере.</span><span class="sxs-lookup"><span data-stu-id="f7e25-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="f7e25-166">В следующих разделах будет использоваться термин разделение — мозг DNS.</span><span class="sxs-lookup"><span data-stu-id="f7e25-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="f7e25-167">Если вы настраиваете DNS с разделением для мозгового отчета, в следующей внутренней и внешней зоне содержатся сведения о типах DNS-записей, необходимых для каждой зоны.</span><span class="sxs-lookup"><span data-stu-id="f7e25-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="f7e25-168">Дополнительные сведения можно найти [в разделе сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f7e25-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="f7e25-169">**Внутренний DNS-сервер:**</span><span class="sxs-lookup"><span data-stu-id="f7e25-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="f7e25-170">Содержит зону DNS с именем contoso.com, для которой она является удостоверяющей.</span><span class="sxs-lookup"><span data-stu-id="f7e25-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="f7e25-171">Внутренняя зона contoso.com включает в себя:</span><span class="sxs-lookup"><span data-stu-id="f7e25-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="f7e25-172">DNS A и AAAA (если используется адресация IPv6) и записи SRV для внутренней конфигурации клиента Lync Server 2013 (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f7e25-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="f7e25-173">DNS A и AAAA (если вы используете адресацию IPv6) или записи CNAME для автоматического обнаружения веб-служб Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="f7e25-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="f7e25-174">DNS A и AAAA (если вы используете записи IPv6-адресации) для имен пулов, режиссеров и режиссеров переднего плана, а также всех внутренних серверов, работающих под управлением Lync Server 2013 в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="f7e25-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="f7e25-175">DNS A и AAAA (если вы используете записи IPv6-адресации) для внутреннего интерфейса Edge каждого сервера Lync Server 2013, пограничного сервера в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="f7e25-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="f7e25-176">DNS A и AAAA (если вы используете записи IPv6-адресации) для внутреннего интерфейса каждого обратного прокси-сервера в демилитаризованной зоне (необязательно для управления обратной прокси).</span><span class="sxs-lookup"><span data-stu-id="f7e25-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="f7e25-177">Весь внутренний интерфейс EDGE сервера Lync Server 2013 в демилитаризованной зоне использует внутреннюю зону DNS для разрешения запросов в contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="f7e25-178">Все серверы Lync Server 2013 и клиенты с Lync 2013 в корпоративной сети указывают внутренним DNS-серверам для разрешения запросов в contoso.com или использование файла HOSTs на каждом пограничном сервере, а также список A и AAAA (если вы используете записи IPv6-адресации) для сервер следующего прыжка, в частности режиссер или Director VIP, серверный IP-адрес пула или стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="f7e25-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="f7e25-179">**Внешний DNS-сервер:**</span><span class="sxs-lookup"><span data-stu-id="f7e25-179">**External DNS:**</span></span>

  - <span data-ttu-id="f7e25-180">Содержит зону DNS с именем contoso.com, для которой она является удостоверяющей.</span><span class="sxs-lookup"><span data-stu-id="f7e25-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="f7e25-181">В зону External contoso.com входит:</span><span class="sxs-lookup"><span data-stu-id="f7e25-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="f7e25-182">DNS A и AAAA (если вы используете IPv6-адресацию) и записи SRV для автонастройки клиента Lync Server 2013 (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f7e25-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="f7e25-183">DNS A и AAAA (если вы используете адресацию IPv6) или записи CNAME для автоматического обнаружения веб-служб Lync Server 2013 для использования с мобильными приложениями</span><span class="sxs-lookup"><span data-stu-id="f7e25-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="f7e25-184">DNS A и AAAA (если вы используете IPv6-адресацию) и записи SRV для внешнего интерфейса EDGE на внешнем виртуальном IP-адресе (VIP) сервера Lync Server 2013, пограничного сервера или подсистемы балансировки нагрузки для оборудования в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="f7e25-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="f7e25-185">DNS A и AAAA (если вы используете записи IPv6-адресации) для внешнего интерфейса обратного прокси-сервера или VIP для пула обратных прокси-серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="f7e25-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="f7e25-186">Автоматическая настройка без разделения и мозгового DNS-сервера</span><span class="sxs-lookup"><span data-stu-id="f7e25-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="f7e25-187">С помощью DNS с разделением «расщепленные сведения» пользователь Lync Server 2013, который подписывается внутренне, может использовать преимущества автоматической настройки, \_если внутренняя зона DNS включает сипинтерналтлс. \_запись TCP SRV для каждого домена SIP, который используется.</span><span class="sxs-lookup"><span data-stu-id="f7e25-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="f7e25-188">Тем не менее, если DNS с разделением не используется, внутренняя автоматическая настройка клиентов, работающих с Lync, не будет работать, если не реализовано одно из описанных ниже решений.</span><span class="sxs-lookup"><span data-stu-id="f7e25-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="f7e25-189">Это связано с тем, что в Lync Server 2013 требуется URI пользователя SIP для соответствия домену пула переднего плана, предназначенного для автоматической настройки.</span><span class="sxs-lookup"><span data-stu-id="f7e25-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="f7e25-190">Это было также так с более ранними версиями Communicator.</span><span class="sxs-lookup"><span data-stu-id="f7e25-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="f7e25-191">Например, если у вас есть два домена SIP, требуется использовать следующие записи службы DNS (SRV):</span><span class="sxs-lookup"><span data-stu-id="f7e25-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="f7e25-192">Если пользователь подписывается как bob@contoso.com, следующая запись SRV будет работать в автоматической настройке, так как домен SIP пользователя (contoso.com) соответствует домену пула переднего плана автоматической конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f7e25-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="f7e25-193">\_сипинтерналтлс. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="f7e25-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="f7e25-195">Если пользователь входит в качестве alice@fabrikam.com, для автоматической настройки второго домена SIP будет использоваться следующая запись DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="f7e25-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="f7e25-196">\_сипинтерналтлс. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="f7e25-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="f7e25-198">Для сравнения, если пользователь выполняет вход как tim@litwareinc.com, следующая запись DNS SRV не будет работать в автоматической конфигурации, так как домен SIP клиента (litwareinc.com) не соответствует домену, в котором находится пул (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="f7e25-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="f7e25-199">\_сипинтерналтлс. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="f7e25-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="f7e25-201">Если для клиентов с Lync требуется автоматическая настройка, выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="f7e25-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="f7e25-202">**Объекты групповой политики**   используют объекты групповой политики (GPO) для заполнения нужных значений сервера.</span><span class="sxs-lookup"><span data-stu-id="f7e25-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7e25-203">Этот параметр не включает автоматическую настройку, но он автоматизирует процесс ручной настройки, поэтому при использовании такого подхода записи SRV, связанные с автоматической конфигурацией, не требуются.</span><span class="sxs-lookup"><span data-stu-id="f7e25-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="f7e25-204">**Сопоставление внутренней зоны**   . Создание зоны во внутренней службе DNS, соответствующей внешней зоне DNS (например, contoso.com), а также создание DNS a и AAAA (если вы используете IPv6-адресацию) записи, соответствующие пулу Lync Server 2013, который используется для автоматического Настройка.</span><span class="sxs-lookup"><span data-stu-id="f7e25-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="f7e25-205">Например, если пользователь размещен на pool01.contoso.net, но входит в состав Lync как bob@contoso.com, создайте внутреннюю зону DNS под названием contoso.com и внутри нее создайте запись DNS A и AAAA (если используется IPv6-адресация) для pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="f7e25-206">**Внутренняя зона**   с закреплением в случае, если вы создаете полную зону в внутреннем DNS, вы можете создать зоны с закреплением (то есть выделенные), соответствующие записям SRV, которые требуются для автоматической настройки, и заполнять эти параметры. зоны с помощью dnscmd. exe.</span><span class="sxs-lookup"><span data-stu-id="f7e25-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="f7e25-207">Dnscmd. exe является обязательным, так как пользовательский интерфейс DNS не поддерживает создание зон с точками на основе контактов.</span><span class="sxs-lookup"><span data-stu-id="f7e25-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="f7e25-208">Например, если домен SIP является contoso.com и у вас есть пул переднего плана под названием pool01, который содержит два сервера переднего плана, вам понадобятся следующие зоны и записи в своем внутреннем DNS-коде:</span><span class="sxs-lookup"><span data-stu-id="f7e25-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="f7e25-209">Если в вашей среде есть второй домен SIP (например, fabrikam.com), вам понадобятся следующие зоны контактов и записи в своем внутреннем DNS:</span><span class="sxs-lookup"><span data-stu-id="f7e25-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="f7e25-210">Полное доменное имя пула переднего плана появляется дважды, но с двумя различными IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="f7e25-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="f7e25-211">Это объясняется тем, что используется балансировка нагрузки DNS, но при использовании аппаратной балансировки нагрузки может быть только одна запись пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f7e25-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="f7e25-212">Кроме того, значения полного доменного имени пула переднего плана меняются между примерами contoso.com и fabrikam.com, но IP-адреса остаются прежними.</span><span class="sxs-lookup"><span data-stu-id="f7e25-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="f7e25-213">Это связано с тем, что пользователи, войдя в какой-либо домен SIP, используют для автоматической настройки один и тот же пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f7e25-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="f7e25-214">Дополнительные сведения можно найти в статье в блоге в формате DMTF, в [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)разделе "Автоматическая настройка и разделение DNS" программы Communicator-мозгового блога.</span><span class="sxs-lookup"><span data-stu-id="f7e25-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7e25-215">Содержимое всех блогов и их URL-адреса могут быть изменены без уведомления.</span><span class="sxs-lookup"><span data-stu-id="f7e25-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="f7e25-216">Настройка системы доменных имен (DNS) для аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="f7e25-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="f7e25-217">Чтобы настроить DNS для перенаправления веб-трафика Lync Server 2013 на сайты аварийного восстановления и переходов на другой ресурс, необходимо использовать поставщик DNS, поддерживающий Жеоднс.</span><span class="sxs-lookup"><span data-stu-id="f7e25-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="f7e25-218">Вы можете настроить записи DNS для веб-сайта, чтобы обеспечить поддержку аварийного восстановления, чтобы функции, использующие веб-службы, продолжались, даже если весь пул переднего плана выйдет из нее.</span><span class="sxs-lookup"><span data-stu-id="f7e25-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="f7e25-219">Это средство аварийного восстановления поддерживает автообнаружение (URL-адрес Lyncdiscover), подходящие и простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f7e25-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="f7e25-220">Вы определяете и настраиваете дополнительные DNS-узел (A и AAAA, если используется IPv6) для внутренних и внешних решений веб-служб в поставщике Жеоднс.</span><span class="sxs-lookup"><span data-stu-id="f7e25-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="f7e25-221">Ниже указаны Объединенные пулы, географически распределенные и Жеоднс, которые поддерживаются поставщиком с помощью функции циклического перенаправления DNS или настроены на использование Pool1 в качестве основного, и отработки отказа в Pool2 в случае потери связи или сбоя оборудования.</span><span class="sxs-lookup"><span data-stu-id="f7e25-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7e25-222">Жеоднс запись (пример)</span><span class="sxs-lookup"><span data-stu-id="f7e25-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="f7e25-223">Записи пула (пример)</span><span class="sxs-lookup"><span data-stu-id="f7e25-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="f7e25-224">Записи CNAME (пример)</span><span class="sxs-lookup"><span data-stu-id="f7e25-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="f7e25-225">Параметры DNS (выберите один вариант)</span><span class="sxs-lookup"><span data-stu-id="f7e25-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7e25-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-229">Псевдоним Meet.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-230">Псевдоним Meet.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-231">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-232">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e25-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-236">Псевдоним Meet.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-237">Псевдоним Meet.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-238">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-239">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7e25-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-243">Псевдоним Dialin.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-244">Псевдоним Dialin.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-245">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-246">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e25-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-250">Псевдоним Dialin.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-251">Псевдоним Dialin.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-252">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-253">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7e25-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-257">Псевдоним Lyncdiscoverinternal.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-258">Псевдоним Lyncdiscoverinternal.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-259">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-260">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e25-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-264">Псевдоним Lyncdiscover.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-265">Псевдоним Lyncdiscover.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-266">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-267">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7e25-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-271">Псевдоним Scheduler.contoso.com для Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-272">Псевдоним Scheduler.contoso.com для Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-273">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-274">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e25-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-278">Псевдоним Scheduler.contoso.com для Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f7e25-279">Псевдоним Scheduler.contoso.com для Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f7e25-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f7e25-280">Циклический перебор между пулами</span><span class="sxs-lookup"><span data-stu-id="f7e25-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f7e25-281">Использовать Primary, подключиться к получателю в случае сбоя</span><span class="sxs-lookup"><span data-stu-id="f7e25-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="f7e25-282">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="f7e25-282">DNS Load Balancing</span></span>

<span data-ttu-id="f7e25-283">Балансировка нагрузки DNS обычно реализуется на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="f7e25-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="f7e25-284">Приложение (например, клиент, работающее под управлением Lync) пытается подключиться к серверу в пуле, подключив один из IP-адресов, возвращенных из DNS A и AAAA (если используется IPv6-адресация), для запроса на запись полного доменного имени пула (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f7e25-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="f7e25-285">Например, если у вас есть три внешних сервера в пуле с именем pool01.contoso.com, произойдет следующее:</span><span class="sxs-lookup"><span data-stu-id="f7e25-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="f7e25-286">Клиенты, использующие Lync, запрашивают DNS для pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="f7e25-287">Запрос возвращает три IP-адреса и кэширует их следующим образом (необязательно в указанном порядке):</span><span class="sxs-lookup"><span data-stu-id="f7e25-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="f7e25-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="f7e25-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="f7e25-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="f7e25-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="f7e25-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="f7e25-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="f7e25-291">Клиент пытается установить подключение по протоколу TCP к одному из IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f7e25-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="f7e25-292">Если это не удается, клиент попытается выполнить следующий IP-адрес в кэше.</span><span class="sxs-lookup"><span data-stu-id="f7e25-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="f7e25-293">Если подключение TCP успешно установлено, клиент согласует TLS для подключения к основному регистратору на pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7e25-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="f7e25-294">Если клиент пытается выполнить все кэшированные записи без успешного соединения, пользователь получит уведомление о том, что серверы Lync Server 2013 в настоящее время недоступны.</span><span class="sxs-lookup"><span data-stu-id="f7e25-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7e25-295">Балансировка нагрузки на основе DNS отличается от циклического перегрузки DNS (DNS RR), который, как правило, указывает на балансировку нагрузки, используя DNS для предоставления другого порядка IP-адресов, соответствующих серверам в пуле.</span><span class="sxs-lookup"><span data-stu-id="f7e25-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="f7e25-296">Обычно DNS RR включает распределение нагрузки, но не включает отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="f7e25-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="f7e25-297">Например, если при попытке подключения к одному IP-адресу, возвращенному DNS A и AAAA (при использовании адресации IPv6) происходит сбой, происходит сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="f7e25-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="f7e25-298">Таким образом, служба DNS-цикл по отдельности является менее надежной, чем балансировка нагрузки на основе DNS.</span><span class="sxs-lookup"><span data-stu-id="f7e25-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="f7e25-299">С помощью средства балансировки нагрузки DNS вы можете использовать DNS-циклы в сочетании.</span><span class="sxs-lookup"><span data-stu-id="f7e25-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="f7e25-300">Балансировка нагрузки DNS используется для указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f7e25-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="f7e25-301">Балансировка нагрузки Серверная SIP на сервер пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="f7e25-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="f7e25-302">Приложения для балансировки нагрузки служб приложений (укас), такие как автосекретарь конференц-связи, группа ответа и метод приостановки</span><span class="sxs-lookup"><span data-stu-id="f7e25-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="f7e25-303">Предотвращение новых подключений к укас приложениям (также называемым "стоком")</span><span class="sxs-lookup"><span data-stu-id="f7e25-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="f7e25-304">Балансировка нагрузки весь трафик между клиентами и серверами пограничного сервера между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="f7e25-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="f7e25-305">Балансировка нагрузки DNS не может использоваться для указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f7e25-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="f7e25-306">Веб-трафик между клиентом и сервером в директории или на серверах переднего плана</span><span class="sxs-lookup"><span data-stu-id="f7e25-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="f7e25-307">Балансировка нагрузки DNS и федеративный трафик:</span><span class="sxs-lookup"><span data-stu-id="f7e25-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="f7e25-308">Если DNS SRV-запрос возвращает несколько DNS-записей, служба Edge Access всегда выберет DNS SRV-запись с наименьшим порядковым номером и наивысшим числовым весом.</span><span class="sxs-lookup"><span data-stu-id="f7e25-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="f7e25-309">Задача "Проектирование интернет-ресурсов" принудительно определяет расположение служб DNS (DNS SRV) " <http://www.ietf.org/rfc/rfc2782.txt> указывает на то, что при наличии нескольких записей DNS SRV используется приоритет, а затем вес.</span><span class="sxs-lookup"><span data-stu-id="f7e25-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="f7e25-310">Например, запись DNS SRV A имеет вес 20 и приоритет 40, а запись DNS SRV B имеет вес 10 и приоритет 50.</span><span class="sxs-lookup"><span data-stu-id="f7e25-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="f7e25-311">Будет выбрана запись DNS SRV с приоритетом 40.</span><span class="sxs-lookup"><span data-stu-id="f7e25-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="f7e25-312">Следующие правила применяются к выбору DNS SRV-записей.</span><span class="sxs-lookup"><span data-stu-id="f7e25-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="f7e25-313">Приоритет считается первым.</span><span class="sxs-lookup"><span data-stu-id="f7e25-313">Priority is considered first.</span></span> <span data-ttu-id="f7e25-314">Клиент должен попытаться связаться с конечным узлом, определенным DNS SRV-записью с минимальным номером приоритета, к которому он может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="f7e25-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="f7e25-315">Целевые объекты с одинаковым приоритетом должны быть предприняты в порядке, определенном полем веса.</span><span class="sxs-lookup"><span data-stu-id="f7e25-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="f7e25-316">Поле «Толщина» задает относительный вес для операций с одинаковым приоритетом.</span><span class="sxs-lookup"><span data-stu-id="f7e25-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="f7e25-317">Более крупные весовые значения должны быть заданы пропорционально более высокой вероятностью выбора.</span><span class="sxs-lookup"><span data-stu-id="f7e25-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="f7e25-318">Администраторам DNS следует использовать толщину 0, если не выбран ни один сервер.</span><span class="sxs-lookup"><span data-stu-id="f7e25-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="f7e25-319">При наличии записей, содержащих значения веса больше 0, записи с весом 0 должны иметь очень малую вероятность выбора.</span><span class="sxs-lookup"><span data-stu-id="f7e25-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="f7e25-320">Если возвращено несколько записей DNS SRV с одинаковыми приоритетами и весовыми коэффициентами, служба Edge Access выберет запись SRV, полученную первой на DNS-сервере.</span><span class="sxs-lookup"><span data-stu-id="f7e25-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

