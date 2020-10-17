---
title: 'Этап 3: Развертывание пилотного пула Lync Server 2013'
description: 'Этап 3: Развертывание пилотного пула Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f72f0cdd2e7d3b9e29891a4adc0ab0551539f465
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571165"
---
# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="d085a-103">Этап 3: Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d085a-103">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d085a-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d085a-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d085a-105">В этом разделе описываются действия, необходимые для развертывания пилотного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d085a-105">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="d085a-106">Для развертывания Lync Server 2013 необходимо использовать построитель топологий для определения топологии и компонентов, которые необходимо развернуть, подготовки среды к развертыванию компонентов Lync Server 2013, публикации структуры топологии на первом сервере переднего плана, а затем установки и настройки программного обеспечения Lync Server 2013 для компонентов для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="d085a-106">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="d085a-107">По завершении развертывания пилотного пула Lync Server 2013 будет сосуществовать в существующем пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d085a-107">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d085a-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="d085a-108">In This Section</span></span>

  - [<span data-ttu-id="d085a-109">Подготовка Active Directory для Lync Server</span><span class="sxs-lookup"><span data-stu-id="d085a-109">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="d085a-110">Загрузка топологии из существующего развертывания</span><span class="sxs-lookup"><span data-stu-id="d085a-110">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="d085a-111">Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d085a-111">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="d085a-112">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="d085a-112">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="d085a-113">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="d085a-113">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="d085a-114">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="d085a-114">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

