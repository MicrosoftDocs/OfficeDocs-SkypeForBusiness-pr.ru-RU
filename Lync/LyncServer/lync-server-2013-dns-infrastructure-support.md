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
ms.openlocfilehash: e5ede9d6af8c9f912a207c602c225c19c3dd1f38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="76fae-102">Поддержка инфраструктуры DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76fae-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76fae-103">_**Последнее изменение темы:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="76fae-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="76fae-104">Для Lync Server 2013 требуется система доменных имен (DNS) и используется следующими способами:</span><span class="sxs-lookup"><span data-stu-id="76fae-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="76fae-105">Для обнаружения внутренних серверов или пулов для межсерверной связи.</span><span class="sxs-lookup"><span data-stu-id="76fae-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="76fae-106">Для предоставления клиентам возможности обнаружения пула переднего плана или сервера Standard Edition, используемого для различных транзакций SIP.</span><span class="sxs-lookup"><span data-stu-id="76fae-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="76fae-107">Для связи простых URL-адресов для конференций с серверами, на которых размещаются эти конференции.</span><span class="sxs-lookup"><span data-stu-id="76fae-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="76fae-108">Для предоставления внешним серверам и клиентам возможности подключения к пограничным серверам или обратному прокси-серверу HTTP для обмена мгновенными сообщениями ил конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="76fae-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="76fae-109">Для предоставления устройствам для объединенных коммуникаций возможности обнаружения пула переднего плана или сервера Standard Edition, на котором функционирует веб-служба обновления устройств, получения обновлений и отправки журналов без необходимости входа.</span><span class="sxs-lookup"><span data-stu-id="76fae-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="76fae-110">Для предоставления мобильным клиентам возможности автоматического обнаружения ресурсов веб-служб без необходимости ручного ввода URL-адресов в настройках устройств.</span><span class="sxs-lookup"><span data-stu-id="76fae-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="76fae-111">Для балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="76fae-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76fae-112">Lync Server 2013 не поддерживает международные доменные имена (IDN).</span><span class="sxs-lookup"><span data-stu-id="76fae-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="76fae-113">Указанное имя должно полностью соответствовать имени компьютера, настроенному на сервере.</span><span class="sxs-lookup"><span data-stu-id="76fae-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="76fae-114">По умолчанию в качестве имени компьютера, который не присоединен к домену, используется короткое имя, а не полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="76fae-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="76fae-115">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="76fae-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="76fae-116">Поэтому необходимо настроить суффикс DNS имени компьютера для развертывания в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="76fae-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="76fae-117"><STRONG>Используйте только стандартные символы </STRONG> (включая A-Z, a-z, 0-9 и дефисы) при назначении полных доменных имен серверов Lync, пограничных серверов и пулов.</span><span class="sxs-lookup"><span data-stu-id="76fae-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="76fae-118">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="76fae-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="76fae-119">Нестандартные символы, включенные в полное доменное имя, часто не поддерживаются внешними системами DNS и открытыми центрами сертификации (например, когда полное доменное имя необходимо назначить SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="76fae-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

