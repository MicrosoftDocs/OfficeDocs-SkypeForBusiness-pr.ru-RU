---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="37472-102">Перенос серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="37472-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37472-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="37472-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="37472-104">Если вы развернули сервер архивации и сервер мониторинга в Office Communications Server 2007 R2, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="37472-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="37472-105">Но если функции архивации и мониторинга важны для вашей организации, следует добавить архивацию и мониторинг в пилотный пул перед миграцией, чтобы эти функции были доступны во время переноса.</span><span class="sxs-lookup"><span data-stu-id="37472-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="37472-106">Если функции архивации и мониторинга должны быть доступны во время миграции и на этапе сосуществования, помните о следующем.</span><span class="sxs-lookup"><span data-stu-id="37472-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="37472-107">Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37472-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="37472-108">Данные, которые вы создаете перед списанием устаревшей среды, будут храниться в истории активности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="37472-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="37472-109">Версия сервера архивирования и сервера мониторинга Office Communications Server 2007 R2 может быть связана только с интерфейсным пулом Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="37472-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="37472-110">В Lync Server 2013 Архивация и мониторинг больше не являются ролями серверов, но службы, интегрированные в интерфейсный пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37472-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="37472-111">Во время совместного использования устаревших развертываний и развертываний Lync Server 2013 в Office Communications Server 2007 R2 сервер архивации и сервер мониторинга собирает данные для пользователей, размещенных в пулах Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="37472-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="37472-112">Lync Server 2013 версии сервера архивации и сервера мониторинга собирают данные для пользователей, размещенных в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37472-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37472-113">На этапе миграции, когда вы по-прежнему используете старый пограничный сервер с новым пилотным пулом Lync Server 2013, версия сервера архивации Office Communications Server 2007 R2 продолжает собирать данные для пользователей, размещенных в пулах Office Communications Server 2007 R2, и для сервера Lync Server 2013 версии сервера архивации собирает данные для пользователей, размещенных в пулах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37472-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="37472-114">Если вы используете решение для архивации и мониторинга стороннего производителя вместе с сервером архивации и сервером мониторинга, обратитесь к поставщику за сведениями о том, когда и как следует интегрировать стороннее решение с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37472-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

