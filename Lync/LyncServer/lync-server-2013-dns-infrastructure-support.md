---
title: 'Lync Server 2013: поддержка инфраструктуры DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="b3231-102">Поддержка инфраструктуры DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3231-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3231-103">_**Тема последнего изменения:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="b3231-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="b3231-104">Для Lync Server 2013 требуется система доменных имен (DNS) и его использование описанными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="b3231-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="b3231-105">Для выяснения внутренних серверов или пулов для обмена данными между серверами.</span><span class="sxs-lookup"><span data-stu-id="b3231-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="b3231-106">Предоставление клиентам возможности поиска пула переднего плана или сервера Standard Edition, используемого для различных транзакций SIP.</span><span class="sxs-lookup"><span data-stu-id="b3231-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="b3231-107">Чтобы связать простые URL-адреса для конференций с серверами, на которых размещаются эти конференции.</span><span class="sxs-lookup"><span data-stu-id="b3231-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="b3231-108">Чтобы разрешить внешним серверам и клиентам подключаться к пограничным серверам или обратно прокси-серверу HTTP для обмена мгновенными сообщениями или конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b3231-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="b3231-109">Чтобы включить устройства унифицированной связи (UC), не вошедших в систему, чтобы найти пул интерфейсов переднего плана или сервер Standard Edition с веб-службой обновления устройств, получить обновления и отправить журналы.</span><span class="sxs-lookup"><span data-stu-id="b3231-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="b3231-110">Чтобы разрешить мобильным клиентам автоматически определять ресурсы веб-служб без необходимости вручную вводить URL-адреса в окне "Параметры устройства".</span><span class="sxs-lookup"><span data-stu-id="b3231-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="b3231-111">Для балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="b3231-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3231-112">Lync Server 2013 не поддерживает международные доменные имена (Иднс).</span><span class="sxs-lookup"><span data-stu-id="b3231-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3231-113">Указанное имя должно быть идентично имени компьютера, настроенному на сервере.</span><span class="sxs-lookup"><span data-stu-id="b3231-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="b3231-114">По умолчанию имя компьютера, которое не присоединено к домену, является коротким именем, а не полным доменным именем (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b3231-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="b3231-115">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="b3231-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b3231-116">Поэтому для компьютера, развертываемого в качестве пограничного сервера, не присоединенного к домену, потребуется указать DNS-суффикс.</span><span class="sxs-lookup"><span data-stu-id="b3231-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="b3231-117"><STRONG>Используйте только стандартные символы</STRONG> (A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам.</span><span class="sxs-lookup"><span data-stu-id="b3231-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b3231-118">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="b3231-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b3231-119">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-серверами и общими центрами сертификации (например, когда полное доменное имя необходимо назначить имени субъекта в сертификате).</span><span class="sxs-lookup"><span data-stu-id="b3231-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

