---
title: Сводка по DNS — единая консолидированная пограничная с общедоступными IP-адресами
description: Сводка по DNS — единая консолидированная пограничная с общедоступными IP-адресами.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f0787d894e741951fd220ef3b2a9fada8183b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572795"
---
# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="7d1e9-103">Сводка по DNS — единая консолидированная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1e9-103">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d1e9-104">_**Последнее изменение темы:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="7d1e9-104">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="7d1e9-105">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты по сравнению с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="7d1e9-106">Кроме того, многие записи являются необязательными в зависимости от того, как вы настраиваете клиенты, на которых работает Lync 2013, и включена ли Федерация.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="7d1e9-107">Дополнительные сведения о требованиях к службе DNS для Lync 2013 приведены в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="7d1e9-108">Дополнительные сведения о автоматической настройке клиентов, использующих Lync 2013 если не настроено разделение DNS, раздел "Автоматическая настройка без Split-Brain DNS" в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-108">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="7d1e9-109">В следующей таблице содержится сводка по записям DNS, которые необходимы для поддержки топологии единой и консолидированной среды пограничных серверов, показанной на рисунке "Топология единой и консолидированной среды пограничных серверов".</span><span class="sxs-lookup"><span data-stu-id="7d1e9-109">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="7d1e9-110">Обратите внимание, что определенные записи DNS необходимы только для автоматической настройки клиентов Lync 2013 и Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-110">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="7d1e9-111">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, соответствующие записи автоматической настройки не нужны.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="7d1e9-112">ВАЖНО! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7d1e9-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="7d1e9-113">Чтобы избежать проблем с маршрутизацией, убедитесь, что в пограничных серверах есть по крайней мере два сетевых адаптера и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="7d1e9-114">Например, как показано в одной консолидированной пограничной топологии с общедоступными IP-адресами на [одной консолидированной границе с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), шлюз по умолчанию будет указывать на внешний маршрутизатор на периметре сети Интернет или брандмауэре, который может предоставить общедоступные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-114">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="7d1e9-115">Связь Network для интерфейсов пограничного сервера является отношением маршрута, а не отношением NAT.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-115">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="7d1e9-116">Настроить два сетевых адаптера на пограничном сервере можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-116">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="7d1e9-117">**Сетевой адаптер 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="7d1e9-117">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="7d1e9-118">Внутренний интерфейс с назначенным адресом 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-118">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="7d1e9-119">Не задается никакой шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-119">No default gateway is defined.</span></span>
    
    <span data-ttu-id="7d1e9-120">Убедитесь, что существует маршрут от сети, содержащей внутренний пограничный интерфейс, в любые сети, содержащие серверы, на которых работают клиенты Lync Server 2013 или Lync Server 2013 (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-120">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="7d1e9-121">**Сетевой адаптер 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="7d1e9-121">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="7d1e9-122">Данному сетевому адаптеру назначаются три общедоступных IP-адреса, например 131.107.155.10 для пограничной службы доступа, 131.107.155.20 для пограничной службы веб-конференций и 131.107.155.30 для пограничной службы аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-122">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7d1e9-p104">Возможно, хотя не рекомендуется, использовать один IP-адрес для всех трех интерфейсов пограничных служб. Хотя при этом экономятся IP-адреса, но для каждой службы потребуются разные номера портов. Номер порта по умолчанию — 443/TCP, что гарантирует, что большинство удаленных брандмауэров будет разрешать этот трафик. Изменение значений порта, например, на 5061/TCP для пограничной службы доступа, 444/TCP для пограничной службы веб-конференций и 443/TCP для пограничной службы аудио- и видеосвязи может создать проблемы для удаленных пользователей, когда брандмауэр, за которым они находятся, не разрешит трафик через 5061/TCP и 444/TCP. Кроме того, три разных IP-адреса облегчают устранение неполадок, поскольку становится возможной фильтрация по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="7d1e9-128">Общедоступный IP-адрес пограничной службы доступа является основным, с шлюзом по умолчанию, установленным в общедоступный маршрутизатор (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-128">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="7d1e9-129">Общедоступные IP-адреса пограничных служб веб-конференций и аудио- и видеосвязи являются дополнительными в разделе **Advanced (Дополнительно)** свойств **протокола IP версии 4 (TCP/IPv4)** и **протокола IP версии 6 (TCP/IPv6)** окна **Local Area Connection Properties (Свойства подключения по локальной сети)** в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-129">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="7d1e9-130">Для настройки пограничного сервера с двумя сетевыми адаптерами можно выбрать один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="7d1e9-131">Другой вариант — использовать один сетевой адаптер для внутренней стороны и три сетевых адаптера для внешней стороны пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="7d1e9-132">Основным преимуществом этого варианта является отдельный сетевой адаптер для каждой службы пограничного сервера и потенциально более краткий сбор данных, когда требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="7d1e9-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="7d1e9-133">Записи DNS, необходимые для единой и консолидированной среды пограничных серверов с общедоступными IP-адресами (пример)</span><span class="sxs-lookup"><span data-stu-id="7d1e9-133">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d1e9-134">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="7d1e9-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7d1e9-135">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="7d1e9-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="7d1e9-136">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="7d1e9-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="7d1e9-137">Сопоставление с/Примечания</span><span class="sxs-lookup"><span data-stu-id="7d1e9-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d1e9-138">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="7d1e9-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="7d1e9-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-141">Внешний интерфейс пограничной службы доступа (Contoso). Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-141">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1e9-142">Внешняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="7d1e9-142">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-143">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-143">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-144">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="7d1e9-144">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-145">Внешний интерфейс пограничной службы веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-145">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d1e9-146">Внешняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="7d1e9-146">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-147">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-147">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-148">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="7d1e9-148">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-149">Внешний интерфейс пограничной службы аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-149">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1e9-150">Внешняя DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="7d1e9-150">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-151">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-151">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-152">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-152">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-153">Внешний интерфейс пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-153">Access Edge external interface.</span></span> <span data-ttu-id="7d1e9-154">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними клиентами.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-154">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="7d1e9-155">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-155">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d1e9-156">Внешняя DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="7d1e9-156">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-157">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-157">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-159">Внешний SIP-интерфейс пограничной службы доступа. Требуется для автоматического обнаружения DNS федеративных партнеров, известных как "Allowed SIP Domain” ("Разрешенный домен SIP") (в предыдущих версиях это называлось расширенной федерацией). Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-159">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1e9-160">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="7d1e9-160">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-161">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7d1e9-161">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-162">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="7d1e9-162">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-163">Внутренний консолидированный интерфейс пограничной службы.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-163">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="7d1e9-164">Записи, приведенные в предыдущей таблице, показаны с расширением <EM>NET</EM> или <EM>COM</EM>, чтобы подчеркнуть зону, в которой они должны размещаться, если не используется разделение DNS.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-164">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="7d1e9-165">Если используется разделение DNS, то все записи могут быть в одной зоне, и единственное отличие будет состоять в их внутренней или внешней версии.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-165">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="7d1e9-166">Дополнительные сведения см в разделе "Split-мозговая служба DNS" в статье <A href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-166">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="7d1e9-167">Записи, необходимые для создания федерации</span><span class="sxs-lookup"><span data-stu-id="7d1e9-167">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d1e9-168">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="7d1e9-168">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7d1e9-169">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="7d1e9-169">FQDN</span></span></th>
<th><span data-ttu-id="7d1e9-170">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="7d1e9-170">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="7d1e9-171">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="7d1e9-171">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d1e9-172">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="7d1e9-172">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-173">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-173">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-174">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-174">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-175">Интерфейс внешнего пограничного сервера доступа SIP, необходимый для возможного автоматического обнаружения DNS федерации другими возможными федеративным клиентами, называется "Разрешенные домены SIP" (в предыдущих выпусках его названием было "улучшенная федерация"). Повторите эту процедуру для всех доменов SIP с поддержкой пользователей Lync</span><span class="sxs-lookup"><span data-stu-id="7d1e9-175">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="7d1e9-176">Эта SRV-запись необходима для мобильности и клиринговой палаты push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="7d1e9-176">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="7d1e9-177">Сводка по DNS для расширяемого протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="7d1e9-177">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d1e9-178">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="7d1e9-178">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7d1e9-179">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="7d1e9-179">FQDN</span></span></th>
<th><span data-ttu-id="7d1e9-180">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="7d1e9-180">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="7d1e9-181">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="7d1e9-181">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d1e9-182">Внешний DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="7d1e9-182">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-183">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-183">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-184">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d1e9-184">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-185">Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к пользователю с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-185">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="7d1e9-186">Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-186">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="7d1e9-187">Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</span><span class="sxs-lookup"><span data-stu-id="7d1e9-187">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1e9-188">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="7d1e9-188">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-189">xmpp.contoso.com (пример)</span><span class="sxs-lookup"><span data-stu-id="7d1e9-189">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-190">IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</span><span class="sxs-lookup"><span data-stu-id="7d1e9-190">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="7d1e9-191">Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-191">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="7d1e9-192">Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-192">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

