---
title: 'Lync Server 2013: требования к сертификатам для мобильной работы'
description: 'Lync Server 2013: требования к сертификатам для мобильных устройств.'
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
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575205"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7cb8e-103">Требования к сертификатам для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cb8e-103">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cb8e-104">_**Последнее изменение темы:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="7cb8e-104">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="7cb8e-105">При развертывании функции мобильной связи и поддержки автоматического обнаружения для мобильных клиентов потребуется добавить в сертификаты записи альтернативных имен субъектов для поддержки безопасных подключений мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-105">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="7cb8e-106">Сертификаты, в которые необходимо добавить записи альтернативных имен субъектов для автоматического обнаружения:</span><span class="sxs-lookup"><span data-stu-id="7cb8e-106">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="7cb8e-107">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="7cb8e-107">Director pool</span></span>

  - <span data-ttu-id="7cb8e-108">Интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="7cb8e-108">Front End pool</span></span>

  - <span data-ttu-id="7cb8e-109">Сертификат обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="7cb8e-109">Reverse proxy</span></span>

<span data-ttu-id="7cb8e-110">В этом разделе описываются записи альтернативных имен субъектов, которые требуется добавить в сертификаты для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-110">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cb8e-111">Обычно повторная выдача сертификатов с использованием внутреннего центра сертификации — это простой процесс, но добавление нескольких альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси-сервером может быть ресурсоемкой задачей.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-111">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="7cb8e-112">Если у вас много доменов SIP, что делает добавление альтернативных имен субъектов очень дорогим, можно настроить обратный прокси для использования протокола HTTP для первоначального запроса службы автообнаружения вместо использования HTTPS (конфигурация по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7cb8e-112">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="7cb8e-113">Дополнительные сведения см <A href="lync-server-2013-technical-requirements-for-mobility.md">в статье технические требования к мобильности в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-113">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="7cb8e-114">Требования к сертификатам пула Директор</span><span class="sxs-lookup"><span data-stu-id="7cb8e-114">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cb8e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7cb8e-115">Description</span></span></th>
<th><span data-ttu-id="7cb8e-116">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="7cb8e-116">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cb8e-117">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="7cb8e-117">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7cb8e-118">SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-118">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb8e-119">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="7cb8e-119">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7cb8e-120">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-120">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7cb8e-121">Кроме того, вы можете использовать сеть SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-121">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="7cb8e-122">Требования к сертификатам интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="7cb8e-122">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cb8e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7cb8e-123">Description</span></span></th>
<th><span data-ttu-id="7cb8e-124">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="7cb8e-124">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cb8e-125">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="7cb8e-125">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7cb8e-126">SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-126">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb8e-127">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="7cb8e-127">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7cb8e-128">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-128">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7cb8e-129">Кроме того, вы можете использовать сеть SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-129">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="7cb8e-130">Требования к сертификатам обратного прокси-сервера (общедоступного центра сертификации)</span><span class="sxs-lookup"><span data-stu-id="7cb8e-130">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cb8e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="7cb8e-131">Description</span></span></th>
<th><span data-ttu-id="7cb8e-132">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="7cb8e-132">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cb8e-133">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="7cb8e-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7cb8e-134">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7cb8e-134">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7cb8e-135">Это альтернативное имя субъекта назначается сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-135">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7cb8e-136">Прослушиватель обратного прокси-сервера будет содержать альтернативные имена субъектов для URL-адресов внешних веб-служб (например, SAN = lyncwebextpool01. contoso. com и dirwebexternal.contoso.com, если вы развернули необязательный директор).</span><span class="sxs-lookup"><span data-stu-id="7cb8e-136">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

