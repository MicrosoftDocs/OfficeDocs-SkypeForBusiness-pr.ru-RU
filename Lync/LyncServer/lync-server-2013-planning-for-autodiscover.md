---
title: 'Lync Server 2013: планирование автообнаружения'
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
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="c841a-102">Планирование автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c841a-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c841a-103">_**Тема последнего изменения:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="c841a-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="c841a-104">Средство автообнаружения было представлено для Lync Server в накопительном обновлении для Lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="c841a-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="c841a-105">Основным предназначением для этой первоначальной реализации автообнаружения было предоставление средств Lync Mobile поиска службы Mobility Service (МККС).</span><span class="sxs-lookup"><span data-stu-id="c841a-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="c841a-106">Служба автообнаружения в Lync Server 2013 теперь является службой, используемой всеми клиентами для поиска серверных и пользовательских служб.</span><span class="sxs-lookup"><span data-stu-id="c841a-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="c841a-107">Служба автообнаружения Microsoft Lync Server 2013 работает на директориях и серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c841a-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c841a-108">Дополнительные сведения о автообнаружения и возможностях, которые передается клиентам, приведены в разделе <A href="lync-server-2013-understanding-autodiscover.md">Общие сведения о автообнаружения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c841a-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="c841a-109">Мобильность по-прежнему является особым сценарием, а для служб Mobility по-прежнему требуется специальное планирование.</span><span class="sxs-lookup"><span data-stu-id="c841a-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="c841a-110">Дополнительные сведения можно найти <A href="lync-server-2013-planning-for-mobility.md">в разделе Планирование мобильных устройств в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c841a-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c841a-111">При вводе автообнаружения в Lync Server 2010 для реализации службы, требующей потенциальных изменений сертификатов на существующем сервере, находились нарушения, которые необходимо было сделать.</span><span class="sxs-lookup"><span data-stu-id="c841a-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="c841a-112">Функцию автообнаружения можно использовать для порта TCP 443 для HTTPS или порта TCP 80 для HTTP.</span><span class="sxs-lookup"><span data-stu-id="c841a-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="c841a-113">Если вы принимаете решение использовать HTTPS, сертификаты на обратных прокси-серверах, режиссерах и серверах переднего плана должны быть повторно выпущены для размещения необходимых `lyncdiscover.<domain>` и `lyncdiscoverinternal.<domain>` DNS-записей.</span><span class="sxs-lookup"><span data-stu-id="c841a-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="c841a-114">Если вы хотите использовать HTTP, повторные выдаче сертификатов могут быть невозможны с помощью записей CNAME DNS (или псевдонима) для использования существующих имен в сертификатах.</span><span class="sxs-lookup"><span data-stu-id="c841a-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="c841a-115">Использование HTTP означает, что начальные соединения не были зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="c841a-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="c841a-116">Поскольку Lync Server 2013 использует функцию автообнаружения для всех клиентов, основным сценарием является использование HTTPS исключительно и создание сертификатов с помощью lyncdiscover. \<домен\> в рамках настройки обратных прокси, режиссеров и серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c841a-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="c841a-117">Если вы реализуете автообнаружение в обновленном развертывании с Lync Server 2010, вам может потребоваться использовать HTTP, чтобы избежать повторной сертификации сертификатов.</span><span class="sxs-lookup"><span data-stu-id="c841a-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="c841a-118">Руководство по обоим сценариям приведено в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c841a-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c841a-119">Список альтернативных имен субъектов в сертификатах, используемых внешним правилом публикации веб-служб, должен содержать <EM>lyncdiscover.&lt; сипдомаин&gt; </EM> запись для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="c841a-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="c841a-120">Дополнительные сведения об элементах альтернативных имен тем, которые требуются для режиссеров, серверов переднего плана и обратного доступа, приведены <A href="lync-server-2013-certificate-summary-autodiscover.md">в разделе сведения о сертификате: автообнаружение в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c841a-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c841a-121">Содержание</span><span class="sxs-lookup"><span data-stu-id="c841a-121">In This Section</span></span>

  - [<span data-ttu-id="c841a-122">Сведения о сертификате: обнаружение автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c841a-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="c841a-123">Сводка порта: автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c841a-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="c841a-124">Сводка DNS: обнаружение автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c841a-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="c841a-125">Гибридная и Разделяемая доменные возможности автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c841a-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

