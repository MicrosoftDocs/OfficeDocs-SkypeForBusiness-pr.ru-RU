---
title: Перенос федерации XMPP
description: Миграция Федерации XMPP.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543215"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="5e1db-103">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5e1db-103">Migrating XMPP federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e1db-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5e1db-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5e1db-105">Предыдущие версии Lync Server и Office Communications Server предоставили шлюз XMPP (Extensible Messaging and Presence Protocol), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с развертываниями XMPP.</span><span class="sxs-lookup"><span data-stu-id="5e1db-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="5e1db-106">В Lync Server 2013 функция XMPP может быть развернута в качестве компонента.</span><span class="sxs-lookup"><span data-stu-id="5e1db-106">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="5e1db-107">Функции XMPP установлены в двух частях: в качестве прокси-сервера XMPP, работающего на пограничном сервере Lync Server 2013, и шлюза XMPP, работающего на сервере переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e1db-107">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="5e1db-108">С точки зрения миграции учетная запись пользователя Lync Server может быть перемещена в пул Lync Server 2013 и продолжать использовать устаревший шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="5e1db-108">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="5e1db-109">Это возможно только в том случае, если федеративный партнер XMPP не настроен в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e1db-109">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="5e1db-110">В целом, если Lync Server 2010 был развернут с шлюзом Office Communications Server 2007 R2 XMPP и для Федерации XMPP включен доступ к старым пользователям Lync Server 2010, для переноса Федерации XMPP в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="5e1db-110">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="5e1db-111">Разверните пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e1db-111">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="5e1db-112">Развертывание пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e1db-112">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="5e1db-113">Перемещение всех пользователей в пул Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e1db-113">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="5e1db-114">Создайте сертификаты и политики доступа XMPP для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5e1db-114">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="5e1db-115">Включите Федерацию XMPP в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e1db-115">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="5e1db-116">Обновите записи DNS, чтобы они ссылались на шлюз XMPP Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e1db-116">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

