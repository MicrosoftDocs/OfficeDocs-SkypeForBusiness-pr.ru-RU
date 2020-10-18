---
title: 'Lync Server 2013: сводка по сертификатам, балансировка нагрузки на DNS и HLB'
description: 'Lync Server 2013: сводка по сертификатам — служба DNS и балансировка нагрузки HLB.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a89975af16b6e39625677f787d3726f00c76c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575975"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="860b6-103">Сводка по сертификатам: Балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="860b6-103">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860b6-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="860b6-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="860b6-105">Требования к сертификатам для директора с балансировкой нагрузки на DNS и аппаратным подсистемным подсистемой балансировки нагрузки будут использовать сертификат по умолчанию с именем субъекта и альтернативными именами субъектов для служб, которые может получить директор.</span><span class="sxs-lookup"><span data-stu-id="860b6-105">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="860b6-106">Для каждого директора в пуле запрашивается сертификат.</span><span class="sxs-lookup"><span data-stu-id="860b6-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="860b6-107">Важно помнить о том, что аппаратный балансировщик нагрузки — балансировка нагрузки только трафик из обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="860b6-107">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="860b6-108">Кроме того, существует сертификат маркера OAuth для проверки подлинности сервера на сервере, установленный на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="860b6-108">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="860b6-109">Сертификаты для Директора</span><span class="sxs-lookup"><span data-stu-id="860b6-109">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="860b6-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="860b6-110">Component</span></span></th>
<th><span data-ttu-id="860b6-111">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="860b6-111">Subject name (SN)</span></span></th>
<th><span data-ttu-id="860b6-112">Альтернативные имена субъектов</span><span class="sxs-lookup"><span data-stu-id="860b6-112">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="860b6-113">Comments</span><span class="sxs-lookup"><span data-stu-id="860b6-113">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="860b6-114">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="860b6-114">Default</span></span></p></td>
<td><p><span data-ttu-id="860b6-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="860b6-115">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="860b6-116">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="860b6-116">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="860b6-117">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="860b6-117">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="860b6-118">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="860b6-118">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="860b6-119">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="860b6-119">meet.contoso.com</span></span></p>
<p><span data-ttu-id="860b6-120">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="860b6-120">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="860b6-121">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="860b6-121">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="860b6-122">(Дополнительно) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="860b6-122">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="860b6-123">Сертификаты директора могут запрашиваться как из внутреннего управляемого центра сертификации, так и из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="860b6-123">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="860b6-124">Режиссер отвечает на запросы от обратного прокси-сервера в сети периметра или от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="860b6-124">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="860b6-125">Внутренние клиенты не будут использовать директор.</span><span class="sxs-lookup"><span data-stu-id="860b6-125">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="860b6-126">Или запись с подстановочными знаками для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="860b6-126">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="860b6-127">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="860b6-127">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="860b6-128">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="860b6-128">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="860b6-129">Без записи</span><span class="sxs-lookup"><span data-stu-id="860b6-129">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="860b6-130">Обратите внимание, что минимальная длина ключа равна 1024, однако может возникнуть предупреждение, что рекомендуемая минимальная длина равна 2048 битам.</span><span class="sxs-lookup"><span data-stu-id="860b6-130">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="860b6-p103">Сертификат OAuthTokenIssuer — это специализированный сертификат для проверки подлинности серверов в крупномасштабной среде, который можно запросить из внутреннего или из общего центра сертификации. Этот сертификат является обязательным.</span><span class="sxs-lookup"><span data-stu-id="860b6-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

