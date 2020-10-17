---
title: 'Lync Server 2013: планирование автообнаружения'
description: 'Lync Server 2013: Планирование службы автообнаружения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544635"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="aa3c0-103">Планирование автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3c0-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa3c0-104">_**Последнее изменение темы:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="aa3c0-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="aa3c0-105">Служба автообнаружения была добавлена для Lync Server в накопительном пакете обновления для Lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="aa3c0-106">Основной целью этой первоначальной реализации автообнаружения было предоставление средству Lync Mobile возможность обнаружения службы Mobility Service (MCX).</span><span class="sxs-lookup"><span data-stu-id="aa3c0-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="aa3c0-107">Служба автообнаружения в Lync Server 2013 теперь является службой, используемой всеми клиентами для обнаружения серверных и пользовательских служб.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="aa3c0-108">Служба автообнаружения Microsoft Lync Server 2013 работает на директориях и серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="aa3c0-109">Более подробную техническую информацию о службе автообнаружения и о том, что происходит с клиентами, можно узнать <A href="lync-server-2013-understanding-autodiscover.md">в статье Общие сведения о службе автообнаружения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="aa3c0-110">Мобильность по-прежнему является отдельным сценарием, а службам Mobility по-прежнему требуется специальное планирование.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="aa3c0-111">Дополнительные сведения см в статье <A href="lync-server-2013-planning-for-mobility.md">планирование мобильных устройств в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="aa3c0-112">Когда служба автообнаружения появилась в Lync Server 2010, существуют компромиссы, которые необходимо выполнить, чтобы реализовать службу, требующую потенциальных изменений сертификатов для существующих развертываний серверов.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="aa3c0-113">Службу автообнаружения можно использовать через порт TCP 443 для HTTPS или через порт TCP 80 для HTTP.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="aa3c0-114">Если было принято решение использовать HTTPS, сертификаты на обратных прокси-серверах, директориях и серверах переднего плана должны быть повторно выдаваться для размещения необходимых `lyncdiscover.<domain>` и `lyncdiscoverinternal.<domain>` DNS-записей.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="aa3c0-115">Если было принято решение об использовании протокола HTTP, можно избежать повторной выпуска сертификатов с помощью записей CNAME DNS (или псевдонимов) для использования существующих имен в сертификатах.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="aa3c0-116">При использовании HTTP имелось в виду, что начальные сообщения не были зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="aa3c0-117">Так как Lync Server 2013 использует функцию автообнаружения для всех клиентов, основной сценарий состоит в том, чтобы использовать только HTTPS и создавать сертификаты с помощью lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="aa3c0-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="aa3c0-118">в рамках настройки обратных прокси-серверов, директоров и серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="aa3c0-119">Если вы реализуете автообнаружение в обновленном развертывании с Lync Server 2010, вам может потребоваться использовать HTTP, чтобы избежать повторной выдачи сертификатов.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="aa3c0-120">Руководство по обоим сценариям представлено в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aa3c0-121">Список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб, должен содержать <EM>lyncdiscover. &lt; запись &gt; sipdomain</EM> для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="aa3c0-122">Для получения сведений о записях альтернативного имени субъекта, необходимых для директоров, серверов переднего плана и обратных прокси-серверов, ознакомьтесь со статьей <A href="lync-server-2013-certificate-summary-autodiscover.md">Сводка по сертификатам — автообнаружение в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa3c0-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa3c0-123">Содержание</span><span class="sxs-lookup"><span data-stu-id="aa3c0-123">In This Section</span></span>

  - [<span data-ttu-id="aa3c0-124">Сводка по сертификатам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3c0-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="aa3c0-125">Сводка по портам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3c0-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="aa3c0-126">Сводка по DNS — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3c0-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="aa3c0-127">Гибридное и комбинированное доменное обнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3c0-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

