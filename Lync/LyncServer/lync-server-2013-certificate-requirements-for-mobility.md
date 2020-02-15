---
title: 'Lync Server 2013: требования к сертификатам для мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf7dd0f3ce9868fbeac5c757fce5371ad77fba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="5ea00-102">Требования к сертификатам для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea00-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea00-103">_**Последнее изменение темы:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="5ea00-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="5ea00-104">При развертывании функции мобильной связи и поддержки автоматического обнаружения для мобильных клиентов потребуется добавить в сертификаты записи альтернативных имен субъектов для поддержки безопасных подключений мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="5ea00-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="5ea00-105">Сертификаты, в которые необходимо добавить записи альтернативных имен субъектов для автоматического обнаружения:</span><span class="sxs-lookup"><span data-stu-id="5ea00-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="5ea00-106">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="5ea00-106">Director pool</span></span>

  - <span data-ttu-id="5ea00-107">Интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="5ea00-107">Front End pool</span></span>

  - <span data-ttu-id="5ea00-108">Сертификат обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="5ea00-108">Reverse proxy</span></span>

<span data-ttu-id="5ea00-109">В этом разделе описываются записи альтернативных имен субъектов, которые требуется добавить в сертификаты для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5ea00-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ea00-110">Обычно повторная выдача сертификатов с использованием внутреннего центра сертификации — это простой процесс, но добавление нескольких альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси-сервером может быть ресурсоемкой задачей.</span><span class="sxs-lookup"><span data-stu-id="5ea00-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="5ea00-111">Если у вас много доменов SIP, что делает добавление альтернативных имен субъектов очень дорогим, можно настроить обратный прокси для использования протокола HTTP для первоначального запроса службы автообнаружения вместо использования HTTPS (конфигурация по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5ea00-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="5ea00-112">Дополнительные сведения см <A href="lync-server-2013-technical-requirements-for-mobility.md">в статье технические требования к мобильности в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5ea00-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="5ea00-113">Требования к сертификатам пула Директор</span><span class="sxs-lookup"><span data-stu-id="5ea00-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea00-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5ea00-114">Description</span></span></th>
<th><span data-ttu-id="5ea00-115">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="5ea00-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea00-116">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5ea00-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ea00-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea00-118">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5ea00-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ea00-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5ea00-120">Кроме того, вы можете использовать сеть SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="5ea00-121">Требования к сертификатам интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="5ea00-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea00-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5ea00-122">Description</span></span></th>
<th><span data-ttu-id="5ea00-123">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="5ea00-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea00-124">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5ea00-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ea00-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea00-126">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5ea00-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ea00-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5ea00-128">Кроме того, вы можете использовать сеть SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="5ea00-129">Требования к сертификатам обратного прокси-сервера (общедоступного центра сертификации)</span><span class="sxs-lookup"><span data-stu-id="5ea00-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea00-130">Описание</span><span class="sxs-lookup"><span data-stu-id="5ea00-130">Description</span></span></th>
<th><span data-ttu-id="5ea00-131">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="5ea00-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea00-132">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5ea00-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5ea00-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5ea00-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5ea00-134">Это альтернативное имя субъекта назначается сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="5ea00-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5ea00-135">Прослушиватель обратного прокси-сервера будет содержать альтернативные имена субъектов для URL-адресов внешних веб-служб (например, SAN = lyncwebextpool01. contoso. com и dirwebexternal.contoso.com, если вы развернули необязательный директор).</span><span class="sxs-lookup"><span data-stu-id="5ea00-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

