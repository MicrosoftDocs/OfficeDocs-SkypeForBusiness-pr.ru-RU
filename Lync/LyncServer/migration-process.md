---
title: Процесс миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="1dacc-102">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="1dacc-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dacc-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1dacc-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1dacc-104">Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 является параллельной миграцией.</span><span class="sxs-lookup"><span data-stu-id="1dacc-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="1dacc-105">В этой статье описаны причины, по которым следует использовать параллельную миграцию, а также сведения о проверке сосуществования.</span><span class="sxs-lookup"><span data-stu-id="1dacc-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="1dacc-106">Переход с одной стороны на другую</span><span class="sxs-lookup"><span data-stu-id="1dacc-106">Side-By-Side Migration</span></span>

<span data-ttu-id="1dacc-107">Почти во всех случаях миграции следует использовать путь параллельной миграции.</span><span class="sxs-lookup"><span data-stu-id="1dacc-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="1dacc-108">При переходе по отдельности вы развертываете новый сервер с помощью Lync Server 2013 вместе с соответствующим сервером, на котором работает Lync Server 2010, а затем перенесите операции на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="1dacc-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="1dacc-109">Если вы хотите вернуться к Lync Server 2010, вы можете только переместить операции на первоначальный сервер.</span><span class="sxs-lookup"><span data-stu-id="1dacc-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="1dacc-110">Имейте в виду, что в этом случае новые собрания, запланированные на обновленных клиентах, не будут работать, а клиентам также потребуется понизить уровень.</span><span class="sxs-lookup"><span data-stu-id="1dacc-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="1dacc-111">Тестирование сосуществования</span><span class="sxs-lookup"><span data-stu-id="1dacc-111">Coexistence Testing</span></span>

<span data-ttu-id="1dacc-112">После развертывания Lync Server 2013 параллельно с Lync Server 2010 развертывание представляет состояние тестирования сосуществования Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1dacc-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="1dacc-113">В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты смогут общаться с текущими и устаревшими пользователями.</span><span class="sxs-lookup"><span data-stu-id="1dacc-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="1dacc-114">Прежде чем переходить от всех пользователей, очень важно понять состояние каждого развертывания и убедиться, что каждое развертывание работает и работает правильно.</span><span class="sxs-lookup"><span data-stu-id="1dacc-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="1dacc-115">Как правило, этап тестирования сосуществования используется во время пилотного тестирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dacc-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="1dacc-116">Пользователи прежних версий перемещаются на Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу функций и функций.</span><span class="sxs-lookup"><span data-stu-id="1dacc-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="1dacc-117">После пилотной проверки пользователи и приложения перемещаются в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Lync Server 2010 будут прекращены.</span><span class="sxs-lookup"><span data-stu-id="1dacc-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

