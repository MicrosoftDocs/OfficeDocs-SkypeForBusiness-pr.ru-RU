---
title: Сводка по сертификатам — масштабируемый пул директоров, аппаратный балансировщик нагрузки
description: Сводка по сертификатам — масштабируемый пул директоров, аппаратный балансировщик нагрузки.
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
ms.openlocfilehash: 08abc37940cd41a29d6620cfc0a2a801de4a8e38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572235"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="279d8-103">Сводка по сертификатам — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="279d8-103">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="279d8-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="279d8-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="279d8-105">Требования к сертификатам для директора с аппаратной подсистемой балансировки нагрузки будут использовать сертификат по умолчанию с именем субъекта и альтернативными именами субъектов для служб, которые может получить пул директоров.</span><span class="sxs-lookup"><span data-stu-id="279d8-105">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="279d8-106">Для каждого директора в пуле запрашивается сертификат.</span><span class="sxs-lookup"><span data-stu-id="279d8-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="279d8-107">Кроме того, существует сертификат маркера OAuth для проверки подлинности сервера на сервере, установленный на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="279d8-107">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="279d8-108">Сертификаты для масштабируемого директора с использованием аппаратного балансировщика нагрузки</span><span class="sxs-lookup"><span data-stu-id="279d8-108">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279d8-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="279d8-109">Component</span></span></th>
<th><span data-ttu-id="279d8-110">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="279d8-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="279d8-111">Альтернативные имена субъектов</span><span class="sxs-lookup"><span data-stu-id="279d8-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="279d8-112">Comments</span><span class="sxs-lookup"><span data-stu-id="279d8-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279d8-113">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="279d8-113">Default</span></span></p></td>
<td><p><span data-ttu-id="279d8-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="279d8-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="279d8-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="279d8-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="279d8-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="279d8-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="279d8-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="279d8-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="279d8-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="279d8-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="279d8-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="279d8-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="279d8-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="279d8-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="279d8-121">(Дополнительно) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="279d8-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="279d8-122">Сертификаты директора могут запрашиваться как из внутреннего управляемого центра сертификации, так и из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="279d8-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="279d8-123">Режиссер отвечает на запросы от обратного прокси-сервера в сети периметра или от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="279d8-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="279d8-124">Или запись с подстановочными знаками для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="279d8-124">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279d8-125">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="279d8-125">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="279d8-126">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="279d8-126">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="279d8-127">Без записи</span><span class="sxs-lookup"><span data-stu-id="279d8-127">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="279d8-128">Обратите внимание, что минимальная длина ключа равна 1024, однако может возникнуть предупреждение, что рекомендуемая минимальная длина равна 2048 битам.</span><span class="sxs-lookup"><span data-stu-id="279d8-128">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="279d8-p102">Сертификат OAuthTokenIssuer — это специализированный сертификат для проверки подлинности серверов в крупномасштабной среде, который можно запросить из внутреннего или из общего центра сертификации. Этот сертификат является обязательным.</span><span class="sxs-lookup"><span data-stu-id="279d8-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

