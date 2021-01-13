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
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Необязательно) Проверка развертывания парковки вызовов в Skype для бизнеса
 
Проверка развертывания парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь. 
  
После установки и настройки парковки вызовов необходимо проверить конфигурацию, чтобы убедиться, что парковка и вызовы работают правильно. Следует проверить по крайней мере следующее:
  
- Позвоните пользователю, для которого включена парковка вызовов, и запаркуем его.
    
    > [!NOTE]
    > Если вы включили парковку вызовов в политике голосовой связи перед выполнением этого теста, пользователю, который припарковал вызов, необходимо выйти из Skype для бизнеса, а затем снова войти, чтобы увидеть параметр парковки вызовов в списке переключений. 
  
- Dial the orbit number to retrieve the call.
    
- Запаркуйте другой звонок, дождитесь истечения его времени ожидания и не берите трубку при переключении на удерживаемого абонента. Убедитесь, что звонок с истекшим временем ожидания правильно перенаправляется в резервное назначение, указанное для **OnTimeoutURI**.
    

