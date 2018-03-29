---
title: Проверка развертывания парковки вызовов в Skype для бизнеса 2015 (необязательно)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Проверка развертывания парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a><span data-ttu-id="f2444-103">Проверка развертывания парковки вызовов в Skype для бизнеса 2015 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="f2444-103">(Optional) Verify Call Park deployment in Skype for Business 2015</span></span>
 
<span data-ttu-id="f2444-104">Проверка развертывания парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f2444-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="f2444-105">После установки и настройки парковки вызовов, необходимо проверить конфигурацию, чтобы убедиться, что парковку и извлечение вызовов работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="f2444-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="f2444-106">Как минимум, необходимо проверить следующее:</span><span class="sxs-lookup"><span data-stu-id="f2444-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="f2444-107">Звонок пользователя с поддержкой парковки вызовов и у пользователя парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f2444-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2444-108">Если вы включили парковки вызовов в политике голосовой связи непосредственно перед выполнением этой проверки, пользователя, который парковку вызовов необходимо выйти из Скайп для бизнеса и затем снова выполните вход, должны иметь возможность параметр парковки вызовов в передачу вызова списка отображается.</span><span class="sxs-lookup"><span data-stu-id="f2444-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="f2444-109">Для извлечения вызова наберите номер орбиты.</span><span class="sxs-lookup"><span data-stu-id="f2444-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="f2444-p102">Приостановите другой вызов, дождитесь истечения времени ожидания и не поднимайте трубку при переключении на удерживаемого абонента. Убедитесь в том, что вызов с истекшим временем ожидания перенаправляется в резервное место назначения, заданное параметром **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="f2444-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

