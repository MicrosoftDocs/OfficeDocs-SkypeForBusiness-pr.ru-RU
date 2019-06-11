---
title: 'Lync Server 2013: сводка по сертификатам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="bd79d-102">Сводка по сертификатам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd79d-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd79d-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="bd79d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="bd79d-104">Требования к сертификатам для режиссера с балансировкой нагрузки DNS и аппаратной подсистемой балансировки нагрузки будут использовать сертификат по умолчанию с именем субъекта и дополнительными именами для служб, которые может получать руководитель.</span><span class="sxs-lookup"><span data-stu-id="bd79d-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="bd79d-105">Для каждого режиссера в пуле запрашивается сертификат.</span><span class="sxs-lookup"><span data-stu-id="bd79d-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="bd79d-106">Важно помнить, что подсистема балансировки нагрузки аппаратных средств обеспечивает балансировку нагрузки только трафик из обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="bd79d-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="bd79d-107">Кроме того, существует сертификат маркеров OAuth для проверки подлинности сервера и сервера, установленный на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="bd79d-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="bd79d-108">Сертификаты для режиссера</span><span class="sxs-lookup"><span data-stu-id="bd79d-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd79d-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="bd79d-109">Component</span></span></th>
<th><span data-ttu-id="bd79d-110">Имя субъекта (SN)</span><span class="sxs-lookup"><span data-stu-id="bd79d-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="bd79d-111">Дополнительные имена субъектов (SAN)</span><span class="sxs-lookup"><span data-stu-id="bd79d-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="bd79d-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bd79d-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd79d-113">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bd79d-113">Default</span></span></p></td>
<td><p><span data-ttu-id="bd79d-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd79d-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bd79d-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd79d-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="bd79d-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd79d-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="bd79d-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd79d-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="bd79d-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd79d-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="bd79d-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd79d-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="bd79d-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd79d-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="bd79d-121">(Необязательно) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd79d-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bd79d-122">Сертификаты в службе каталогов могут запрашиваться либо с помощью внутреннего управляемого центра сертификации (ЦС), либо из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="bd79d-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="bd79d-123">Режиссер отвечает на запросы на обратных прокси-серверах периметра или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bd79d-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="bd79d-124">Внутренние клиенты не будут использовать режиссер.</span><span class="sxs-lookup"><span data-stu-id="bd79d-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="bd79d-125">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="bd79d-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd79d-126">Оаустокениссуер</span><span class="sxs-lookup"><span data-stu-id="bd79d-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="bd79d-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd79d-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bd79d-128">Нет записи</span><span class="sxs-lookup"><span data-stu-id="bd79d-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="bd79d-129">Обратите внимание, что минимальная длина ключа составляет 1024, но вы можете получить предупреждение о том, что минимальная рекомендуемая длина ключа составляет 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="bd79d-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="bd79d-130">Сертификат Оаустокениссуер является однозначным сертификатом для серверов с проверкой подлинности в крупномасштабной среде и может запрашиваться из внутреннего или общедоступного ЦС.</span><span class="sxs-lookup"><span data-stu-id="bd79d-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="bd79d-131">Требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="bd79d-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

