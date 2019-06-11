---
title: 'Lync Server 2013: сведения о сертификате — автообнаружение'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c3777f9b13dc18e3e52e80120009f93c20db3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="ebc4e-102">Сведения о сертификате: обнаружение автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebc4e-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebc4e-103">_**Тема последнего изменения:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="ebc4e-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="ebc4e-104">Служба автообнаружения Lync Server 2013 работает на серверах пула и интерфейсах, а также при публикации в DNS может использоваться клиентами Lync для поиска служб сервера и пользователей.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="ebc4e-105">Если вы обновляете приложение Lync Server 2010 и не разрешили мобильность, то перед тем как клиенты смогут использовать автоматическое обнаружение, необходимо изменить список альтернативных имен субъектов сертификата на любом сетевом сервере и на внешнем интерфейсе, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="ebc4e-106">Кроме того, может потребоваться изменить список альтернативных имен субъектов в сертификатах, используемых для использования внешних правил публикации веб-службы на обратных прокси.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="ebc4e-107">Решение о том, следует ли использовать списки альтернативных имен для субъектов в обратных прокси-серверах, зависит от того, публикуются ли служба автообнаружения для порта 80 или для порта 443:</span><span class="sxs-lookup"><span data-stu-id="ebc4e-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="ebc4e-108">**Опубликовано на порте 80**   изменения сертификата не требуются, если начальный запрос к службе автообнаружения вызывается через порт 80.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="ebc4e-109">Это связано с тем, что мобильные устройства Lync обращаются к обратному прокси-серверу на порте 80 извне, а затем подсоединены к директору или серверу переднего плана с помощью внутреннего порта 8080.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="ebc4e-110">Дополнительные сведения можно найти в разделе "начальный процесс автообнаружения с помощью порта 80" [технические требования для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="ebc4e-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="ebc4e-111">**Опубликовано на порте 443**   список альтернативных имен субъектов в сертификатах, используемых внешним правилом публикации веб-служб, должен содержаться в \*lyncdiscover.\< сипдомаин\> \* запись для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ebc4e-112">Мы настоятельно рекомендуем использовать HTTPS через HTTP.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="ebc4e-113">Протокол HTTPS использует сертификаты для шифрования трафика.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="ebc4e-114">HTTP не обеспечивает шифрование, а все отправленные данные будут представлять собой обычный текст.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="ebc4e-115">Повторное выдача сертификатов с помощью внутреннего центра сертификации обычно является простым процессом.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="ebc4e-116">Но для общедоступных сертификатов, используемых в правиле публикации веб-службы, добавление нескольких записей альтернативных имен может быть дорогостоящим.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="ebc4e-117">Для решения этой проблемы мы поддерживаем начальное подключение автоматического обнаружения через порт 80, который затем перенаправляется на порт 8080 на сервере директора или на внешнем клиенте.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebc4e-118">Если ваша инфраструктура Lync Server 2013 использует внутренние сертификаты, выданные внутренним центром сертификации (ЦС), и вы планируете поддерживать беспроводную связь с мобильными устройствами, необходимо установить либо корневую цепочку сертификатов из внутреннего ЦС. на мобильных устройствах или необходимо изменить общедоступный сертификат в инфраструктуре Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="ebc4e-119">В этой статье описаны дополнительные имена субъектов, необходимые для режиссера, сервера переднего плана и обратного прокси.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="ebc4e-120">На него ссылаются только добавленные дополнительные имена субъектов (SAN).</span><span class="sxs-lookup"><span data-stu-id="ebc4e-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="ebc4e-121">Ознакомьтесь с разделом Планирование, в котором вы найдете инструкции по использованию других операций с сертификатами.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="ebc4e-122">Дополнительные сведения можно найти [в разделе сценарии для режиссера в Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [сценарии для внешних пользователей Access в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)и [сценарии обратной прокси-сервера в Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="ebc4e-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="ebc4e-123">В следующих таблицах определяются записи автообнаружения для службы каталогов, пула интерфейсов и обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="ebc4e-124">Требования к сертификатам пула директоров</span><span class="sxs-lookup"><span data-stu-id="ebc4e-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebc4e-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ebc4e-125">Description</span></span></th>
<th><span data-ttu-id="ebc4e-126">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="ebc4e-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebc4e-127">URL-адрес внутренней службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="ebc4e-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ebc4e-128">SAN = линкдисковеринтернал. &lt;внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc4e-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc4e-129">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="ebc4e-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ebc4e-130">SAN = lyncdiscover. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc4e-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ebc4e-131">Вы назначаете новому обновленному сертификату новый элемент SAN на сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="ebc4e-132">Кроме того, вы можете использовать сеть SAN = \*. &lt;сипдомаин&gt;.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="ebc4e-133">Требования к сертификату пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="ebc4e-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebc4e-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ebc4e-134">Description</span></span></th>
<th><span data-ttu-id="ebc4e-135">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="ebc4e-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebc4e-136">URL-адрес внутренней службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="ebc4e-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ebc4e-137">SAN = линкдисковеринтернал. &lt;внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc4e-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc4e-138">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="ebc4e-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ebc4e-139">SAN = lyncdiscover. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc4e-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ebc4e-140">Вы назначаете новому обновленному сертификату новый элемент SAN на сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="ebc4e-141">Кроме того, вы можете использовать сеть SAN = \*. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc4e-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="ebc4e-142">Требования сертификата по обратному прокси (общедоступному центру сертификации)</span><span class="sxs-lookup"><span data-stu-id="ebc4e-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebc4e-143">Описание</span><span class="sxs-lookup"><span data-stu-id="ebc4e-143">Description</span></span></th>
<th><span data-ttu-id="ebc4e-144">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="ebc4e-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebc4e-145">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="ebc4e-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ebc4e-146">SAN = lyncdiscover. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc4e-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ebc4e-147">Вы назначаете новый обновленный сертификат для новой записи SAN в прослушиватель SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="ebc4e-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

