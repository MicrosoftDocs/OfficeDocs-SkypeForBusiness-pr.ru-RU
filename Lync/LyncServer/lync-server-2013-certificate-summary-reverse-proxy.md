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
ms.openlocfilehash: 25e83fb5857988396c3d13d2b07078c654972c92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515746"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="26090-102">Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26090-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26090-103">_**Последнее изменение темы:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="26090-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="26090-104">Требования к сертификатам для обратного прокси-сервера значительно проще, чем для пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="26090-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="26090-105">В приведенной блок-схеме представлены обязательные требования.</span><span class="sxs-lookup"><span data-stu-id="26090-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="26090-106">Сопроводительная таблица представляет Типичное имя субъекта сертификата и альтернативные имена субъектов в отношении сценариев, которые мы рассматривали в дискуссиях пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="26090-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="26090-107">Более подробную информацию о сценариях пограничных серверов можно найти [в статье сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="26090-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="26090-108">**Блок-схема сертификатов для обратного прокси-сервера**</span><span class="sxs-lookup"><span data-stu-id="26090-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="26090-109">![Сертификаты для пограничного сервера (блок-схема)](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Сертификаты для пограничного сервера (блок-схема)")</span><span class="sxs-lookup"><span data-stu-id="26090-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="26090-110">Обратный прокси-сервер: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="26090-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26090-111">Компонент</span><span class="sxs-lookup"><span data-stu-id="26090-111">Component</span></span></th>
<th><span data-ttu-id="26090-112">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="26090-112">Subject name</span></span></th>
<th><span data-ttu-id="26090-113">Альтернативное имя субъекта (SAN)/заказ</span><span class="sxs-lookup"><span data-stu-id="26090-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="26090-114">Comments</span><span class="sxs-lookup"><span data-stu-id="26090-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26090-115">Обратный прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="26090-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="26090-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="26090-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="26090-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="26090-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="26090-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="26090-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="26090-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="26090-123">(Необязательно):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="26090-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="26090-124">Сертификат должен быть выпущен открытым центром сертификации и содержать ключ EKU сервера.</span><span class="sxs-lookup"><span data-stu-id="26090-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="26090-125">Службы включают в себя службу адресной книги, расширения группы рассылки Office Web Apps для конференций и правила публикации для IP-устройств Lync.</span><span class="sxs-lookup"><span data-stu-id="26090-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="26090-126">Альтернативное имя субъекта включает следующее:</span><span class="sxs-lookup"><span data-stu-id="26090-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="26090-127">Полное доменное имя внешних веб-служб для сервера переднего плана или интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="26090-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="26090-128">Полное доменное имя внешних веб-служб для директора или пула директоров</span><span class="sxs-lookup"><span data-stu-id="26090-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="26090-129">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="26090-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="26090-130">Правила публикации интернет-собраний</span><span class="sxs-lookup"><span data-stu-id="26090-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="26090-131">Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="26090-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="26090-132">Lyncdiscover (автообнаружение)</span><span class="sxs-lookup"><span data-stu-id="26090-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="26090-133">Дополнительный подстановочный знак заменяет имя SAN собраний и телефонных подключений</span><span class="sxs-lookup"><span data-stu-id="26090-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

