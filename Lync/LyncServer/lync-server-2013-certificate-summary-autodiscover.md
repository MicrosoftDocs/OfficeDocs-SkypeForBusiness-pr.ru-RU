---
title: 'Lync Server 2013: сводка по сертификатам — автообнаружение'
description: 'Lync Server 2013: сводка по сертификатам — автообнаружение.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574715"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="05f35-103">Сводка по сертификатам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05f35-103">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05f35-104">_**Последнее изменение темы:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="05f35-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="05f35-105">Служба автообнаружения Lync Server 2013 выполняется на серверах директоров и интерфейсных серверах пула, и при публикации в DNS могут использоваться клиентами Lync для обнаружения серверных и пользовательских служб.</span><span class="sxs-lookup"><span data-stu-id="05f35-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="05f35-106">Если вы выполняете обновление с Lync Server 2010 и не развертываете мобильность, прежде чем клиенты смогут использовать автоматическое обнаружение, необходимо изменить списки альтернативных имен субъектов сертификата на любом директоре и сервере переднего плана, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="05f35-106">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="05f35-107">Кроме того, может потребоваться изменить списки альтернативных имен субъектов для сертификатов, используемых для правил публикации внешних веб-служб на обратных прокси-серверах.</span><span class="sxs-lookup"><span data-stu-id="05f35-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="05f35-108">Решение о том, следует ли использовать списки альтернативных имен субъектов для обратных прокси-серверов, зависит от того, публикуется ли служба автообнаружения на порте 80 или на порте 443:</span><span class="sxs-lookup"><span data-stu-id="05f35-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="05f35-109">**Опубликовано на порте 80**     Если исходный запрос к службе автообнаружения поступает через порт 80, изменения сертификатов не требуются.</span><span class="sxs-lookup"><span data-stu-id="05f35-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="05f35-110">Это связано с тем, что мобильные устройства, работающие с Lync, обращаются к обратному прокси-серверу через порт 80 извне, а затем подсоединены к директору или внешнему серверу по порту 8080 внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="05f35-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="05f35-111">Для получения дополнительных сведений обратитесь к разделу "исходный процесс автообнаружения с использованием порта 80" [технических требований для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="05f35-111">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="05f35-112">**Опубликовано на порте 443**     Список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб, должен содержать \*lyncdiscover. \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="05f35-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="05f35-113">запись для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="05f35-113">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="05f35-114">Настоятельно рекомендуется использовать протокол HTTPS через HTTP.</span><span class="sxs-lookup"><span data-stu-id="05f35-114">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="05f35-115">HTTPS использует сертификаты для шифрования трафика.</span><span class="sxs-lookup"><span data-stu-id="05f35-115">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="05f35-116">HTTP не обеспечивает шифрование, а все отправляемые данные будут иметь обычный текст.</span><span class="sxs-lookup"><span data-stu-id="05f35-116">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="05f35-117">Как правило, повторное выдача сертификатов с помощью внутреннего центра сертификации является простым процессом.</span><span class="sxs-lookup"><span data-stu-id="05f35-117">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="05f35-118">Но для общедоступных сертификатов, используемых в правиле публикации веб-службы, добавление нескольких записей альтернативного имени субъекта может привести к дорогостоящему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="05f35-118">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="05f35-119">Чтобы обойти эту проблему, мы поддерживаем начальное подключение автоматического обнаружения через порт 80, который затем перенаправляется на порт 8080 на директоре или сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="05f35-119">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05f35-120">Если в вашей инфраструктуре Lync Server 2013 используются внутренние сертификаты, выданные внутренним центром сертификации (CA), и планируется поддержка беспроводного подключения к мобильным устройствам, на мобильных устройствах необходимо установить корневую цепочку сертификатов из внутреннего ЦС или необходимо изменить общедоступный сертификат в вашей инфраструктуре Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05f35-120">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="05f35-121">В этом разделе описываются дополнительные альтернативные имена субъектов, необходимые для директора, сервера переднего плана и обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="05f35-121">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="05f35-122">Указываются только добавленные альтернативные имена субъектов (SAN).</span><span class="sxs-lookup"><span data-stu-id="05f35-122">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="05f35-123">Ознакомьтесь с разделами, посвященными планированию, для других операций с сертификатами.</span><span class="sxs-lookup"><span data-stu-id="05f35-123">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="05f35-124">Дополнительные сведения: [сценарии для директора в Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [сценарии для доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)и [сценарии для обратного прокси-сервера в Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="05f35-124">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="05f35-125">В следующих таблицах определены записи SAN автообнаружения для пула директоров, интерфейсного пула и обратного прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="05f35-125">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="05f35-126">Требования к сертификатам пула Директор</span><span class="sxs-lookup"><span data-stu-id="05f35-126">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05f35-127">Описание</span><span class="sxs-lookup"><span data-stu-id="05f35-127">Description</span></span></th>
<th><span data-ttu-id="05f35-128">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="05f35-128">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05f35-129">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="05f35-129">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="05f35-130">SAN = lyncdiscoverinternal. &lt; внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="05f35-130">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05f35-131">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="05f35-131">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="05f35-132">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="05f35-132">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="05f35-133">Обновленный сертификат с новой записью SAN назначается сертификату по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05f35-133">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="05f35-134">Кроме того, вы можете использовать сеть SAN = \*. &lt; sipdomain &gt; .</span><span class="sxs-lookup"><span data-stu-id="05f35-134">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="05f35-135">Требования к сертификатам интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="05f35-135">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05f35-136">Описание</span><span class="sxs-lookup"><span data-stu-id="05f35-136">Description</span></span></th>
<th><span data-ttu-id="05f35-137">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="05f35-137">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05f35-138">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="05f35-138">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="05f35-139">SAN = lyncdiscoverinternal. &lt; внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="05f35-139">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05f35-140">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="05f35-140">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="05f35-141">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="05f35-141">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="05f35-142">Обновленный сертификат с новой записью SAN назначается сертификату по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05f35-142">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="05f35-143">Кроме того, вы можете использовать сеть SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="05f35-143">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="05f35-144">Требования к сертификатам обратного прокси-сервера (общедоступного центра сертификации)</span><span class="sxs-lookup"><span data-stu-id="05f35-144">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05f35-145">Описание</span><span class="sxs-lookup"><span data-stu-id="05f35-145">Description</span></span></th>
<th><span data-ttu-id="05f35-146">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="05f35-146">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05f35-147">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="05f35-147">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="05f35-148">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="05f35-148">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="05f35-149">Обновленный сертификат с новой записью SAN назначается прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="05f35-149">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

