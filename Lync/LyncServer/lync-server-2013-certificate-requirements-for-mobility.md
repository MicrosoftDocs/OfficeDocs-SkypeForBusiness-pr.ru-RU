---
title: 'Lync Server 2013: требования к сертификатам для организации мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="440b9-102">Требования к сертификатам для организации мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440b9-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="440b9-103">_**Тема последнего изменения:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="440b9-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="440b9-104">Если вы разворачиваете мобильное устройство и поддерживаете автоматическое обнаружение для мобильных клиентов, необходимо включить некоторые записи альтернативных имен для субъектов в сертификаты для обеспечения защищенных подключений из мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="440b9-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="440b9-105">Необходимо включить записи альтернативных имен для субъектов для автоматического обнаружения в следующих сертификатах:</span><span class="sxs-lookup"><span data-stu-id="440b9-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="440b9-106">директоров</span><span class="sxs-lookup"><span data-stu-id="440b9-106">Director pool</span></span>

  - <span data-ttu-id="440b9-107">переднего плана</span><span class="sxs-lookup"><span data-stu-id="440b9-107">Front End pool</span></span>

  - <span data-ttu-id="440b9-108">Сертификат обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="440b9-108">Reverse proxy</span></span>

<span data-ttu-id="440b9-109">В этом разделе описаны записи альтернативных имен субъектов, необходимые для сертификатов для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="440b9-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="440b9-110">Повторное выдача сертификатов с помощью внутреннего центра сертификации обычно является простым процессом, но добавление нескольких записей альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси, может быть дорогостоящим.</span><span class="sxs-lookup"><span data-stu-id="440b9-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="440b9-111">Если у вас много доменов SIP, что значительно затрудняет Добавление альтернативных имен субъектов, вы можете настроить обратный прокси так, чтобы он использовал HTTP для первоначального запроса на обслуживание автообнаружения, вместо использования HTTPS (конфигурация по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="440b9-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="440b9-112">Подробности можно найти <A href="lync-server-2013-technical-requirements-for-mobility.md">в разделе Технические требования для мобильных устройств на Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="440b9-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="440b9-113">Требования к сертификатам пула директоров</span><span class="sxs-lookup"><span data-stu-id="440b9-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="440b9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="440b9-114">Description</span></span></th>
<th><span data-ttu-id="440b9-115">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="440b9-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="440b9-116">URL-адрес внутренней службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="440b9-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="440b9-117">SAN = линкдисковеринтернал. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="440b9-118">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="440b9-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="440b9-119">SAN = lyncdiscover. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="440b9-120">Кроме того, вы можете использовать сеть SAN = \*. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="440b9-121">Требования к сертификату пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="440b9-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="440b9-122">Описание</span><span class="sxs-lookup"><span data-stu-id="440b9-122">Description</span></span></th>
<th><span data-ttu-id="440b9-123">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="440b9-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="440b9-124">URL-адрес внутренней службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="440b9-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="440b9-125">SAN = линкдисковеринтернал. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="440b9-126">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="440b9-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="440b9-127">SAN = lyncdiscover. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="440b9-128">Кроме того, вы можете использовать сеть SAN = \*. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="440b9-129">Требования сертификата по обратному прокси (общедоступному центру сертификации)</span><span class="sxs-lookup"><span data-stu-id="440b9-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="440b9-130">Описание</span><span class="sxs-lookup"><span data-stu-id="440b9-130">Description</span></span></th>
<th><span data-ttu-id="440b9-131">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="440b9-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="440b9-132">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="440b9-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="440b9-133">SAN = lyncdiscover. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="440b9-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="440b9-134">Вы назначаете эту сеть SAN сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="440b9-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="440b9-135">В обратном прослушивателе прокси-сервера будут указаны альтернативные имена для URL-адресов внешних веб-служб (например, SAN = lyncwebextpool01. contoso. com и dirwebexternal.contoso.com, если вы развернули дополнительный режиссер).</span><span class="sxs-lookup"><span data-stu-id="440b9-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

