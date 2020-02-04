---
title: Стандартный сценарий миграции — высокоуровневый
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
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="c2b16-102">Стандартный сценарий миграции — высокоуровневый</span><span class="sxs-lookup"><span data-stu-id="c2b16-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b16-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c2b16-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c2b16-104">Используйте следующие элементы в качестве отправной точки при переносе Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group Chat на Lync Server 2013 и на сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c2b16-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="c2b16-105">Стандартный путь миграции Lync Server 2013 выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c2b16-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="c2b16-106">Ваша организация ранее развернула Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group чата, и вы хотите развернуть Lync Server 2013 на сервере сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c2b16-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="c2b16-107">Разверните Lync Server 2013, а затем разверните пулы серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c2b16-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="c2b16-108">Подготовьте и запланируйте миграцию сохраненных комнат чатов и определите, какое время нужно выключить систему для миграции.</span><span class="sxs-lookup"><span data-stu-id="c2b16-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="c2b16-109">Запустите командлеты Windows PowerShell для миграции (**Export-ксперсистентчатдата** и **Import-ксперсистентчатдата**), чтобы переместить содержимое на сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="c2b16-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="c2b16-110">Убедитесь, что миграция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="c2b16-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="c2b16-111">Списание устаревшего развертывания.</span><span class="sxs-lookup"><span data-stu-id="c2b16-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="c2b16-112">Настройте сохраняемый сервер чата таким образом, чтобы устаревшие клиенты могли подключаться к Lync Server 2013, серверу сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c2b16-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="c2b16-113">Это необходимо, так как требуется время для развертывания новых клиентов, и вы хотите разрешить существующим пользователям старых клиентов получить доступ к своим комнатам чата, как только это станет возможным.</span><span class="sxs-lookup"><span data-stu-id="c2b16-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="c2b16-114">Развертывайте новые клиенты, продолжая обеспечивать доступ к своим комнатам чата сотрудникам с помощью устаревшего группового чата (клиентов).</span><span class="sxs-lookup"><span data-stu-id="c2b16-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

