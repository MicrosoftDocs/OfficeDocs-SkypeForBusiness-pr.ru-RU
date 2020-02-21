---
title: Стандартный сценарий миграции — высокий уровень
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b2dd76a071c01c74f3d42f9c1ffbfa76c4a924
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="83a27-102">Стандартный сценарий миграции — высокий уровень</span><span class="sxs-lookup"><span data-stu-id="83a27-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83a27-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="83a27-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="83a27-104">Используйте следующие элементы в качестве отправной точки при переносе Lync Server 2010, группового чата или Office Communications Server 2007 R2 на Lync Server 2013, сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="83a27-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="83a27-105">Стандартный путь миграции Lync Server 2013 выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83a27-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="83a27-106">В Организации ранее было развернуто Lync Server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat, и вы хотите развернуть Lync Server 2013, сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="83a27-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="83a27-107">Разверните Lync Server 2013, а затем разверните пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="83a27-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="83a27-108">Подготовьте и запланируйте миграцию комнат сохраняемого чата и определите время, необходимое для завершения миграции системы.</span><span class="sxs-lookup"><span data-stu-id="83a27-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="83a27-109">Выполните командлеты Windows PowerShell для миграции (**Export-CsPersistentChatData** и **Import-CsPersistentChatData**), чтобы переместить контент на сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="83a27-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="83a27-110">Убедитесь, что перенос прошел успешно.</span><span class="sxs-lookup"><span data-stu-id="83a27-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="83a27-111">Выведите из эксплуатации устаревшее развертывание.</span><span class="sxs-lookup"><span data-stu-id="83a27-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="83a27-112">Настройте сервер сохраняемого чата, чтобы устаревшие клиенты могли подключаться к серверу сохраняемого чата в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83a27-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="83a27-113">Это необходимо, так как для развертывания новых клиентов нужно время, а вам нужно предоставить текущим пользователям с устаревшими клиентами доступ к комнатам чата как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="83a27-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="83a27-114">Развертывайте новые клиенты, не отключаясь, чтобы сотрудники со старым сеансом группы (клиенты) могли попасть в комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="83a27-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

