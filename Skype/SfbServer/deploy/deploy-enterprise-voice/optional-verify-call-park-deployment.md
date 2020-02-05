---
title: Необязательно Проверка развертывания на предмет остановки звонка в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Проверка развертывания функции парковки звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 7dfaf916e94db18c3b53fc7e9c9e3b136fa445b8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767342"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Необязательно Проверка развертывания на предмет остановки звонка в Skype для бизнеса
 
Проверка развертывания функции парковки звонков в Skype для бизнеса Server Enterprise. 
  
После установки и настройки парковки звонка необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом. At minimum, verify the following:
  
- Позвоните пользователю, для которого установлен флажок "припаркованный Звонок", и приостановить Звонок абонентом.
    
    > [!NOTE]
    > Если вы включили переадресацию звонков в политике голосовой связи только перед выполнением этого теста, пользователь, который применяет звонок, должен выйти из Skype для бизнеса, а затем войти в систему, чтобы он мог видеть параметр парковки в списке приема звонков. 
  
- Для извлечения вызова наберите номер орбиты.
    
- Приостановите другой вызов, дождитесь истечения времени ожидания и не поднимайте трубку при переключении на удерживаемого абонента. Убедитесь в том, что вызов с истекшим временем ожидания перенаправляется в резервное место назначения, заданное параметром **OnTimeoutURI**.
    

