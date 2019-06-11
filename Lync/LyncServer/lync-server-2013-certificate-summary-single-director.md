---
title: 'Lync Server 2013: сводка по сертификатам — единственный директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e44be0ca76a1926a1515657a9d7d5646a49390c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8dd63-102">Сводка по сертификатам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dd63-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dd63-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8dd63-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8dd63-104">Требования к сертификатам для единого директора состоят из сертификата по умолчанию, который содержит имя субъекта и другие имена тем для служб, которые может получать руководитель.</span><span class="sxs-lookup"><span data-stu-id="8dd63-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="8dd63-105">Кроме того, существует сертификат маркера OAuth для проверки подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="8dd63-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="8dd63-106">Сертификаты для режиссера</span><span class="sxs-lookup"><span data-stu-id="8dd63-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dd63-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="8dd63-107">Component</span></span></th>
<th><span data-ttu-id="8dd63-108">Имя субъекта (SN)</span><span class="sxs-lookup"><span data-stu-id="8dd63-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="8dd63-109">Дополнительные имена субъектов (SAN)</span><span class="sxs-lookup"><span data-stu-id="8dd63-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="8dd63-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8dd63-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dd63-111">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8dd63-111">Default</span></span></p></td>
<td><p><span data-ttu-id="8dd63-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8dd63-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8dd63-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8dd63-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="8dd63-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8dd63-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="8dd63-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8dd63-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="8dd63-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8dd63-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="8dd63-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8dd63-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="8dd63-118">(Необязательно) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="8dd63-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8dd63-119">Сертификаты в службе каталогов могут запрашиваться либо с помощью внутреннего управляемого центра сертификации (ЦС), либо из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="8dd63-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="8dd63-120">Режиссер отвечает на запросы на обратных прокси-серверах периметра или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8dd63-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="8dd63-121">Внутренние клиенты не будут использовать режиссер.</span><span class="sxs-lookup"><span data-stu-id="8dd63-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="8dd63-122">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="8dd63-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd63-123">Оаустокениссуер</span><span class="sxs-lookup"><span data-stu-id="8dd63-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="8dd63-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8dd63-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8dd63-125">Нет записи</span><span class="sxs-lookup"><span data-stu-id="8dd63-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="8dd63-126">Обратите внимание, что минимальная длина ключа составляет 1024, но вы можете получить предупреждение о том, что минимальная рекомендуемая длина ключа составляет 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="8dd63-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="8dd63-127">Сертификат Оаустокениссуер является однозначным сертификатом для серверов с проверкой подлинности в крупномасштабной среде и может запрашиваться из внутреннего или общедоступного ЦС.</span><span class="sxs-lookup"><span data-stu-id="8dd63-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="8dd63-128">Требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="8dd63-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

