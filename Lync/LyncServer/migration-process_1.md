---
title: Процесс миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="495db-102">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="495db-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="495db-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="495db-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="495db-104">Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 — это параллельная процедура миграции.</span><span class="sxs-lookup"><span data-stu-id="495db-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="495db-105">В этом разделе описываются причины для использования параллельной миграции и приводятся сведения о сосуществовании.</span><span class="sxs-lookup"><span data-stu-id="495db-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="495db-106">Параллельная миграция</span><span class="sxs-lookup"><span data-stu-id="495db-106">Side-by-Side Migration</span></span>

<span data-ttu-id="495db-107">Почти во всех случаях следует использовать параллельную миграцию.</span><span class="sxs-lookup"><span data-stu-id="495db-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="495db-108">При параллельной миграции вы развертываете новый сервер с Lync Server 2013 наряду с соответствующим сервером, на котором работает Office Communications Server 2007 R2, а затем переносите операции на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="495db-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="495db-109">Если потребуется выполнить откат к серверу Office Communications Server 2007 R2, только переместит операции обратно на исходные серверы.</span><span class="sxs-lookup"><span data-stu-id="495db-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="495db-110">Имейте в виду, что в этом случае проведение новых собраний, запланированных с помощью обновленных клиентов, будет невозможно, и клиенты также потребуется откатить до предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="495db-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="495db-111">Тестирование сосуществования</span><span class="sxs-lookup"><span data-stu-id="495db-111">Coexistence Testing</span></span>

<span data-ttu-id="495db-112">После развертывания Lync Server 2013 параллельно с Office Communications Server 2007 R2 топология представляет состояние тестирования сосуществования Lync Server 2013 и Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="495db-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="495db-113">Пока топология находится в этом состоянии, необходимо убедиться в том, что службы запускаются, все сайты доступны для администрирования и клиенты обеспечивают взаимодействие как с новыми, так и со старыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="495db-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="495db-114">Перед миграцией всех пользователей крайне важно оценить состояние каждого развертывания и убедиться в его работоспособности.</span><span class="sxs-lookup"><span data-stu-id="495db-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="495db-115">Как правило, этап тестирования сосуществования существует во время пилотного тестирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="495db-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="495db-116">Устаревшие пользователи перемещаются в Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу совместимости и функций и функций приложений.</span><span class="sxs-lookup"><span data-stu-id="495db-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="495db-117">После пилотного тестирования пользователи и приложения переносятся в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Office Communications Server 2007 R2 будут отменены.</span><span class="sxs-lookup"><span data-stu-id="495db-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

