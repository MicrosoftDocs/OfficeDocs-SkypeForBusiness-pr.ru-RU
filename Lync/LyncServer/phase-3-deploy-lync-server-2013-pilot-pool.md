---
title: 'Этап 3: развертывание пула Lync Server 2013 Pilot'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345fe1a110a4521fddde239681891a1491a17cca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="b8e3c-102">Этап 3: развертывание пула Lync Server 2013 Pilot</span><span class="sxs-lookup"><span data-stu-id="b8e3c-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8e3c-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b8e3c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b8e3c-104">В этом разделе описаны действия, которые необходимо выполнить для развертывания пилотного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8e3c-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="b8e3c-105">Для развертывания Lync Server 2013 необходимо, чтобы определить топологию и компоненты, которые вы хотите развернуть, с помощью построителя топологии, подготовить среду для развертывания компонентов Lync Server 2013 и опубликовать структуру топологии на первом интерфейсе. Сервер, а затем Установка и настройка программного обеспечения Lync Server 2013 для компонентов, которые нужно развернуть.</span><span class="sxs-lookup"><span data-stu-id="b8e3c-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="b8e3c-106">По завершении развертывание проекта Lync Server 2013 для пилотного пула будет сосуществовать с существующим пулом Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b8e3c-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b8e3c-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="b8e3c-107">In This Section</span></span>

  - [<span data-ttu-id="b8e3c-108">Подготовка Active Directory для Lync Server</span><span class="sxs-lookup"><span data-stu-id="b8e3c-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="b8e3c-109">Загрузка топологии из существующего развертывания</span><span class="sxs-lookup"><span data-stu-id="b8e3c-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="b8e3c-110">Развертывание пула Lync Server 2013 Pilot</span><span class="sxs-lookup"><span data-stu-id="b8e3c-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="b8e3c-111">Проверка возможности совместного использования пилотного и старого пула</span><span class="sxs-lookup"><span data-stu-id="b8e3c-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="b8e3c-112">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="b8e3c-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="b8e3c-113">Настройка политик доступа и сертификатов шлюза XMPP</span><span class="sxs-lookup"><span data-stu-id="b8e3c-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

