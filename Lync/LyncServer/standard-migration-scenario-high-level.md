---
title: Стандартный сценарий миграции — высокоуровневый
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="8a8e9-102">Стандартный сценарий миграции — высокоуровневый</span><span class="sxs-lookup"><span data-stu-id="8a8e9-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a8e9-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="8a8e9-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8a8e9-104">Используйте следующие элементы в качестве отправной точки при переносе Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group Chat на Lync Server 2013 и на сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8a8e9-105">Стандартный путь миграции Lync Server 2013 выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a8e9-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="8a8e9-106">Ваша организация ранее развернула Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group чата, и вы хотите развернуть Lync Server 2013 на сервере сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="8a8e9-107">Разверните Lync Server 2013, а затем разверните пулы серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="8a8e9-108">Подготовьте и запланируйте миграцию сохраненных комнат чатов и определите, какое время нужно выключить систему для миграции.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="8a8e9-109">Запустите командлеты Windows PowerShell для миграции (**Export-ксперсистентчатдата** и **Import-ксперсистентчатдата**), чтобы переместить содержимое на сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="8a8e9-110">Убедитесь, что миграция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="8a8e9-111">Списание устаревшего развертывания.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="8a8e9-112">Настройте сохраняемый сервер чата таким образом, чтобы устаревшие клиенты могли подключаться к Lync Server 2013, серверу сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8a8e9-113">Это необходимо, так как требуется время для развертывания новых клиентов, и вы хотите разрешить существующим пользователям старых клиентов получить доступ к своим комнатам чата, как только это станет возможным.</span><span class="sxs-lookup"><span data-stu-id="8a8e9-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="8a8e9-114">Развертывайте новые клиенты, продолжая обеспечивать доступ к своим комнатам чата сотрудникам с помощью устаревшего группового чата (клиентов).</span><span class="sxs-lookup"><span data-stu-id="8a8e9-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

