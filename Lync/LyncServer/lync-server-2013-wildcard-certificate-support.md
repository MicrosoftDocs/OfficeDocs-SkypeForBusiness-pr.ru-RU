---
title: 'Lync Server 2013: поддержка групповых сертификатов'
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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="2d5e3-102">Поддержка групповых сертификатов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d5e3-103">_**Тема последнего изменения:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="2d5e3-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="2d5e3-104">Lync Server 2013 использует сертификаты для обеспечения шифрования связи и проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="2d5e3-105">В некоторых случаях, например, веб-публикации с помощью обратного прокси, не требуется полное доменное имя (FQDN) сервера, на котором не указана служба.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="2d5e3-106">В этих случаях вы можете использовать сертификаты с подстановочными знаками SAN (обычно называемыми подстановочными сертификатами), чтобы снизить стоимость сертификата, запрашиваемого общедоступным центром сертификации, и уменьшить сложность процесса планирования для сертификатов. .</span><span class="sxs-lookup"><span data-stu-id="2d5e3-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2d5e3-107">Чтобы сохранить функциональность устройств с единым коммуникационным подключением (например, стационарных телефонов), необходимо тщательно протестировать развернутый сертификат, чтобы убедиться, что устройства правильно работают после реализации сертификата с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="2d5e3-108">В качестве имени субъекта (также называемого общим именем или CN) отсутствует поддержка подстановочных знаков для любой роли.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="2d5e3-109">При использовании подстановочных элементов в сети хранения данных поддерживаются следующие роли сервера.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-110">**Обратный прокси-сервер.**    Подстановочные знаки в сети хранения данных поддерживаются для простого сертификата публикации URL-адреса (сопоставления и набора номера).</span><span class="sxs-lookup"><span data-stu-id="2d5e3-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-111">**Обратный прокси-сервер.**    Запись с подстановочными знаками в сети SAN поддерживается для записей San для LyncDiscover сертификата публикации.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-112">**Режиссер.**    Подстановочные знаки в сети хранения данных поддерживаются для простых URL-адресов (для звонков и набора номера) и для записей San для LyncDiscover и линкдисковеринтернал в компонентах Director.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-113">**Сервер переднего плана (стандартный выпуск) и пул переднего плана (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="2d5e3-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="2d5e3-114">Подстановочные знаки в сети хранения данных поддерживаются для простых URL-адресов (для звонков и набора номера) и для записей SAN для LyncDiscover и Линкдисковеринтернал на веб-компонентах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-115">**Единая система обмена сообщениями Exchange (UM).**    Сервер не использует записи San при развертывании в качестве изолированного сервера.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-116">**Сервер клиентского доступа Microsoft Exchange Server.**    Записи с подстановочными знаками в сети хранения данных поддерживаются для внутренних и внешних клиентов.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="2d5e3-117">**Единая система обмена сообщениями (UM) и сервер клиентского доступа Microsoft Exchange Server на одном и том же сервере.**    Поддерживаются записи с подстановочными знаками в сети хранения данных.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="2d5e3-118">Роли сервера, не описанные в этом разделе:</span><span class="sxs-lookup"><span data-stu-id="2d5e3-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="2d5e3-119">Внутренние роли сервера (в том числе сервер-посредник, Архивация и мониторинг сервера, бесперебойно работающего филиала, а также бесперебойно работающего сервера филиалов)</span><span class="sxs-lookup"><span data-stu-id="2d5e3-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="2d5e3-120">Внешние интерфейсы пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2d5e3-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="2d5e3-121">Внутренний пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="2d5e3-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d5e3-122">В интерфейсе внутренней серверной граничного сервера можно назначить элементу SAN подстановочный знак и поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="2d5e3-123">Сеть хранения данных на внутреннем пограничном сервере не запрашивается, а для записи с подстановочными знаками в сети хранения данных — ограниченные значения.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="2d5e3-124">Дополнительные сведения о конфигурациях сертификатов, в том числе использование подстановочных знаков в сертификатах, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2d5e3-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="2d5e3-125">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="2d5e3-126">Требования к сертификатам для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="2d5e3-127">Сводка по сертификатам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="2d5e3-128">Сводка по сертификатам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="2d5e3-129">Сводка по сертификатам — масштабированный пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="2d5e3-130">Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="2d5e3-131">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5e3-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="2d5e3-132">Дополнительные сведения о настройке сертификатов для Exchange, в том числе использование подстановочных знаков, можно найти в документации по продукту Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2d5e3-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

