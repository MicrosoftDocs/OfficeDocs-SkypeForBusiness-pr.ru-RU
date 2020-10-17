---
title: 'Lync Server 2013: сводка по сертификатам — один директор'
description: 'Lync Server 2013: сводка по сертификатам — один директор.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572165"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="054e1-103">Сводка по сертификатам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="054e1-103">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="054e1-104">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="054e1-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="054e1-105">Требования к сертификатам для одного директора состоят из сертификата по умолчанию, который содержит имя субъекта и альтернативные имена субъекта для служб, которые может получить руководитель.</span><span class="sxs-lookup"><span data-stu-id="054e1-105">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="054e1-106">Кроме того, существует сертификат маркера OAuth для проверки подлинности «сервер-сервер».</span><span class="sxs-lookup"><span data-stu-id="054e1-106">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="054e1-107">Сертификаты для Директора</span><span class="sxs-lookup"><span data-stu-id="054e1-107">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="054e1-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="054e1-108">Component</span></span></th>
<th><span data-ttu-id="054e1-109">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="054e1-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="054e1-110">Альтернативные имена субъектов</span><span class="sxs-lookup"><span data-stu-id="054e1-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="054e1-111">Comments</span><span class="sxs-lookup"><span data-stu-id="054e1-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="054e1-112">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="054e1-112">Default</span></span></p></td>
<td><p><span data-ttu-id="054e1-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="054e1-113">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="054e1-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="054e1-114">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="054e1-115">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="054e1-115">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="054e1-116">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="054e1-116">meet.contoso.com</span></span></p>
<p><span data-ttu-id="054e1-117">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="054e1-117">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="054e1-118">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="054e1-118">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="054e1-119">(Дополнительно) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="054e1-119">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="054e1-120">Сертификаты директора могут запрашиваться как из внутреннего управляемого центра сертификации, так и из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="054e1-120">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="054e1-121">Режиссер отвечает на запросы от обратного прокси-сервера в сети периметра или от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="054e1-121">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="054e1-122">Внутренние клиенты не будут использовать директор.</span><span class="sxs-lookup"><span data-stu-id="054e1-122">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="054e1-123">Или запись с подстановочными знаками для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="054e1-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="054e1-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="054e1-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="054e1-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="054e1-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="054e1-126">Без записи</span><span class="sxs-lookup"><span data-stu-id="054e1-126">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="054e1-127">Обратите внимание, что минимальная длина ключа равна 1024, однако может возникнуть предупреждение, что рекомендуемая минимальная длина равна 2048 битам.</span><span class="sxs-lookup"><span data-stu-id="054e1-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="054e1-p103">Сертификат OAuthTokenIssuer — это специализированный сертификат для проверки подлинности серверов в крупномасштабной среде, который можно запросить из внутреннего или из общего центра сертификации. Этот сертификат является обязательным.</span><span class="sxs-lookup"><span data-stu-id="054e1-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

