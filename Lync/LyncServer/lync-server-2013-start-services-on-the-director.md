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
ms.openlocfilehash: dc8536008f2b9bf4b66b1d4a1f9e9577835adb03
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="ce6f2-102">Запуск служб в директоре в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce6f2-102">Start services on the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce6f2-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ce6f2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ce6f2-104">После установки локального хранилища конфигурации, установки компонентов Lync Server и настройки сертификатов в директоре необходимо запустить службы Lync Server на сервере.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-104">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="ce6f2-105">Чтобы запустить службы на каждом Директоре в развертывании, можно воспользоваться следующей процедурой.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-105">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="ce6f2-106">Запуск служб на Директоре</span><span class="sxs-lookup"><span data-stu-id="ce6f2-106">To start services on a Director</span></span>

1.  <span data-ttu-id="ce6f2-107">В мастере развертывания Lync Server на странице **Lync server 2013** нажмите кнопку **выполнить** рядом с **шагом 4: Start Services**.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-107">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="ce6f2-108">На странице **Запуск служб** нажмите кнопку **Далее** , чтобы запустить службы Lync Server на сервере.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-108">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="ce6f2-109">После успешного запуска всех служб на странице **Выполнение команд** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-109">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="ce6f2-110">Под пунктом **Шаг 4. Запуск служб** щелкните **Состояние служб (дополнительно)**.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-110">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="ce6f2-111">В консоли **управления Microsoft (** MMC) на сервере убедитесь, что все службы Lync Server 2013 работают.</span><span class="sxs-lookup"><span data-stu-id="ce6f2-111">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

