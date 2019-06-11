---
title: Удаление старых серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f9d3419d9fc46cc4b547c645fa9f938f4a2a23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="9d182-102">Удаление старых серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="9d182-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d182-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9d182-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9d182-104">Если ваше развертывание содержит сервер архивирования или сервер мониторинга, после перехода на Lync Server 2013 эти серверы могут быть удалены из устаревшей среды, при этом все пользователи удаляются из других устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="9d182-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="9d182-105">Сервер архивирования или сервер мониторинга можно удалить в любой последовательности.</span><span class="sxs-lookup"><span data-stu-id="9d182-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="9d182-106">Ключевое требование состоит в том, что все пользователи удалены из всех оставшихся устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="9d182-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="9d182-107">Вы можете переместить пользователей из Lync Server 2010 в Lync Server 2013, выполнив действия, описанные в разделе [Этап 4: перемещение тестовых пользователей в пул пилотных проектов](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="9d182-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="9d182-108">После того как вы подтвердите удаление всех пользователей из оставшихся пулов, выполните процедуру, описанную в разделе "удаление Microsoft Lync Server 2010 и удаление ролей сервера", которые можно скачать по адресу [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227).</span><span class="sxs-lookup"><span data-stu-id="9d182-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

