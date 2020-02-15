---
title: 'Lync Server 2013: сводка по сертификатам — один директор'
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
ms.openlocfilehash: abb3b1e9963d88a7876232219a8d4f2290c2c9cc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="2b361-102">Сводка по сертификатам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b361-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b361-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2b361-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2b361-104">Требования к сертификатам для одного директора состоят из сертификата по умолчанию, который содержит имя субъекта и альтернативные имена субъекта для служб, которые может получить руководитель.</span><span class="sxs-lookup"><span data-stu-id="2b361-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="2b361-105">Кроме того, существует сертификат маркера OAuth для проверки подлинности «сервер-сервер».</span><span class="sxs-lookup"><span data-stu-id="2b361-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="2b361-106">Сертификаты для Директора</span><span class="sxs-lookup"><span data-stu-id="2b361-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b361-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="2b361-107">Component</span></span></th>
<th><span data-ttu-id="2b361-108">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="2b361-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="2b361-109">Альтернативные имена субъектов</span><span class="sxs-lookup"><span data-stu-id="2b361-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="2b361-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2b361-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b361-111">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="2b361-111">Default</span></span></p></td>
<td><p><span data-ttu-id="2b361-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2b361-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2b361-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2b361-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="2b361-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b361-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="2b361-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b361-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="2b361-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b361-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="2b361-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b361-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="2b361-118">(Дополнительно) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b361-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b361-119">Сертификаты директора могут запрашиваться как из внутреннего управляемого центра сертификации, так и из общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="2b361-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="2b361-120">Режиссер отвечает на запросы от обратного прокси-сервера в сети периметра или от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2b361-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="2b361-121">Внутренние клиенты не будут использовать директор.</span><span class="sxs-lookup"><span data-stu-id="2b361-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="2b361-122">Или запись с подстановочными знаками для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="2b361-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b361-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="2b361-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="2b361-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2b361-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2b361-125">Без записи</span><span class="sxs-lookup"><span data-stu-id="2b361-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="2b361-126">Обратите внимание, что минимальная длина ключа равна 1024, однако может возникнуть предупреждение, что рекомендуемая минимальная длина равна 2048 битам.</span><span class="sxs-lookup"><span data-stu-id="2b361-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="2b361-p103">Сертификат OAuthTokenIssuer — это специализированный сертификат для проверки подлинности серверов в крупномасштабной среде, который можно запросить из внутреннего или из общего центра сертификации. Этот сертификат является обязательным.</span><span class="sxs-lookup"><span data-stu-id="2b361-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

