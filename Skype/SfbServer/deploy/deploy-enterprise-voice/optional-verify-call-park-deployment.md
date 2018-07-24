---
title: (Необязательно) Проверка развертывания парковки вызовов в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Проверка развертывания парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: b07b3b3bfb709770a4f30f2f6cb43e5ce5dbcc3a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000531"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="e8d53-103">(Необязательно) Проверка развертывания парковки вызовов в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e8d53-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="e8d53-104">Проверка развертывания парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e8d53-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="e8d53-105">После установки и настройки парковки вызовов, необходимо проверить конфигурацию, чтобы убедиться, что парковку и извлечение вызовов работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="e8d53-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="e8d53-106">Как минимум, необходимо проверить следующее:</span><span class="sxs-lookup"><span data-stu-id="e8d53-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="e8d53-107">Звонок пользователя с поддержкой парковки вызовов и у пользователя парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e8d53-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8d53-108">Если вы включили парковки вызовов в политике голосовой связи непосредственно перед выполнением этой проверки, пользователя, который парковку вызовов необходимо выйти из Скайп для бизнеса и затем снова выполните вход, должны иметь возможность параметр парковки вызовов в передачу вызова списка отображается.</span><span class="sxs-lookup"><span data-stu-id="e8d53-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="e8d53-109">Для извлечения вызова наберите номер орбиты.</span><span class="sxs-lookup"><span data-stu-id="e8d53-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="e8d53-p102">Приостановите другой вызов, дождитесь истечения времени ожидания и не поднимайте трубку при переключении на удерживаемого абонента. Убедитесь в том, что вызов с истекшим временем ожидания перенаправляется в резервное место назначения, заданное параметром **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="e8d53-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

