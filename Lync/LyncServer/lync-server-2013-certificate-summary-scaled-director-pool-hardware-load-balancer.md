---
title: Сводка по сертификатам — масштабированный пул директоров, аппаратный балансировщик нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcecbd1ec0c486e888a8c7303e450f75abf05bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="bd9c7-102">Сводка по сертификатам — масштабированный пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd9c7-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd9c7-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bd9c7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bd9c7-104">Требования к сертификатам для режиссера с помощью аппаратной подсистемы балансировки нагрузки будут использовать сертификат по умолчанию, который содержит имя субъекта и альтернативные имена субъектов для служб, которые может получать пул режиссера.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="bd9c7-105">Для каждого режиссера в пуле запрашивается сертификат.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="bd9c7-106">Кроме того, существует сертификат маркеров OAuth для проверки подлинности сервера и сервера, установленный на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="bd9c7-107">Сертификаты для масштабированного директора с помощью аппаратной подсистемы балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="bd9c7-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd9c7-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="bd9c7-108">Component</span></span></th>
<th><span data-ttu-id="bd9c7-109">Имя субъекта (SN)</span><span class="sxs-lookup"><span data-stu-id="bd9c7-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="bd9c7-110">Дополнительные имена субъектов (SAN)</span><span class="sxs-lookup"><span data-stu-id="bd9c7-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="bd9c7-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bd9c7-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd9c7-112">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bd9c7-112">Default</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd9c7-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd9c7-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="bd9c7-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd9c7-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="bd9c7-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd9c7-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="bd9c7-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd9c7-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="bd9c7-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd9c7-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="bd9c7-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd9c7-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="bd9c7-120">(Необязательно) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd9c7-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-121">Сертификаты в службе каталогов могут запрашиваться либо с помощью внутреннего управляемого центра сертификации (ЦС), либо из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="bd9c7-122">Режиссер отвечает на запросы на обратных прокси-серверах периметра или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="bd9c7-123">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="bd9c7-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c7-124">оаустокениссуер</span><span class="sxs-lookup"><span data-stu-id="bd9c7-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bd9c7-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-126">Нет записи</span><span class="sxs-lookup"><span data-stu-id="bd9c7-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="bd9c7-127">Обратите внимание, что минимальная длина ключа составляет 1024, но вы можете получить предупреждение о том, что минимальная рекомендуемая длина ключа составляет 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="bd9c7-128">Сертификат Оаустокениссуер является однозначным сертификатом для серверов с проверкой подлинности в крупномасштабной среде и может запрашиваться из внутреннего или общедоступного ЦС.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-128">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="bd9c7-129">Требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="bd9c7-129">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

