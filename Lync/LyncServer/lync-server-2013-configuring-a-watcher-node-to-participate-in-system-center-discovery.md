---
title: Настройка узла-наблюдателя для участия в обнаружении System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="1bf46-102">Настройка узла-наблюдателя в Lync Server 2013 для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="1bf46-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bf46-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1bf46-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1bf46-104">Чтобы убедиться в том, что узел-наблюдатель участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить описанные ниже действия на компьютере с установленной консолью System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1bf46-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="1bf46-105">На вкладке **Администрирование** выберите пункт **управляемая агентом**.</span><span class="sxs-lookup"><span data-stu-id="1bf46-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="1bf46-106">Щелкните правой кнопкой мыши имя компьютера узла-наблюдателя и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1bf46-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="1bf46-107">В диалоговом окне **Свойства** на вкладке **Безопасность** выберите **Разрешить этому агенту выступать в качестве прокси-сервера и найдите управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1bf46-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="1bf46-108">После того как вы настраиваете узел наблюдателя для работы в качестве прокси-сервера, перезагрузите компьютер с узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="1bf46-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="1bf46-109">После перезагрузки компьютера убедитесь в том, что в журнал событий Operations Manager на этом компьютере не записываются события об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1bf46-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="1bf46-110">После запуска компьютера в течение 15 минут или с помощью консоли Operations Manager убедитесь, что компьютеры Lync Server указаны в категории **Lync** .</span><span class="sxs-lookup"><span data-stu-id="1bf46-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

