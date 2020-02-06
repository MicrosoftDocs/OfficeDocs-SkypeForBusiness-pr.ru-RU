---
title: Удаление старых серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если ваше развертывание содержало сервер архивирования или сервер мониторинга, после перехода на Skype для бизнеса Server 2019 эти серверы можно будет удалить из устаревшей среды, при этом все пользователи удаляются из других устаревших пулов. Сервер архивирования или сервер мониторинга можно удалить в любой последовательности. Ключевое требование состоит в том, что все пользователи удалены из всех оставшихся устаревших пулов.
ms.openlocfilehash: 034d2ad284c0247b19e56e4cd8d751a0cf32ee69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812997"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="4d190-105">Удаление старых серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="4d190-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="4d190-106">Если ваше развертывание содержит сервер архивирования или сервер мониторинга, после перехода на Skype для бизнеса Server 2019 эти серверы могут быть удалены из устаревшей среды при условии, что все пользователи были удалены из всех оставшихся старых пулов.</span><span class="sxs-lookup"><span data-stu-id="4d190-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="4d190-107">Сервер архивирования или сервер мониторинга можно удалить в любой последовательности.</span><span class="sxs-lookup"><span data-stu-id="4d190-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="4d190-108">Ключевое требование состоит в том, что все пользователи удалены из всех оставшихся устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="4d190-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="4d190-109">Вы можете переместить пользователей в Skype для бизнеса Server 2019, выполнив действия, описанные в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="4d190-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="4d190-110">После того как вы подтвердите, что все пользователи удалены из остальных пулов, декоммисион сервер и удалите роли.</span><span class="sxs-lookup"><span data-stu-id="4d190-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="4d190-111">Устаревшая, но уместная — пример удаления Microsoft Lync Server и отмены ролей сервера, которые можно скачать по адресу [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="4d190-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

