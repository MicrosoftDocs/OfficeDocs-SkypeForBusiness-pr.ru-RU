---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="8ed43-102">Перенос серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="8ed43-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ed43-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8ed43-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8ed43-104">Если вы развернули сервер архивации и сервер мониторинга в Office Communications Server 2007 R2, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8ed43-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="8ed43-105">Тем не менее, если функции архивации и мониторинга важны для вашей организации, необходимо добавить архивацию и мониторинг в пилотный пул перед переходом, чтобы обеспечить доступность функций в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="8ed43-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="8ed43-106">Если вы хотите выполнять архивацию и мониторинг на этапе миграции и сосуществования, учитывайте указанные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="8ed43-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="8ed43-107">Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ed43-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="8ed43-108">Данные, которые вы заархивированы перед списанием устаревшей среды, будут журналом активности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ed43-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="8ed43-109">Версия архивации сервера и сервера мониторинга Office Communications Server 2007 R2 может быть связана только с внешним интерфейсом пула Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ed43-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="8ed43-110">В Lync Server 2013 возможности архивации и мониторинга больше не являются серверными ролями, но службы, интегрированные в пул переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ed43-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="8ed43-111">В течение времени существования устаревших развертываний и сред Lync Server 2013 версия Office Communications Server 2007 R2 сервера архивации и мониторинг сервера собирают данные для пользователей, размещенных на пулах Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ed43-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="8ed43-112">Версия Lync Server 2013 для архивации сервера и сервера мониторинга собирают данные для пользователей, которые хранятся в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ed43-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ed43-113">На этапе миграции при использовании устаревшего пограничного сервера с новым пулом Lync Server 2013 Pilot версия сервера архивации Office Communications Server 2007 R2 продолжает собирать данные для пользователей, размещенных на сервере Office Communications Server 2007 Пулы R2 и Lync Server 2013 версия сервера архивации собирает данные для пользователей, которые хранятся в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ed43-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="8ed43-114">Если вы используете стороннее решение для архивации и мониторинга в сочетании с сервером архивирования и мониторинга, обратитесь к своему поставщику о том, когда и как следует интегрировать сторонние решения с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ed43-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

