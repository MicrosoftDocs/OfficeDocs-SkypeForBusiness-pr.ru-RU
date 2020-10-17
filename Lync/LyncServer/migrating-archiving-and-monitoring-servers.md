---
title: Перенос серверов архивирования и мониторинга
description: Перенос серверов архивации и мониторинга.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabd16fd38dbf463a4bc608fe77368e781571fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565385"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="a6bce-103">Перенос серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="a6bce-103">Migrating Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6bce-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a6bce-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a6bce-105">Если вы развернули сервер архивации и сервер мониторинга в среде Lync Server 2010, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a6bce-105">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="a6bce-106">Если функции архивации и мониторинга критически важны для вашей организации, следует добавить архивацию и мониторинг в пилотный пул Lync Server 2013 перед переносом, чтобы обеспечить доступность функций в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="a6bce-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="a6bce-107">Если функции архивации и мониторинга должны быть доступны во время миграции, помните о следующем.</span><span class="sxs-lookup"><span data-stu-id="a6bce-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="a6bce-108">Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6bce-108">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a6bce-109">Данные, резервные копии которых были созданы перед ликвидацией старой среды, будут указаны в журнале действий в среде Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6bce-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="a6bce-110">Lync Server 2010 версии сервера архивации и сервера мониторинга можно связать только с интерфейсным пулом Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6bce-110">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="a6bce-111">В Lync Server 2013 Архивация и мониторинг больше не являются ролями серверов, но службы, интегрированные в интерфейсный пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6bce-111">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="a6bce-112">Во время совместного использования устаревших развертываний и развертываний Lync Server 2013 версия сервера архивации и сервера мониторинга Lync Server 2010 собирает данные для пользователей, размещенных в пулах Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6bce-112">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="a6bce-113">Архивация и мониторинг в Lync Server 2013 сбор данных для пользователей, размещенных в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6bce-113">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6bce-114">На этапе миграции, когда вы по-прежнему используете старый пограничный сервер с новым пилотным пулом Lync Server 2013, версия сервера архивации для Lync Server 2010 продолжает собирать данные для пользователей, размещенных на сервере Lync Server 2010 Pools и архивация в Lync Server 2013 собирает данные для пользователей, размещенных в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6bce-114">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="a6bce-115">Если вы используете решение для архивации и мониторинга стороннего производителя в сочетании с архивацией и мониторингом в Lync Server 2013, обратитесь к поставщику за сведениями о том, когда и как следует интегрировать стороннее решение с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6bce-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

