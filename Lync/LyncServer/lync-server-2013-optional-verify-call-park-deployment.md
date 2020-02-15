---
title: 'Lync Server 2013: Проверка развертывания парковки вызовов (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b18de4af492fb45ef37e64cca45cc2d3d2b965
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="e2d17-102">Необязательно Проверка развертывания парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2d17-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2d17-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e2d17-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e2d17-104">После установки и настройки парковки вызовов необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="e2d17-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="e2d17-105">Следует проверить по крайней мере следующее:</span><span class="sxs-lookup"><span data-stu-id="e2d17-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="e2d17-106">Вызовите пользователя с включенным Парковким вызовов и приостановить вызов.</span><span class="sxs-lookup"><span data-stu-id="e2d17-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2d17-107">Если вы включили приостановку вызовов в политике голосовой связи непосредственно перед выполнением этого теста, пользователь, который подключается к серверу Lync Server, должен выйти из Lync Server, а затем снова войти, чтобы увидеть параметр парковки вызовов в списке передаваемых вызовов.</span><span class="sxs-lookup"><span data-stu-id="e2d17-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="e2d17-108">Dial the orbit number to retrieve the call.</span><span class="sxs-lookup"><span data-stu-id="e2d17-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="e2d17-p102">Запаркуйте другой звонок, дождитесь истечения его времени ожидания и не берите трубку при переключении на удерживаемого абонента. Убедитесь, что звонок с истекшим временем ожидания правильно перенаправляется в резервное назначение, указанное для **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="e2d17-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

