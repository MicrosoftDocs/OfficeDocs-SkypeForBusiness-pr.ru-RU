---
title: 'Lync Server 2013: сводка по сертификатам, балансировка нагрузки на DNS и HLB'
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
ms.openlocfilehash: e915a8b9d7e339453c687d269ed10bc744ab761b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="32532-102">Сводка по сертификатам: Балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32532-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32532-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="32532-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="32532-104">Требования к сертификатам для директора с балансировкой нагрузки на DNS и аппаратным подсистемным подсистемой балансировки нагрузки будут использовать сертификат по умолчанию с именем субъекта и альтернативными именами субъектов для служб, которые может получить директор.</span><span class="sxs-lookup"><span data-stu-id="32532-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="32532-105">Для каждого директора в пуле запрашивается сертификат.</span><span class="sxs-lookup"><span data-stu-id="32532-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="32532-106">Важно помнить о том, что аппаратный балансировщик нагрузки — балансировка нагрузки только трафик из обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="32532-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="32532-107">Кроме того, существует сертификат маркера OAuth для проверки подлинности сервера на сервере, установленный на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="32532-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="32532-108">Сертификаты для Директора</span><span class="sxs-lookup"><span data-stu-id="32532-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32532-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="32532-109">Component</span></span></th>
<th><span data-ttu-id="32532-110">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="32532-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="32532-111">Альтернативные имена субъектов</span><span class="sxs-lookup"><span data-stu-id="32532-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="32532-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="32532-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32532-113">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="32532-113">Default</span></span></p></td>
<td><p><span data-ttu-id="32532-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="32532-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="32532-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="32532-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="32532-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="32532-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="32532-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32532-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="32532-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32532-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="32532-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32532-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="32532-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32532-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="32532-121">(Дополнительно) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32532-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32532-122">Сертификаты директора могут запрашиваться как из внутреннего управляемого центра сертификации, так и из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="32532-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="32532-123">Режиссер отвечает на запросы от обратного прокси-сервера в сети периметра или от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="32532-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="32532-124">Внутренние клиенты не будут использовать директор.</span><span class="sxs-lookup"><span data-stu-id="32532-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="32532-125">Или запись с подстановочными знаками для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="32532-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32532-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="32532-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="32532-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="32532-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="32532-128">Без записи</span><span class="sxs-lookup"><span data-stu-id="32532-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="32532-129">Обратите внимание, что минимальная длина ключа равна 1024, однако может возникнуть предупреждение, что рекомендуемая минимальная длина равна 2048 битам.</span><span class="sxs-lookup"><span data-stu-id="32532-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="32532-p103">Сертификат OAuthTokenIssuer — это специализированный сертификат для проверки подлинности серверов в крупномасштабной среде, который можно запросить из внутреннего или из общего центра сертификации. Этот сертификат является обязательным.</span><span class="sxs-lookup"><span data-stu-id="32532-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

