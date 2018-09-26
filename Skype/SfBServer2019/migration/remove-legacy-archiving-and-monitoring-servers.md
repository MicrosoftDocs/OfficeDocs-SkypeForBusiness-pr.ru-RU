---
title: Удаление прежних версий Архивация и наблюдение за серверами
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если устаревшее развертывание содержит сервера архивирование или сервера мониторинга, после миграции в Скайп for Business Server 2019, этих серверов можно удалить из старой среды условии, что все пользователи удалены из всех оставшихся пулов прежних версий. Архивация сервера или сервера мониторинга можно удалить в любой последовательности. Ключевые требование заключается в том, что все пользователи были удалены из всех оставшихся пулов прежних версий.
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028616"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="29049-105">Удаление прежних версий Архивация и наблюдение за серверами</span><span class="sxs-lookup"><span data-stu-id="29049-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="29049-106">Если устаревшее развертывание содержится сервера архивирование или сервера мониторинга, после миграции в Скайп for Business Server 2019, этих серверов можно удален из старой среды, при условии, что все пользователи удалены из всех оставшихся пулов прежних версий.</span><span class="sxs-lookup"><span data-stu-id="29049-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="29049-107">Архивация сервера или сервера мониторинга можно удалить в любой последовательности.</span><span class="sxs-lookup"><span data-stu-id="29049-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="29049-108">Ключевые требование заключается в том, что все пользователи были удалены из всех оставшихся пулов прежних версий.</span><span class="sxs-lookup"><span data-stu-id="29049-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="29049-109">Можно переместить пользователей в Скайп для Business Server 2019, выполнив процедуры, описанные в [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="29049-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="29049-110">После подтверждения, что все пользователи удалены из всех оставшихся пулов decommision сервера и удалить роли.</span><span class="sxs-lookup"><span data-stu-id="29049-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="29049-111">Объект не ранее, но соответствующий пример является «Удаление Microsoft Lync Server и удаление роли сервера,» которого можно загрузить на [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="29049-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

