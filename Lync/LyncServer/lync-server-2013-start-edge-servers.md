---
title: 'Lync Server 2013: начало пограничных серверов'
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
ms.openlocfilehash: 948529b62e9752010b9b4ad808f681dd1797f2d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-edge-servers-in-lync-server-2013"></a><span data-ttu-id="d581c-102">Запуск пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d581c-102">Start Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d581c-103">_**Последнее изменение темы:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="d581c-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="d581c-104">После завершения настройки пограничных серверов и подсистем балансировки нагрузки потребуется запустить службы на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="d581c-104">After completing the set up of the Edge Servers and load balancers, you need to start the services on each Edge Server.</span></span>

<div>

## <a name="to-start-the-services"></a><span data-ttu-id="d581c-105">Запуск служб</span><span class="sxs-lookup"><span data-stu-id="d581c-105">To start the services</span></span>

1.  <span data-ttu-id="d581c-106">На каждом пограничном сервере в мастере развертывания в разделе **Step 4: Start Services** (Шаг 4. Запуск служб) нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d581c-106">On each Edge Server, in the Deployment Wizard, next to **Step 4: Start Services**, click **Run**.</span></span>

2.  <span data-ttu-id="d581c-107">На странице **Start Lync Server 15 Services** (Запуск служб Lync Server 15) просмотрите список служб, а затем нажмите кнопку **Далее**, чтобы запустить службы.</span><span class="sxs-lookup"><span data-stu-id="d581c-107">On the **Start Lync Server 15 Services** page, review the list of services, and then click **Next** to start the services.</span></span>

3.  <span data-ttu-id="d581c-108">После того как службы будут запущены, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="d581c-108">After the services are started, click **Finish** to close the wizard.</span></span>

4.  <span data-ttu-id="d581c-109">В разделе **Шаг 4. Запуск служб** щелкните шаг **Services Status (Optional)** (Состояние службы (дополнительно)).</span><span class="sxs-lookup"><span data-stu-id="d581c-109">Under **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="d581c-110">В консоли **управления Microsoft (** MMC) на сервере убедитесь, что все службы Lync Server 2013 работают.</span><span class="sxs-lookup"><span data-stu-id="d581c-110">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

