---
title: Процесс миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2771a7a8b29cf410f9da5155e8f379bd7efe0e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="e02fd-102">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="e02fd-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02fd-103">_**Тема последнего изменения:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="e02fd-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e02fd-104">Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 — это процедура параллельной миграции.</span><span class="sxs-lookup"><span data-stu-id="e02fd-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="e02fd-105">В этой статье описаны причины, по которым следует использовать параллельную миграцию, а также сведения о сосуществовании.</span><span class="sxs-lookup"><span data-stu-id="e02fd-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="e02fd-106">Переход с одной стороны на другую</span><span class="sxs-lookup"><span data-stu-id="e02fd-106">Side-by-Side Migration</span></span>

<span data-ttu-id="e02fd-107">Почти во всех случаях миграции следует использовать путь параллельной миграции.</span><span class="sxs-lookup"><span data-stu-id="e02fd-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="e02fd-108">При переходе по отдельности вы можете развернуть новый сервер с помощью Lync Server 2013 и соответствующего сервера, на котором запущен Office Communications Server 2007 R2, а затем перенести операции на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="e02fd-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="e02fd-109">Если вы хотите вернуться к Office Communications Server 2007 R2, вам нужно будет только перевернуть их на первоначальные серверы.</span><span class="sxs-lookup"><span data-stu-id="e02fd-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="e02fd-110">Имейте в виду, что в этом случае новые собрания, запланированные на обновленных клиентах, не будут работать, а клиентам также потребуется понизить уровень.</span><span class="sxs-lookup"><span data-stu-id="e02fd-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="e02fd-111">Тестирование сосуществования</span><span class="sxs-lookup"><span data-stu-id="e02fd-111">Coexistence Testing</span></span>

<span data-ttu-id="e02fd-112">После развертывания Lync Server 2013 параллельно с Office Communications Server 2007 R2 топология представляет состояние тестирования сосуществования Lync Server 2013 и Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e02fd-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="e02fd-113">В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты смогут общаться с текущими и устаревшими пользователями.</span><span class="sxs-lookup"><span data-stu-id="e02fd-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="e02fd-114">Прежде чем переходить от всех пользователей, очень важно понять состояние каждого развертывания и убедиться, что каждое развертывание работает и работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e02fd-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="e02fd-115">Как правило, этап тестирования сосуществования используется во время пилотного тестирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e02fd-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="e02fd-116">Пользователи прежних версий перемещаются на Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу функций и функций.</span><span class="sxs-lookup"><span data-stu-id="e02fd-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="e02fd-117">После пилотной проверки пользователи и приложения перемещаются в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Office Communications Server 2007 R2 будут прекращены.</span><span class="sxs-lookup"><span data-stu-id="e02fd-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

