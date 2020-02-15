---
title: 'Lync Server 2013: запуск служб в директоре'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on the Director
ms:assetid: 095b13e1-e788-4b80-93fa-5c5e7498678b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398146(v=OCS.15)
ms:contentKeyID: 48183351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94d4ab3755739742f96cb2b0f4377d4059d63bfd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="e6d12-102">Запуск служб в директоре в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d12-102">Start services on the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6d12-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e6d12-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e6d12-104">После установки локального хранилища конфигурации, установки компонентов Lync Server и настройки сертификатов в директоре необходимо запустить службы Lync Server на сервере.</span><span class="sxs-lookup"><span data-stu-id="e6d12-104">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="e6d12-105">Чтобы запустить службы на каждом Директоре в развертывании, можно воспользоваться следующей процедурой.</span><span class="sxs-lookup"><span data-stu-id="e6d12-105">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="e6d12-106">Запуск служб на Директоре</span><span class="sxs-lookup"><span data-stu-id="e6d12-106">To start services on a Director</span></span>

1.  <span data-ttu-id="e6d12-107">В мастере развертывания Lync Server на странице **Lync server 2013** нажмите кнопку **выполнить** рядом с **шагом 4: Start Services**.</span><span class="sxs-lookup"><span data-stu-id="e6d12-107">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="e6d12-108">На странице **Запуск служб** нажмите кнопку **Далее** , чтобы запустить службы Lync Server на сервере.</span><span class="sxs-lookup"><span data-stu-id="e6d12-108">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="e6d12-109">После успешного запуска всех служб на странице **Выполнение команд** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e6d12-109">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="e6d12-110">Под пунктом **Шаг 4. Запуск служб** щелкните **Состояние служб (дополнительно)**.</span><span class="sxs-lookup"><span data-stu-id="e6d12-110">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="e6d12-111">В консоли **управления Microsoft (** MMC) на сервере убедитесь, что все службы Lync Server 2013 работают.</span><span class="sxs-lookup"><span data-stu-id="e6d12-111">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

