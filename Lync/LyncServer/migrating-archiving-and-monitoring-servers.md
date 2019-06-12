---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901961ad7456dfd8b0340cba03ff44a9e77a147f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="c0111-102">Перенос серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="c0111-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0111-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c0111-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c0111-104">Если вы развернули сервер архивации и сервер мониторинга в среде Lync Server 2010, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c0111-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="c0111-105">Тем не менее, если функции архивации и мониторинга критически важны для вашей организации, необходимо добавить архивацию и мониторинг в пул Lync Server 2013 Pilot, прежде чем вы сможете выполнить миграцию, чтобы они были доступны в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="c0111-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="c0111-106">Если вы хотите использовать функции архивации и наблюдения в процессе миграции, имейте в виду следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="c0111-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="c0111-107">Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0111-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="c0111-108">Данные, которые вы заархивированы перед списанием устаревшей среды, будут журналом действий в среде Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c0111-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="c0111-109">Версия Lync Server 2010 для архивации сервера и сервера мониторинга может быть связана только с интерфейсом front end сервера Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c0111-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="c0111-110">В Lync Server 2013 возможности архивации и мониторинга больше не являются серверными ролями, но службы, интегрированные в пул переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0111-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="c0111-111">В течение времени существования устаревших развертываний и сред Lync Server 2013 версия сервера архивации и мониторинга сервера Lync Server 2010 собирает данные для пользователей, размещенных в пулах Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c0111-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="c0111-112">Архивация и мониторинг в Lync Server 2013 сбор данных для пользователей, размещенных в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0111-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0111-113">На этапе миграции при использовании устаревшего пограничного сервера с новым пулом Lync Server 2013 Pilot версия сервера архивирования для Lync Server 2010 продолжает собирать данные для пользователей, размещенных на Lync Server 2010 пулов и архивации в Lync Server 2013 сбор данных для пользователей, размещенных в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0111-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="c0111-114">Если вы используете сторонние решения для архивации и мониторинга в сочетании с архивацией и мониторингом в Lync Server 2013, обратитесь к своему поставщику о том, когда и как следует интегрировать сторонние решения с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0111-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

