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
description: Если устаревшее развертывание содержало сервер архивации или сервер мониторинга, после перехода на Skype для бизнеса Server 2019 эти серверы можно удалить из устаревшей среды при условии, что все пользователи были удалены из всех оставшихся устаревших пулов. Сервер архивирования и сервер мониторинга можно удалять в любом порядке. Главное требование состоит в удалении всех пользователей из всех оставшихся устаревших пулов.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752171"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="2901f-105">Удаление старых серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="2901f-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="2901f-106">Если устаревшее развертывание содержало сервер архивации или сервер мониторинга, после перехода на Skype для бизнеса Server 2019 эти серверы можно удалить из устаревшей среды при условии, что все пользователи были удалены из всех оставшихся устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="2901f-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="2901f-107">Сервер архивирования и сервер мониторинга можно удалять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="2901f-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="2901f-108">Главное требование состоит в удалении всех пользователей из всех оставшихся устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="2901f-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="2901f-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool.](phase-4-move-test-users-to-the-pilot-pool.md)</span><span class="sxs-lookup"><span data-stu-id="2901f-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="2901f-110">После подтверждения удаления всех пользователей из оставшихся пулов необходимо отсоенить сервер и удалить роли.</span><span class="sxs-lookup"><span data-stu-id="2901f-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="2901f-111">Дата, но релевантный пример: "Удаление Microsoft Lync Server и удаление ролей сервера", которое можно скачать по ссылке [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="2901f-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

