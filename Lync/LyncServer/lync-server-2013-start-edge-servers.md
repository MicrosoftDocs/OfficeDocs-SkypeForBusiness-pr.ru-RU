---
title: 'Lync Server 2013: запуск пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start Edge Servers
ms:assetid: fe62b18f-2189-4112-ba90-b1c590cf84d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413083(v=OCS.15)
ms:contentKeyID: 48185963
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2488e81c0512e8698337209161558b2789cd2f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-edge-servers-in-lync-server-2013"></a><span data-ttu-id="1d525-102">Запуск пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d525-102">Start Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d525-103">_**Тема последнего изменения:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="1d525-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="1d525-104">После завершения настройки пограничных серверов и подсистем балансировки нагрузки необходимо запустить службы на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="1d525-104">After completing the set up of the Edge Servers and load balancers, you need to start the services on each Edge Server.</span></span>

<div>

## <a name="to-start-the-services"></a><span data-ttu-id="1d525-105">Запуск служб</span><span class="sxs-lookup"><span data-stu-id="1d525-105">To start the services</span></span>

1.  <span data-ttu-id="1d525-106">На каждом пограничном сервере в мастере развертывания рядом с **шагом 4: запуск служб**, нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1d525-106">On each Edge Server, in the Deployment Wizard, next to **Step 4: Start Services**, click **Run**.</span></span>

2.  <span data-ttu-id="1d525-107">На странице **Запуск служб Lync Server 15** просмотрите список служб, а затем нажмите кнопку **Далее** , чтобы запустить эти службы.</span><span class="sxs-lookup"><span data-stu-id="1d525-107">On the **Start Lync Server 15 Services** page, review the list of services, and then click **Next** to start the services.</span></span>

3.  <span data-ttu-id="1d525-108">После запуска служб нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="1d525-108">After the services are started, click **Finish** to close the wizard.</span></span>

4.  <span data-ttu-id="1d525-109">В разделе **действие 4: запустите службы**, выберите **состояние службы (необязательно)**.</span><span class="sxs-lookup"><span data-stu-id="1d525-109">Under **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="1d525-110">Убедитесь, что в консоли управления **службами** (MMC) на сервере запущены все службы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d525-110">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

