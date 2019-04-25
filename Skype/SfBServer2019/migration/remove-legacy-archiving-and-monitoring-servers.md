---
title: Удаление старых серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если устаревшее развертывание содержит сервера архивирование или сервера мониторинга, после миграции в Скайп for Business Server 2019, этих серверов можно удалить из старой среды условии, что все пользователи удалены из всех оставшихся пулов прежних версий. Архивация сервера или сервера мониторинга можно удалить в любой последовательности. Ключевые требование заключается в том, что все пользователи были удалены из всех оставшихся пулов прежних версий.
ms.openlocfilehash: 5a3a691c8f2e8a4ad3610ccf1ea947ce23b74111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231425"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="bd6d1-105">Удаление старых серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="bd6d1-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="bd6d1-106">Если устаревшее развертывание содержится сервера архивирование или сервера мониторинга, после миграции в Скайп for Business Server 2019, этих серверов можно удален из старой среды, при условии, что все пользователи удалены из всех оставшихся пулов прежних версий.</span><span class="sxs-lookup"><span data-stu-id="bd6d1-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="bd6d1-107">Архивация сервера или сервера мониторинга можно удалить в любой последовательности.</span><span class="sxs-lookup"><span data-stu-id="bd6d1-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="bd6d1-108">Ключевые требование заключается в том, что все пользователи были удалены из всех оставшихся пулов прежних версий.</span><span class="sxs-lookup"><span data-stu-id="bd6d1-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="bd6d1-109">Можно переместить пользователей в Скайп для Business Server 2019, выполнив процедуры, описанные в [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="bd6d1-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="bd6d1-110">После подтверждения, что все пользователи удалены из всех оставшихся пулов decommision сервера и удалить роли.</span><span class="sxs-lookup"><span data-stu-id="bd6d1-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="bd6d1-111">Объект не ранее, но соответствующий пример является «Удаление Microsoft Lync Server и удаление роли сервера,» которого можно загрузить на [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="bd6d1-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

