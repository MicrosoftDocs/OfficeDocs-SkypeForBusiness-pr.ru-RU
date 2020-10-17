---
title: Поддержка подстановочных сертификатов Lync Server 2013
description: Поддержка подстановочных сертификатов Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46cc362eb925a86b5e90d51569db6d425ba88fa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546115"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="db3f3-103">Поддержка сертификатов с подстановочными знаками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-103">Wildcard certificate support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db3f3-104">_**Последнее изменение темы:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="db3f3-104">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="db3f3-105">Lync Server 2013 использует сертификаты для обеспечения шифрования связи и проверки подлинности сервера удостоверений.</span><span class="sxs-lookup"><span data-stu-id="db3f3-105">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="db3f3-106">В некоторых ситуациях, таких как веб-публикация через обратный прокси-сервер, строгое соответствие записи альтернативного имени субъекта с полным доменным именем сервера, представляющего службу, не требуется.</span><span class="sxs-lookup"><span data-stu-id="db3f3-106">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="db3f3-107">В этом случае вы можете использовать сертификаты с записями альтернативного имени субъекта с подстановочными знаками (более известные как «групповые сертификаты»), чтобы сократить стоимость сертификата, запрашиваемого из общего центра сертификации и снизить сложность процесса планирования для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="db3f3-107">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="db3f3-108">Чтобы сохранить функциональные возможности устройств объединенных коммуникаций (например, стационарного телефона), вам следует тщательно протестировать развернутый сертификат и убедиться, что после применения группового сертификата все устройства работаю правильно.</span><span class="sxs-lookup"><span data-stu-id="db3f3-108">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="db3f3-p102">Ни для одной из ролей нет поддержки записи с подстановочными знаками в качестве имени субъекта (которое также называется общим именем). При использовании записей с подстановочными знаками в альтернативном имени субъекта поддерживаются следующие роли сервера:</span><span class="sxs-lookup"><span data-stu-id="db3f3-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-111">**Обратный прокси-сервер.**     Для сертификата публикации простого URL-адреса (сопоставления и дозвона) поддерживается запись с подстановочными знаками сети.</span><span class="sxs-lookup"><span data-stu-id="db3f3-111">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-112">**Обратный прокси-сервер.**     Запись с подстановочными знаками в сети хранения данных поддерживается для записей SAN для LyncDiscover в сертификате публикации.</span><span class="sxs-lookup"><span data-stu-id="db3f3-112">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-113">**Директор.**     Запись с подстановочными знаками поддерживается для простых URL-адресов (для входящих и исходящих звонков) и для записей сети SAN для LyncDiscover и LyncDiscoverInternal в веб-компонентах Director.</span><span class="sxs-lookup"><span data-stu-id="db3f3-113">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-114">**Сервер переднего плана (Standard Edition) и пул переднего плана (корпоративный выпуск).**</span><span class="sxs-lookup"><span data-stu-id="db3f3-114">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="db3f3-115">Подстановочные знаки в сети хранения данных поддерживаются для простых URL-адресов (для входящих и исходящих звонков) и для записей сети SAN для LyncDiscover и LyncDiscoverInternal в интерфейсных веб-компонентах.</span><span class="sxs-lookup"><span data-stu-id="db3f3-115">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-116">**Единая система обмена сообщениями Exchange.**     Сервер не использует записи SAN при развертывании в качестве изолированного сервера.</span><span class="sxs-lookup"><span data-stu-id="db3f3-116">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-117">**Сервер клиентского доступа Microsoft Exchange Server.**     Записи с подстановочными знаками в SAN поддерживаются для внутренних и внешних клиентов.</span><span class="sxs-lookup"><span data-stu-id="db3f3-117">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="db3f3-118">**Единая система обмена сообщениями Exchange и сервер клиентского доступа Microsoft Exchange Server на одном и том же сервере.**     Поддерживаются подстановочные записи в сети хранения данных.</span><span class="sxs-lookup"><span data-stu-id="db3f3-118">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="db3f3-119">Роли сервера, которые не рассматриваются в данном разделе:</span><span class="sxs-lookup"><span data-stu-id="db3f3-119">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="db3f3-120">Внутренние роли сервера (в том числе сервер-посредник, сервер архивации и мониторинга, устройство для обеспечения связи в филиалах, а также сервер для обеспечения связи в филиалах)</span><span class="sxs-lookup"><span data-stu-id="db3f3-120">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="db3f3-121">Интерфейсы внешних пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="db3f3-121">External Edge Server interfaces</span></span>

  - <span data-ttu-id="db3f3-122">Внутренний пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="db3f3-122">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db3f3-123">Для внутреннего интерфейса пограничного сервера для сети хранения данных можно назначить подстановочный знак, который поддерживается.</span><span class="sxs-lookup"><span data-stu-id="db3f3-123">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="db3f3-124">Сеть хранения данных на внутреннем пограничном сервере не запрашивается, а для записи с подстановочными знаками в сети хранения данных используется ограниченное значение.</span><span class="sxs-lookup"><span data-stu-id="db3f3-124">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="db3f3-125">Дополнительные сведения о конфигурациях сертификатов, включая использование подстановочных знаков в сертификатах, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="db3f3-125">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="db3f3-126">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-126">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="db3f3-127">Требования к сертификатам для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-127">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="db3f3-128">Сводка по сертификатам: Балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-128">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="db3f3-129">Сводка по сертификатам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-129">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="db3f3-130">Сводка по сертификатам — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-130">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="db3f3-131">Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-131">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="db3f3-132">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db3f3-132">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="db3f3-133">Для получения дополнительных сведений о настройке сертификатов для Exchange, в том числе об использовании подстановочных знаков, обратитесь к документации по продукту Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="db3f3-133">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

