---
title: 'Lync Server 2013: сводка по DNS — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 269d5a687baba53ed0bd60d4854b79643f23f0e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532126"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="4d0b7-102">Сводка по DNS — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d0b7-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d0b7-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4d0b7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4d0b7-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты по сравнению с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="4d0b7-105">Кроме того, многие записи являются необязательными в зависимости от того, как вы настраиваете клиенты, на которых работает Lync 2013, и включена ли Федерация.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="4d0b7-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013 приведены в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="4d0b7-107">Для получения дополнительных сведений о настройке автоматической настройки клиентов Lync 2013 если DNS с разделением не настроена, ознакомьтесь с разделом "Автоматическая настройка без разделения DNS", чтобы [определить требования к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="4d0b7-108">В следующей таблице содержится сводка по записям DNS, которые необходимы для поддержки топологии единой и консолидированной среды пограничных серверов, показанной на рисунке "Топология единой и консолидированной среды пограничных серверов".</span><span class="sxs-lookup"><span data-stu-id="4d0b7-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="4d0b7-109">Обратите внимание, что определенные записи DNS необходимы только для автоматической настройки клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="4d0b7-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, связанные записи не нужны.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="4d0b7-111">ВАЖНО! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4d0b7-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="4d0b7-112">Чтобы избежать проблем с маршрутизацией, убедитесь, что в пограничных серверах есть по крайней мере два сетевых адаптера и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="4d0b7-113">Например, как показано в масштабируемом консолидированном пограничных подразделении [, балансировка нагрузки DNS с частными IP-адресами, использующими NAT в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), шлюз по умолчанию указывает на внешний брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="4d0b7-114">Настроить два сетевых адаптера на пограничном сервере можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="4d0b7-115">**Сетевой адаптер 1 — узел 1 (внутренний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="4d0b7-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="4d0b7-116">Внутренний интерфейс с назначенным адресом 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="4d0b7-117">Не задается никакой шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="4d0b7-118">Убедитесь, что существует маршрут от сети, содержащей внутренний пограничный интерфейс, в любые сети, содержащие серверы, на которых работают клиенты Lync Server 2013 или Lync Server 2013 (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="4d0b7-119">**Сетевой адаптер 1 — узел 2 (внутренний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="4d0b7-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="4d0b7-120">Назначается внутренний интерфейс с IP-адресом 172.25.33.11.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="4d0b7-121">Не задается никакой шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="4d0b7-122">Убедитесь, что существует маршрут от сети, содержащей внутренний пограничный интерфейс, в любые сети, содержащие серверы, на которых работают клиенты Lync Server 2013 или Lync Server 2013 (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="4d0b7-123">**Сетевой адаптер 2 — узел 1 (внешний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="4d0b7-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="4d0b7-124">Данному сетевому адаптеру назначаются три частных IP-адреса, например 10.45.16.10 для пограничной службы доступа, 10.45.16.20 для пограничной службы веб-конференций и 10.45.16.30 для пограничной службы аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d0b7-p104">Возможно, хотя не рекомендуется, использовать один IP-адрес для всех трех интерфейсов пограничных служб. Хотя при этом экономятся IP-адреса, но для каждой службы потребуются разные номера портов. Номер порта по умолчанию — 443/TCP, что гарантирует, что большинство удаленных брандмауэров будет разрешать этот трафик. Изменение значений порта, например, на 5061/TCP для пограничной службы доступа, 444/TCP для пограничной службы веб-конференций и 443/TCP для пограничной службы аудио- и видеосвязи может создать проблемы для удаленных пользователей, когда брандмауэр, за которым они находятся, не разрешит трафик через 5061/TCP и 444/TCP. Кроме того, три разных IP-адреса облегчают устранение неполадок, поскольку становится возможной фильтрация по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="4d0b7-130">Общедоступный IP-адрес пограничной службы доступа является основным, с шлюзом по умолчанию, установленным в интегрированный маршрутизатор (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="4d0b7-131">Частные IP-адреса пограничных служб веб-конференций и аудио- и видеосвязи являются дополнительными в разделе **Advanced (Дополнительно)** свойств **протокола IP версии 4 (TCP/IPv4)** и **протокола IP версии 6 (TCP/IPv6)** окна **Local Area Connection Properties (Свойства подключения по локальной сети)** в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="4d0b7-132">**Сетевой адаптер 2 — узел 2 (внешний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="4d0b7-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="4d0b7-133">Данному сетевому адаптеру назначаются три частных IP-адреса, например 10.45.16.11 для пограничной службы доступа, 10.45.16.21 для пограничной службы веб-конференций и 10.45.16.31 для пограничной службы аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="4d0b7-134">Общедоступный IP-адрес пограничной службы доступа является основным, с шлюзом по умолчанию, установленным в интегрированный маршрутизатор (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="4d0b7-135">Частные IP-адреса пограничных служб веб-конференций и аудио- и видеосвязи являются дополнительными в разделе **Advanced (Дополнительно)** свойств **протокола IP версии 4 (TCP/IPv4)** и **протокола IP версии 6 (TCP/IPv6)** окна **Local Area Connection Properties (Свойства подключения по локальной сети)** в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4d0b7-136">Для настройки пограничного сервера с двумя сетевыми адаптерами можно выбрать один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="4d0b7-137">Другой вариант — использовать один сетевой адаптер для внутренней стороны и три сетевых адаптера для внешней стороны пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="4d0b7-138">Основным преимуществом этого варианта является отдельный сетевой адаптер для каждой службы пограничного сервера и потенциально более краткий сбор данных, когда требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="4d0b7-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="4d0b7-139">Записи DNS, необходимые для масштабированной и консолидированной среды пограничных серверов, балансировки нагрузки на DNS с частными IP-адресами, использующими NAT (пример)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0b7-140">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="4d0b7-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4d0b7-141">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="4d0b7-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4d0b7-142">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="4d0b7-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4d0b7-143">Сопоставление с/Примечания</span><span class="sxs-lookup"><span data-stu-id="4d0b7-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0b7-144">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="4d0b7-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-146">131.107.155.10 и 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="4d0b7-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-147">Внешний интерфейс пограничной службы доступа (Contoso). Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0b7-148">Внешняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="4d0b7-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-150">131.107.155.20 и 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="4d0b7-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-151">Внешний интерфейс пограничной службы веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0b7-152">Внешняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="4d0b7-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-154">131.107.155.30 и 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="4d0b7-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-155">Внешний интерфейс пограничной службы аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0b7-156">Внешняя DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="4d0b7-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-157">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-159">Внешний интерфейс пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-159">Access Edge external interface.</span></span> <span data-ttu-id="4d0b7-160">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними клиентами.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="4d0b7-161">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0b7-162">Внешняя DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="4d0b7-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-163">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-p107">Внешний SIP-интерфейс пограничной службы доступа. Требуется для автоматического обнаружения DNS федеративных партнеров, известных как "Allowed SIP Domain” ("Разрешенный домен SIP") (в предыдущих версиях это называлось расширенной федерацией). Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0b7-168">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="4d0b7-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4d0b7-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-170">172.25.33.10 и 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="4d0b7-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-171">Внутренний интерфейс консолидированного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4d0b7-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="4d0b7-172">Записи, необходимые для создания федерации</span><span class="sxs-lookup"><span data-stu-id="4d0b7-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0b7-173">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="4d0b7-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4d0b7-174">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="4d0b7-174">FQDN</span></span></th>
<th><span data-ttu-id="4d0b7-175">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="4d0b7-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4d0b7-176">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="4d0b7-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0b7-177">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="4d0b7-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-178">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-180">Интерфейс внешнего пограничного сервера доступа SIP, необходимый для возможного автоматического обнаружения DNS федерации другими возможными федеративным клиентами, называется "Разрешенные домены SIP" (в предыдущих выпусках его названием было "улучшенная федерация"). Повторите эту процедуру для всех доменов SIP с поддержкой пользователей Lync</span><span class="sxs-lookup"><span data-stu-id="4d0b7-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="4d0b7-181">Эта SRV-запись необходима для мобильности и клиринговой палаты push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="4d0b7-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4d0b7-182">Сводка по DNS — возможность подключения к общедоступным службам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="4d0b7-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0b7-183">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="4d0b7-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4d0b7-184">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="4d0b7-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4d0b7-185">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="4d0b7-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4d0b7-186">Сопоставление с/Примечания</span><span class="sxs-lookup"><span data-stu-id="4d0b7-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0b7-187">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="4d0b7-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-189">Интерфейс пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="4d0b7-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-190">Внешний интерфейс пограничной службы доступа (Contoso)По необходимости повторяйте для всех доменов SIP, где есть пользователи с включенной поддержкой Lync</span><span class="sxs-lookup"><span data-stu-id="4d0b7-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4d0b7-191">Сводка по DNS для расширяемого протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="4d0b7-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0b7-192">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="4d0b7-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4d0b7-193">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="4d0b7-193">FQDN</span></span></th>
<th><span data-ttu-id="4d0b7-194">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="4d0b7-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4d0b7-195">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="4d0b7-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0b7-196">Внешний DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="4d0b7-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-197">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0b7-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-199">Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к пользователю с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="4d0b7-200">Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="4d0b7-201">Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</span><span class="sxs-lookup"><span data-stu-id="4d0b7-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0b7-202">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="4d0b7-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-203">xmpp.contoso.com (пример)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-204">IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</span><span class="sxs-lookup"><span data-stu-id="4d0b7-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="4d0b7-205">Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="4d0b7-206">Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="4d0b7-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

