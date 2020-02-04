---
title: Настройка компьютера Lync Server для участия в обнаружении System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="ce004-102">Настройка компьютера Lync Server 2013 для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="ce004-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce004-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ce004-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ce004-104">Чтобы убедиться в том, что новый агент сервера Lync участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить описанные ниже действия для каждого компьютера, на котором установлена консоль System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ce004-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="ce004-105">На вкладке **Администрирование** выберите пункт **управляемая агентом**.</span><span class="sxs-lookup"><span data-stu-id="ce004-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="ce004-106">Right-click the name of the computer, and then click **Properties**.</span><span class="sxs-lookup"><span data-stu-id="ce004-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="ce004-107">В диалоговом окне **Свойства** на вкладке **Безопасность** выберите **Разрешить этому агенту выступать в качестве прокси-сервера и найдите управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce004-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="ce004-108">После завершения действия 2 перезапустите службу агента работоспособности.</span><span class="sxs-lookup"><span data-stu-id="ce004-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="ce004-109">(При перезагрузке служба будет "принудительно" обнаружение нового компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce004-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="ce004-110">Если вы не перезапускает службу, она может занять до 4 часов, прежде чем новый компьютер будет обнаружен с помощью System Center Operations Manager.).</span><span class="sxs-lookup"><span data-stu-id="ce004-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="ce004-111">После перезагрузки службы убедитесь в том, что в журнале событий Operations Manager на этом компьютере не записываются события ошибок.</span><span class="sxs-lookup"><span data-stu-id="ce004-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

