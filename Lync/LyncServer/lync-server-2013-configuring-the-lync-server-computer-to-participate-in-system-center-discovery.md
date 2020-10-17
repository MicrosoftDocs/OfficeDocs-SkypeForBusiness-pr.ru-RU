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
ms.openlocfilehash: 9783b8054c74b071c927cc42f32d05700877daad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532376"
---
# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="613b2-102">Настройка компьютера Lync Server 2013 для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="613b2-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="613b2-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="613b2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="613b2-104">Чтобы убедиться, что новый агент Lync Server участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на каждом компьютере, на котором установлена консоль System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="613b2-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="613b2-105">На вкладке **Администрирование** щелкните элемент **Управляемый агентом**.</span><span class="sxs-lookup"><span data-stu-id="613b2-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="613b2-p101">Щелкните правой кнопкой мыши имя компьютера и выберите пункт **Свойства**. В диалоговом окне **Свойства** на вкладке **Безопасность** выберите **Разрешить агенту работать как прокси и обнаруживать управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="613b2-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="613b2-p102">После выполнения действия 2 перезапустите службу агента работоспособности. (При перезапуске службы будет автоматически выполнено обнаружение нового компьютера. Если не перезапустить службу, обнаружение нового компьютера агентом System Center Operations Manager может занять до 4 часов.) После перезапуска службы проверьте журнал событий Operations Manager и убедитесь, что в нем не были записаны ошибки для данного компьютера.</span><span class="sxs-lookup"><span data-stu-id="613b2-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

