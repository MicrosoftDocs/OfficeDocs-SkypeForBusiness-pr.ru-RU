---
title: Необязательно Проверка развертывания на предмет остановки звонка в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Проверка развертывания функции парковки звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292845"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="c75b3-103">Необязательно Проверка развертывания на предмет остановки звонка в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c75b3-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="c75b3-104">Проверка развертывания функции парковки звонков в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c75b3-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c75b3-105">После установки и настройки парковки звонка необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="c75b3-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="c75b3-106">At minimum, verify the following:</span><span class="sxs-lookup"><span data-stu-id="c75b3-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="c75b3-107">Позвоните пользователю, для которого установлен флажок "припаркованный Звонок", и приостановить Звонок абонентом.</span><span class="sxs-lookup"><span data-stu-id="c75b3-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c75b3-108">Если вы включили переадресацию звонков в политике голосовой связи только перед выполнением этого теста, пользователь, который применяет звонок, должен выйти из Skype для бизнеса, а затем войти в систему, чтобы он мог видеть параметр парковки в списке приема звонков.</span><span class="sxs-lookup"><span data-stu-id="c75b3-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="c75b3-109">Для извлечения вызова наберите номер орбиты.</span><span class="sxs-lookup"><span data-stu-id="c75b3-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="c75b3-p102">Приостановите другой вызов, дождитесь истечения времени ожидания и не поднимайте трубку при переключении на удерживаемого абонента. Убедитесь в том, что вызов с истекшим временем ожидания перенаправляется в резервное место назначения, заданное параметром **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="c75b3-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

