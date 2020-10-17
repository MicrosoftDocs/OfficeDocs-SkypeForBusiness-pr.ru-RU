---
title: 'Lync Server 2013: Проверка развертывания парковки вызовов (необязательно)'
description: 'Lync Server 2013: (необязательно) Проверка развертывания парковки вызовов.'
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
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541935"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="e58de-103">Необязательно Проверка развертывания парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e58de-103">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e58de-104">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e58de-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e58de-105">После установки и настройки парковки вызовов необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="e58de-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="e58de-106">Следует проверить по крайней мере следующее:</span><span class="sxs-lookup"><span data-stu-id="e58de-106">At minimum, verify the following:</span></span>

  - <span data-ttu-id="e58de-107">Вызовите пользователя с включенным Парковким вызовов и приостановить вызов.</span><span class="sxs-lookup"><span data-stu-id="e58de-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e58de-108">Если вы включили приостановку вызовов в политике голосовой связи непосредственно перед выполнением этого теста, пользователь, который подключается к серверу Lync Server, должен выйти из Lync Server, а затем снова войти, чтобы увидеть параметр парковки вызовов в списке передаваемых вызовов.</span><span class="sxs-lookup"><span data-stu-id="e58de-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="e58de-109">Dial the orbit number to retrieve the call.</span><span class="sxs-lookup"><span data-stu-id="e58de-109">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="e58de-p102">Запаркуйте другой звонок, дождитесь истечения его времени ожидания и не берите трубку при переключении на удерживаемого абонента. Убедитесь, что звонок с истекшим временем ожидания правильно перенаправляется в резервное назначение, указанное для **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="e58de-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

