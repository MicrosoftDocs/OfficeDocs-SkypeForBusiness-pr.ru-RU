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
ms.openlocfilehash: 87657340205722a721485f213029220641885075
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533396"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="83871-102">Требования к сертификатам для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83871-102">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83871-103">_**Последнее изменение темы:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="83871-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="83871-104">При развертывании функции мобильной связи и поддержки автоматического обнаружения для мобильных клиентов потребуется добавить в сертификаты записи альтернативных имен субъектов для поддержки безопасных подключений мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="83871-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="83871-105">Сертификаты, в которые необходимо добавить записи альтернативных имен субъектов для автоматического обнаружения:</span><span class="sxs-lookup"><span data-stu-id="83871-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="83871-106">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="83871-106">Director pool</span></span>

  - <span data-ttu-id="83871-107">Интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="83871-107">Front End pool</span></span>

  - <span data-ttu-id="83871-108">Сертификат обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="83871-108">Reverse proxy</span></span>

<span data-ttu-id="83871-109">В этом разделе описываются записи альтернативных имен субъектов, которые требуется добавить в сертификаты для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="83871-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83871-110">Обычно повторная выдача сертификатов с использованием внутреннего центра сертификации — это простой процесс, но добавление нескольких альтернативных имен субъектов в общедоступные сертификаты, используемые обратным прокси-сервером может быть ресурсоемкой задачей.</span><span class="sxs-lookup"><span data-stu-id="83871-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="83871-111">Если у вас много доменов SIP, что делает добавление альтернативных имен субъектов очень дорогим, можно настроить обратный прокси для использования протокола HTTP для первоначального запроса службы автообнаружения вместо использования HTTPS (конфигурация по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="83871-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="83871-112">Дополнительные сведения см <A href="lync-server-2013-technical-requirements-for-mobility.md">в статье технические требования к мобильности в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="83871-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="83871-113">Требования к сертификатам пула Директор</span><span class="sxs-lookup"><span data-stu-id="83871-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83871-114">Описание</span><span class="sxs-lookup"><span data-stu-id="83871-114">Description</span></span></th>
<th><span data-ttu-id="83871-115">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="83871-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83871-116">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="83871-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="83871-117">SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83871-118">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="83871-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="83871-119">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="83871-120">Кроме того, вы можете использовать сеть SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="83871-121">Требования к сертификатам интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="83871-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83871-122">Описание</span><span class="sxs-lookup"><span data-stu-id="83871-122">Description</span></span></th>
<th><span data-ttu-id="83871-123">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="83871-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83871-124">Внутренний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="83871-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="83871-125">SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83871-126">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="83871-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="83871-127">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="83871-128">Кроме того, вы можете использовать сеть SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="83871-129">Требования к сертификатам обратного прокси-сервера (общедоступного центра сертификации)</span><span class="sxs-lookup"><span data-stu-id="83871-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83871-130">Описание</span><span class="sxs-lookup"><span data-stu-id="83871-130">Description</span></span></th>
<th><span data-ttu-id="83871-131">Запись альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="83871-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83871-132">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="83871-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="83871-133">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="83871-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="83871-134">Это альтернативное имя субъекта назначается сертификату, назначенному прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="83871-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="83871-135">Прослушиватель обратного прокси-сервера будет содержать альтернативные имена субъектов для URL-адресов внешних веб-служб (например, SAN = lyncwebextpool01. contoso. com и dirwebexternal.contoso.com, если вы развернули необязательный директор).</span><span class="sxs-lookup"><span data-stu-id="83871-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

