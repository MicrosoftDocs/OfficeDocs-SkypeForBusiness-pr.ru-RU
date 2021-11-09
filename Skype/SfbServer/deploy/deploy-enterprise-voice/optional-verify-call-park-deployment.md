---
title: (Необязательный) Проверка развертывания Call Park в Skype для бизнеса
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Проверка развертывания call-парка в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 9258a38936ffe22eb209c4b4bd9d1e5692341003
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838341"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Необязательный) Проверка развертывания Call Park в Skype для бизнеса
 
Проверка развертывания call-парка в Skype для бизнеса Server Корпоративная голосовая связь. 
  
После установки и настройки парка вызовов необходимо проверить конфигурацию, чтобы убедиться, что парковка и вызовы для повторного вызова работают как ожидалось. Следует проверить по крайней мере следующее:
  
- Вызов пользователя, включенного в Call Park, и оставить вызов пользователю.
    
    > [!NOTE]
    > Если вы включили call Park в голосовой политике перед выполнением этого теста, пользователю, который выполняет парковку, необходимо выйти из Skype для бизнеса, а затем войти обратно, чтобы увидеть параметр Парк вызовов в списке вызовов передачи. 
  
- Dial the orbit number to retrieve the call.
    
- Запаркуйте другой звонок, дождитесь истечения его времени ожидания и не берите трубку при переключении на удерживаемого абонента. Убедитесь, что звонок с истекшим временем ожидания правильно перенаправляется в резервное назначение, указанное для **OnTimeoutURI**.
    

