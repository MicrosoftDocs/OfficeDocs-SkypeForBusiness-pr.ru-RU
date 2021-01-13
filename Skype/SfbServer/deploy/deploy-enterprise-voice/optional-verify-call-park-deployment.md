---
title: (Необязательно) Проверка развертывания парковки вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Проверка развертывания парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830899"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="bb8af-103">(Необязательно) Проверка развертывания парковки вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bb8af-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="bb8af-104">Проверка развертывания парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="bb8af-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="bb8af-105">После установки и настройки парковки вызовов необходимо проверить конфигурацию, чтобы убедиться, что парковка и вызовы работают правильно.</span><span class="sxs-lookup"><span data-stu-id="bb8af-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="bb8af-106">Следует проверить по крайней мере следующее:</span><span class="sxs-lookup"><span data-stu-id="bb8af-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="bb8af-107">Позвоните пользователю, для которого включена парковка вызовов, и запаркуем его.</span><span class="sxs-lookup"><span data-stu-id="bb8af-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb8af-108">Если вы включили парковку вызовов в политике голосовой связи перед выполнением этого теста, пользователю, который припарковал вызов, необходимо выйти из Skype для бизнеса, а затем снова войти, чтобы увидеть параметр парковки вызовов в списке переключений.</span><span class="sxs-lookup"><span data-stu-id="bb8af-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="bb8af-109">Dial the orbit number to retrieve the call.</span><span class="sxs-lookup"><span data-stu-id="bb8af-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="bb8af-p102">Запаркуйте другой звонок, дождитесь истечения его времени ожидания и не берите трубку при переключении на удерживаемого абонента. Убедитесь, что звонок с истекшим временем ожидания правильно перенаправляется в резервное назначение, указанное для **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="bb8af-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

