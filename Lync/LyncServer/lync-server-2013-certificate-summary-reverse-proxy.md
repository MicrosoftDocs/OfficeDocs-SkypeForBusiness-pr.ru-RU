---
title: 'Lync Server 2013: сводка по сертификатам — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="19aea-102">Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19aea-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19aea-103">_**Тема последнего изменения:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="19aea-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="19aea-104">Требования к сертификатам для обратного прокси-сервера значительно проще, чем для пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="19aea-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="19aea-105">В предоставленных блок-схемах представлены необходимые требования.</span><span class="sxs-lookup"><span data-stu-id="19aea-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="19aea-106">Сопутствующая таблица представляет собой типичное имя субъекта сертификата и альтернативные имена субъектов в отношении сценариев, которые мы проверили в обсуждениях пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="19aea-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="19aea-107">Более подробную информацию о сценариях пограничного сервера можно найти [в разделе сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="19aea-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="19aea-108">**Блок-схема "сертификаты" для обратного прокси**</span><span class="sxs-lookup"><span data-stu-id="19aea-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="19aea-109">![Блок-схема сертификации для пограничного сервера](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Блок-схема сертификации для пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="19aea-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="19aea-110">Обратный прокси: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="19aea-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19aea-111">Компонент</span><span class="sxs-lookup"><span data-stu-id="19aea-111">Component</span></span></th>
<th><span data-ttu-id="19aea-112">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="19aea-112">Subject name</span></span></th>
<th><span data-ttu-id="19aea-113">Замещающий имя субъекта (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="19aea-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="19aea-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="19aea-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19aea-115">Обратный прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="19aea-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="19aea-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="19aea-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="19aea-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="19aea-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="19aea-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="19aea-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="19aea-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="19aea-123">(Необязательно):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="19aea-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="19aea-124">Сертификат должен быть выдан общедоступным центром сертификации и в серверном EKU.</span><span class="sxs-lookup"><span data-stu-id="19aea-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="19aea-125">Службы включают в себя службу адресной книги, развертывание групп рассылки Office Web Apps для конференций и правила публикации для IP-устройств Lync.</span><span class="sxs-lookup"><span data-stu-id="19aea-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="19aea-126">Ниже указаны дополнительные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="19aea-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="19aea-127">Полное доменное имя внешней веб-службы для пула серверов переднего плана или внешнего интерфейса</span><span class="sxs-lookup"><span data-stu-id="19aea-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="19aea-128">Полное доменное имя внешней веб-службы для режиссера или режиссера</span><span class="sxs-lookup"><span data-stu-id="19aea-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="19aea-129">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="19aea-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="19aea-130">Правило публикации для собрания по сети</span><span class="sxs-lookup"><span data-stu-id="19aea-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="19aea-131">Office Web Apps для конференций</span><span class="sxs-lookup"><span data-stu-id="19aea-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="19aea-132">Lyncdiscover (автообнаружение)</span><span class="sxs-lookup"><span data-stu-id="19aea-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="19aea-133">Необязательный подстановочный знак заменяет и соответствие требованиям к сети SAN</span><span class="sxs-lookup"><span data-stu-id="19aea-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

