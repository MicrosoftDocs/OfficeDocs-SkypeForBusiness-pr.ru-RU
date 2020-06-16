---
title: Удаление старых серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4f149db04be75cec961478f4382b3e7a333e0a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="52ce8-102">Удаление старых серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="52ce8-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52ce8-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="52ce8-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="52ce8-104">Если ваше развертывание Office Communications Server 2007 R2 содержит сервер архивации или сервер мониторинга, то после перехода на Lync Server 2013 эти серверы можно удалить из устаревшей среды, если все пользователи удалены из всех оставшихся пулов Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52ce8-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="52ce8-105">Сервер архивирования и сервер мониторинга можно удалять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="52ce8-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="52ce8-106">Ключевое требование состоит в том, что все пользователи удалены из всех оставшихся пулов Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52ce8-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="52ce8-107">Вы можете переместить пользователей из Office Communications Server 2007 R2 на Lync Server 2013, выполнив процедуры, описанные в [шаге 6: перемещение пользователей в пилотный пул](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="52ce8-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="52ce8-108">После подтверждения того, что все пользователи удалены из всех оставшихся пулов, выполните процедуру, описанную в разделе "удаление серверов и ролей серверов" по адресу [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887) :</span><span class="sxs-lookup"><span data-stu-id="52ce8-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

