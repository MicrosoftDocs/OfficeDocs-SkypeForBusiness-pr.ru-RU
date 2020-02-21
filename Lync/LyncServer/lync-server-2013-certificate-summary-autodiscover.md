---
title: 'Lync Server 2013: сводка по сертификатам — автообнаружение'
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
ms.openlocfilehash: 7424d0c002e5b14335a6d0256fc72a3beff733cc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="48526-102">Сводка по сертификатам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48526-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48526-103">_**Последнее изменение темы:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="48526-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="48526-104">Служба автообнаружения Lync Server 2013 выполняется на серверах директоров и интерфейсных серверах пула, и при публикации в DNS могут использоваться клиентами Lync для обнаружения серверных и пользовательских служб.</span><span class="sxs-lookup"><span data-stu-id="48526-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="48526-105">Если вы выполняете обновление с Lync Server 2010 и не развертываете мобильность, прежде чем клиенты смогут использовать автоматическое обнаружение, необходимо изменить списки альтернативных имен субъектов сертификата на любом директоре и сервере переднего плана, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="48526-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="48526-106">Кроме того, может потребоваться изменить списки альтернативных имен субъектов для сертификатов, используемых для правил публикации внешних веб-служб на обратных прокси-серверах.</span><span class="sxs-lookup"><span data-stu-id="48526-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="48526-107">Решение о том, следует ли использовать списки альтернативных имен субъектов для обратных прокси-серверов, зависит от того, публикуется ли служба автообнаружения на порте 80 или на порте 443:</span><span class="sxs-lookup"><span data-stu-id="48526-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="48526-108">**Опубликовано на порте 80**   изменения сертификатов не требуются, если исходный запрос к службе автообнаружения проходит через порт 80.</span><span class="sxs-lookup"><span data-stu-id="48526-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="48526-109">Это связано с тем, что мобильные устройства, работающие с Lync, обращаются к обратному прокси-серверу через порт 80 извне, а затем подсоединены к директору или внешнему серверу по порту 8080 внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="48526-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="48526-110">Для получения дополнительных сведений обратитесь к разделу "исходный процесс автообнаружения с использованием порта 80" [технических требований для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="48526-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="48526-111">**Опубликовано на порте 443**   список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб, должен содержать *lyncdiscover.\< запись\> sipdomain* для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="48526-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="48526-112">Настоятельно рекомендуется использовать протокол HTTPS через HTTP.</span><span class="sxs-lookup"><span data-stu-id="48526-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="48526-113">HTTPS использует сертификаты для шифрования трафика.</span><span class="sxs-lookup"><span data-stu-id="48526-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="48526-114">HTTP не обеспечивает шифрование, а все отправляемые данные будут иметь обычный текст.</span><span class="sxs-lookup"><span data-stu-id="48526-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="48526-115">Как правило, повторное выдача сертификатов с помощью внутреннего центра сертификации является простым процессом.</span><span class="sxs-lookup"><span data-stu-id="48526-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="48526-116">Но для общедоступных сертификатов, используемых в правиле публикации веб-службы, добавление нескольких записей альтернативного имени субъекта может привести к дорогостоящему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="48526-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="48526-117">Чтобы обойти эту проблему, мы поддерживаем начальное подключение автоматического обнаружения через порт 80, который затем перенаправляется на порт 8080 на директоре или сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="48526-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48526-118">Если в вашей инфраструктуре Lync Server 2013 используются внутренние сертификаты, выданные внутренним центром сертификации (CA), и планируется поддержка беспроводного подключения к мобильным устройствам, необходимо установить корневую цепочку сертификатов из внутреннего центра сертификации. на мобильных устройствах или необходимо изменить общедоступный сертификат в вашей инфраструктуре Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48526-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="48526-119">В этом разделе описываются дополнительные альтернативные имена субъектов, необходимые для директора, сервера переднего плана и обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="48526-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="48526-120">Указываются только добавленные альтернативные имена субъектов (SAN).</span><span class="sxs-lookup"><span data-stu-id="48526-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="48526-121">Ознакомьтесь с разделами, посвященными планированию, для других операций с сертификатами.</span><span class="sxs-lookup"><span data-stu-id="48526-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="48526-122">Дополнительные сведения: [сценарии для директора в Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [сценарии для доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)и [сценарии для обратного прокси-сервера в Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="48526-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="48526-123">В следующих таблицах определены записи SAN автообнаружения для пула директоров, интерфейсного пула и обратного прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="48526-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="48526-124">Требования к сертификатам пула Директор</span><span class="sxs-lookup"><span data-stu-id="48526-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48526-125">Описание</span><span class="sxs-lookup"><span data-stu-id="48526-125">Description</span></span></th>
<th><span data-ttu-id="48526-126">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="48526-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48526-127">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="48526-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="48526-128">SAN = lyncdiscoverinternal. &lt;внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="48526-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48526-129">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="48526-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="48526-130">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="48526-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="48526-131">Обновленный сертификат с новой записью SAN назначается сертификату по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48526-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="48526-132">Кроме того, вы можете использовать сеть SAN = \*. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="48526-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="48526-133">Требования к сертификатам интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="48526-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48526-134">Описание</span><span class="sxs-lookup"><span data-stu-id="48526-134">Description</span></span></th>
<th><span data-ttu-id="48526-135">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="48526-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48526-136">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="48526-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="48526-137">SAN = lyncdiscoverinternal. &lt;внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="48526-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48526-138">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="48526-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="48526-139">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="48526-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="48526-140">Обновленный сертификат с новой записью SAN назначается сертификату по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48526-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="48526-141">Кроме того, вы можете использовать сеть SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="48526-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="48526-142">Требования к сертификатам обратного прокси-сервера (общедоступного центра сертификации)</span><span class="sxs-lookup"><span data-stu-id="48526-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48526-143">Описание</span><span class="sxs-lookup"><span data-stu-id="48526-143">Description</span></span></th>
<th><span data-ttu-id="48526-144">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="48526-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48526-145">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="48526-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="48526-146">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="48526-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="48526-147">Обновленный сертификат с новой записью SAN назначается прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="48526-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

