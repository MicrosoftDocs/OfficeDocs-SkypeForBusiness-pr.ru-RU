---
title: Сводка по DNS — единая консолидированная пограничная с частными IP-адресами с использованием NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c3c111ef2518d159719426dfadd6c070f246349
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="cf46d-102">Сводка по DNS — единый консолидированный край с частными IP-адресами, использующими NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf46d-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf46d-103">_**Последнее изменение темы:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="cf46d-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="cf46d-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты по сравнению с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="cf46d-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="cf46d-105">Кроме того, многие записи являются необязательными в зависимости от того, как вы настраиваете клиенты, на которых работает Lync 2013, и включена ли Федерация.</span><span class="sxs-lookup"><span data-stu-id="cf46d-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="cf46d-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013 приведены в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf46d-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="cf46d-107">Дополнительные сведения о автоматической настройке клиентов, использующих Lync 2013 если не настроено разделение DNS, раздел "Автоматическая настройка без разделения DNS-имен" в разделе [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf46d-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="cf46d-108">В следующей таблице содержится сводка по записям DNS, которые необходимы для поддержки топологии единой и консолидированной среды пограничных серверов, показанной на рисунке "Топология единой и консолидированной среды пограничных серверов".</span><span class="sxs-lookup"><span data-stu-id="cf46d-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="cf46d-109">Обратите внимание, что определенные записи DNS необходимы только для автоматической настройки клиентов Lync 2013 и Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="cf46d-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="cf46d-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, соответствующие записи автоматической настройки не нужны.</span><span class="sxs-lookup"><span data-stu-id="cf46d-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="cf46d-111">ВАЖНО! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="cf46d-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="cf46d-112">Чтобы избежать проблем с маршрутизацией, убедитесь, что в пограничных серверах есть по крайней мере два сетевых адаптера и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="cf46d-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="cf46d-113">Например, как показано в одной консолидированной пограничной топологии на рисунке [с частными IP-адресами и NAT в Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), шлюз по умолчанию будет направляться внешнему брандмауэру (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="cf46d-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="cf46d-114">Настроить два сетевых адаптера на пограничном сервере можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cf46d-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="cf46d-115">**Сетевой адаптер 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="cf46d-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="cf46d-116">Внутренний интерфейс с назначенным адресом 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="cf46d-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="cf46d-117">Не задается никакой шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf46d-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="cf46d-118">Убедитесь, что существует маршрут от сети, содержащей внутренний пограничный интерфейс, в любые сети, содержащие серверы, на которых работают клиенты Lync Server 2013 или Lync Server 2013 (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="cf46d-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="cf46d-119">**Сетевой адаптер 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="cf46d-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="cf46d-120">Этому сетевому адаптеру назначены 3 частных IP-адреса, например 10.45.16.10 для пограничного сервера доступа, 10.45.16.20 для пограничного сервера веб-конференций и 10.45.16.30 для пограничного сервера аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="cf46d-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cf46d-p104">Для всех 3 интерфейсов пограничной службы можно использовать один IP-адрес, однако это не рекомендуется. Несмотря на экономию IP-адресов, в этом случае также потребуется 3 различных номера порта для каждой службы. По умолчанию используется TCP-порт 443, который гарантирует, что большинство удаленных брандмауэров будут разрешать трафик. Изменение номеров портов (например, TCP-порт 5061 для пограничного сервера доступа, TCP-порт 444 для пограничного сервера веб-конференций и TCP-порт 443 для пограничного сервера аудио- и видеоконференций) может привести к возникновению проблем у удаленных пользователей, если брандмауэр, за которым они расположены, не разрешает трафик через порты TCP-порты 5061 и 444. Кроме того, 3 отдельных IP-адреса упрощают устранение неполадок, поскольку позволяют выполнять фильтрацию по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="cf46d-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="cf46d-126">IP-адрес пограничного сервера доступа является основным адресом, для которого в качестве шлюза по умолчанию задан интегрированный маршрутизатор (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="cf46d-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="cf46d-127">IP-адреса пограничного сервера веб-конференций и пограничного сервера аудио- и видеоконференций являются дополнительными.</span><span class="sxs-lookup"><span data-stu-id="cf46d-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="cf46d-128">Для настройки пограничного сервера с двумя сетевыми адаптерами можно выбрать один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="cf46d-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="cf46d-129">Другой вариант — использовать один сетевой адаптер для внутренней стороны и три сетевых адаптера для внешней стороны пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="cf46d-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="cf46d-130">Основным преимуществом этого варианта является отдельный сетевой адаптер для каждой службы пограничного сервера и потенциально более краткий сбор данных, когда требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="cf46d-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="cf46d-131">DNS-записи, требуемые для единой консолидированной топологии сети периметра с частными IP-адресами с использованием преобразования сетевых адресов (NAT) (пример)</span><span class="sxs-lookup"><span data-stu-id="cf46d-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf46d-132">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="cf46d-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="cf46d-133">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="cf46d-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="cf46d-134">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="cf46d-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="cf46d-135">Сопоставление с/Примечания</span><span class="sxs-lookup"><span data-stu-id="cf46d-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf46d-136">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="cf46d-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="cf46d-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="cf46d-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="cf46d-139">Внешний интерфейс пограничного сервера доступа (Contoso). Требуется для всех доменов SIP с включенными пользователями Lync.</span><span class="sxs-lookup"><span data-stu-id="cf46d-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf46d-140">Внешняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="cf46d-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="cf46d-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="cf46d-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="cf46d-143">Внешний интерфейс пограничной службы веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="cf46d-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf46d-144">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="cf46d-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="cf46d-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="cf46d-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="cf46d-147">Внешний интерфейс пограничной службы аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="cf46d-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf46d-148">Внешняя DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="cf46d-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="cf46d-149">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cf46d-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-151">Внешний интерфейс пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="cf46d-151">Access Edge external interface.</span></span> <span data-ttu-id="cf46d-152">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними клиентами.</span><span class="sxs-lookup"><span data-stu-id="cf46d-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="cf46d-153">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="cf46d-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf46d-154">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="cf46d-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="cf46d-155">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cf46d-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-157">Внешний SIP-интерфейс пограничной службы доступа. Требуется для автоматического обнаружения DNS федеративных партнеров, известных как "Allowed SIP Domain” ("Разрешенный домен SIP") (в предыдущих версиях это называлось расширенной федерацией). Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="cf46d-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf46d-158">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="cf46d-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="cf46d-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cf46d-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="cf46d-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="cf46d-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="cf46d-161">Внутренний консолидированный интерфейс пограничной службы.</span><span class="sxs-lookup"><span data-stu-id="cf46d-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="cf46d-162">Записи, представленные в предыдущей таблице, имеют расширение <EM>.net</EM> или <EM>.com</EM>, чтобы указать, в какой зоне они должны быть расположены, если не используется разделенная DNS.</span><span class="sxs-lookup"><span data-stu-id="cf46d-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="cf46d-163">Если используется разделенная DNS, все записи будут расположены в одной зоне <EM>.com</EM> и будут отличаться только версией внутренней или внешней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="cf46d-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="cf46d-164">Дополнительные сведения см в разделе "Split-мозговая служба DNS" в статье <A href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf46d-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="cf46d-165">Записи, необходимые для создания федерации</span><span class="sxs-lookup"><span data-stu-id="cf46d-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf46d-166">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="cf46d-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="cf46d-167">FQDN</span><span class="sxs-lookup"><span data-stu-id="cf46d-167">FQDN</span></span></th>
<th><span data-ttu-id="cf46d-168">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="cf46d-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="cf46d-169">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="cf46d-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf46d-170">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="cf46d-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="cf46d-171">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cf46d-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-173">Интерфейс внешнего пограничного сервера доступа SIP, необходимый для возможного автоматического обнаружения DNS федерации другими возможными федеративным клиентами, называется "Разрешенные домены SIP" (в предыдущих выпусках его названием было "улучшенная федерация"). Повторите эту процедуру для всех доменов SIP с поддержкой пользователей Lync</span><span class="sxs-lookup"><span data-stu-id="cf46d-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="cf46d-174">Эта SRV-запись необходима для мобильности и клиринговой палаты push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="cf46d-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="cf46d-175">Сводка по DNS для расширяемого протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="cf46d-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf46d-176">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="cf46d-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="cf46d-177">FQDN</span><span class="sxs-lookup"><span data-stu-id="cf46d-177">FQDN</span></span></th>
<th><span data-ttu-id="cf46d-178">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="cf46d-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="cf46d-179">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="cf46d-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf46d-180">Внешний DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="cf46d-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="cf46d-181">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="cf46d-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cf46d-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cf46d-183">Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к Пользователь с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="cf46d-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="cf46d-184">Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="cf46d-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="cf46d-185">Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</span><span class="sxs-lookup"><span data-stu-id="cf46d-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf46d-186">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="cf46d-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="cf46d-187">xmpp.contoso.com (пример)</span><span class="sxs-lookup"><span data-stu-id="cf46d-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="cf46d-188">IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</span><span class="sxs-lookup"><span data-stu-id="cf46d-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="cf46d-189">Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="cf46d-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="cf46d-190">Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="cf46d-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

