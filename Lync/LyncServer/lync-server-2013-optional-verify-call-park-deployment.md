---
title: 'Lync Server 2013: (необязательно) Проверка развертывания для остановки вызова'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="1aaba-102">Необязательно Проверка развертывания парковки звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aaba-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aaba-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1aaba-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1aaba-104">После установки и настройки парковки звонка необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="1aaba-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="1aaba-105">At minimum, verify the following:</span><span class="sxs-lookup"><span data-stu-id="1aaba-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="1aaba-106">Позвоните пользователю, для которого установлен флажок "припаркованный Звонок", и приостановить Звонок абонентом.</span><span class="sxs-lookup"><span data-stu-id="1aaba-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1aaba-107">Если вы включили переадресацию звонков в голосовой политике прямо перед выполнением этого теста, пользователь, который применяет приостановку, должен выйти из Lync Server, а затем снова войти, чтобы можно было видеть параметр "дозвониться" в списке "передача звонков".</span><span class="sxs-lookup"><span data-stu-id="1aaba-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="1aaba-108">Для извлечения вызова наберите номер орбиты.</span><span class="sxs-lookup"><span data-stu-id="1aaba-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="1aaba-p102">Приостановите другой вызов, дождитесь истечения времени ожидания и не поднимайте трубку при переключении на удерживаемого абонента. Убедитесь в том, что вызов с истекшим временем ожидания перенаправляется в резервное место назначения, заданное параметром **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="1aaba-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

