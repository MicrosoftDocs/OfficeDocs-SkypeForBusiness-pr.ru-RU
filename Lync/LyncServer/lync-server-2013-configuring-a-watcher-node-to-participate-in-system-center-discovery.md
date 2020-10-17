---
title: Настройка узла-наблюдателя для участия в обнаружении System Center
description: Настройка узла-наблюдателя для участия в обнаружении System Center.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a42ae77e0c8bde8b8e4de4461180ad00380a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564365"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="4d061-103">Настройка узла-наблюдателя в Lync Server 2013 для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="4d061-103">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d061-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4d061-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4d061-105">Чтобы убедиться, что узел-наблюдатель участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на компьютере с установленной консолью System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="4d061-105">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="4d061-106">На вкладке **Администрирование** выберите **Управляемые агентом**.</span><span class="sxs-lookup"><span data-stu-id="4d061-106">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="4d061-p101">Щелкните правой кнопкой компьютер узла-наблюдателя и выберите пункт **Свойства**. В диалоговом окне **Свойства** перейдите на вкладку **Безопасность**, установите флажок **Разрешить агенту работать как прокси и обнаруживать управляемые объекты на других компьютерах** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d061-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="4d061-109">После настройки узла-наблюдателя для работы в качестве прокси-сервера необходимо перезагрузить компьютер этого узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="4d061-109">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="4d061-110">После перезагрузки компьютера убедитесь, что события ошибок не записываются в журнал событий Operations Manager на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="4d061-110">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="4d061-111">После запуска компьютера в течение 15 минут или, с помощью консоли Operations Manager убедитесь, что компьютеры Lync Server указаны в категории **Lync** .</span><span class="sxs-lookup"><span data-stu-id="4d061-111">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

