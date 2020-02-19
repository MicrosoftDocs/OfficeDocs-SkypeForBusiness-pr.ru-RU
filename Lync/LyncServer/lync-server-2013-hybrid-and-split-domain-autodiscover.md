---
title: 'Lync Server 2013: гибридное и разделенное доменное обнаружение'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d181887ad031a1873b289600de3f59b9d3131dd0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="86d79-102">Гибридное и комбинированное доменное обнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86d79-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86d79-103">_**Последнее изменение темы:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="86d79-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="86d79-104">Общее адресное пространство SIP, которое также называется развертыванием с *разделенным доменом* или *гибридным* развертыванием, представляет собой конфигурацию, в которой пользователи развертываются в локальном развертывании и в интерактивной среде.</span><span class="sxs-lookup"><span data-stu-id="86d79-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="86d79-105">Желаемый результат состоит в том, что пользователь независимо от того, где находится домашний сервер (локальный или в сети), подключается к развертыванию и перенаправляется на расположение домашнего сервера.</span><span class="sxs-lookup"><span data-stu-id="86d79-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="86d79-106">Для этого используется функция автообнаружения Lync Server 2013 для перенаправления интерактивного пользователя в сетевую топологию.</span><span class="sxs-lookup"><span data-stu-id="86d79-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="86d79-107">Это можно сделать, настроив URL-адрес автообнаружения с помощью командной консоли Lync Server, командлета **Get-CsHostingProvider** и командлета **Set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="86d79-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="86d79-108">Мобильность для развертывания разделенного домена</span><span class="sxs-lookup"><span data-stu-id="86d79-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="86d79-109">Вам потребуется собрать и записать следующие развернутые атрибуты:</span><span class="sxs-lookup"><span data-stu-id="86d79-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="86d79-110">В командной консоли Lync Server введите</span><span class="sxs-lookup"><span data-stu-id="86d79-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="86d79-111">В результатах найдите сетевого поставщика с атрибутом **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="86d79-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="86d79-112">Например, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="86d79-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="86d79-113">Запишите значение параметра ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="86d79-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="86d79-114">Включите Федерацию на локальной панели управления Lync Server, разрешив Федерацию с поставщиком в Интернете.</span><span class="sxs-lookup"><span data-stu-id="86d79-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="86d79-115">Включите федерацию для этого сетевого поставщика.</span><span class="sxs-lookup"><span data-stu-id="86d79-115">Enable federation for the online provider.</span></span> <span data-ttu-id="86d79-116">По умолчанию для всех интерактивных пользователей включена Федерация домена и могут связываться со всеми доменами.</span><span class="sxs-lookup"><span data-stu-id="86d79-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="86d79-117">Если вы определите заблокированные и разрешенные домены, определите домены, которые вы явно разрешите или явным образом заблокируйте.</span><span class="sxs-lookup"><span data-stu-id="86d79-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="86d79-118">Для Интернет-Федерации необходимо спланировать исключения брандмауэра, сертификаты и узел DNS (A или AAAA, если используется IPv6).</span><span class="sxs-lookup"><span data-stu-id="86d79-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="86d79-119">Кроме того, следует настроить политики федерации.</span><span class="sxs-lookup"><span data-stu-id="86d79-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="86d79-120">Дополнительные сведения см. в статье [планирование для интеграции Lync server 2013 и Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="86d79-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

