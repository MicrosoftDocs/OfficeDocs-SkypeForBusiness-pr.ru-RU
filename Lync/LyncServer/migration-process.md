---
title: Процесс миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d941b97080bf4ffd0efc87549c5a4fb80c1275c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="fc651-102">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="fc651-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc651-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fc651-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fc651-104">Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 — параллельная миграция.</span><span class="sxs-lookup"><span data-stu-id="fc651-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="fc651-105">В этом разделе описывается, почему следует использовать параллельную миграцию, а также сведения о тестировании сосуществования.</span><span class="sxs-lookup"><span data-stu-id="fc651-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="fc651-106">Параллельная миграция</span><span class="sxs-lookup"><span data-stu-id="fc651-106">Side-By-Side Migration</span></span>

<span data-ttu-id="fc651-107">Почти во всех случаях следует использовать параллельную миграцию.</span><span class="sxs-lookup"><span data-stu-id="fc651-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="fc651-108">При параллельной миграции вы развертываете новый сервер с Lync Server 2013 наряду с соответствующим сервером, на котором работает Lync Server 2010, а затем перенесите операции на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="fc651-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="fc651-109">Если потребуется выполнить откат к Lync Server 2010, только переместит операции на исходные серверы.</span><span class="sxs-lookup"><span data-stu-id="fc651-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="fc651-110">Имейте в виду, что в этом случае проведение новых собраний, запланированных с помощью обновленных клиентов, будет невозможно, и клиенты также потребуется откатить до предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="fc651-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="fc651-111">Тестирование сосуществования</span><span class="sxs-lookup"><span data-stu-id="fc651-111">Coexistence Testing</span></span>

<span data-ttu-id="fc651-112">После развертывания Lync Server 2013 параллельно с Lync Server 2010 развертывание представляет состояние тестирования сосуществования Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fc651-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="fc651-113">В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты могут общаться с текущими и устаревшими пользователями.</span><span class="sxs-lookup"><span data-stu-id="fc651-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="fc651-114">Перед миграцией всех пользователей крайне важно оценить состояние каждого развертывания и убедиться в его работоспособности.</span><span class="sxs-lookup"><span data-stu-id="fc651-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="fc651-115">Как правило, этап тестирования сосуществования существует во время пилотного тестирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc651-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="fc651-116">Устаревшие пользователи перемещаются в Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу совместимости и функций и функций приложений.</span><span class="sxs-lookup"><span data-stu-id="fc651-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="fc651-117">После пилотного тестирования пользователи и приложения перемещаются в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Lync Server 2010 будут отменены.</span><span class="sxs-lookup"><span data-stu-id="fc651-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

