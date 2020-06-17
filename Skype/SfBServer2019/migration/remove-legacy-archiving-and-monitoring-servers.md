---
title: Удаление старых серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если устаревшее развертывание содержит сервер архивации или сервер мониторинга, то после перехода на Skype для бизнеса Server 2019 эти серверы можно удалить из устаревшей среды, при этом все пользователи удалены из всех оставшихся устаревших пулов. Сервер архивирования и сервер мониторинга можно удалять в любом порядке. Главное требование состоит в удалении всех пользователей из всех оставшихся устаревших пулов.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752171"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="10948-105">Удаление старых серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="10948-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="10948-106">Если устаревшее развертывание содержит сервер архивации или сервер мониторинга, после перехода на Skype для бизнеса Server 2019 эти серверы можно удалить из устаревшей среды, если все пользователи удалены из всех оставшихся устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="10948-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="10948-107">Сервер архивирования и сервер мониторинга можно удалять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="10948-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="10948-108">Главное требование состоит в удалении всех пользователей из всех оставшихся устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="10948-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="10948-109">Вы можете переместить пользователей в Skype для бизнеса Server 2019, выполнив процедуры, описанные в [шаге 4: Move Test users to the пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="10948-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="10948-110">После подтверждения того, что все пользователи удалены из всех оставшихся пулов, декоммисион сервер и удаляет роли.</span><span class="sxs-lookup"><span data-stu-id="10948-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="10948-111">Устаревшее, но уместное, пример "удаление Microsoft Lync Server и удаление ролей сервера", которые можно скачать на сайте [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="10948-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

