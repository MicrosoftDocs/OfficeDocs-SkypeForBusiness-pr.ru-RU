---
title: Исправление или обновление серверов переднего плана в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Сводка: Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371719"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a>Исправление или обновление серверов переднего плана в Скайп для Business Server
 
**Сводка:** Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.
  
Исправление серверы в пуле переднего плана, происходит так на одном сервере за раз. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Установка обновления на серверы переднего плана в пуле

1. Введите следующий командлет:
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Если при выполнении этого командлета отображаются сведения об отсутствующих репликах, перед применением исправлений выполните следующий командлет для восстановления пула.
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. На первом сервере, где требуется внести исправления, выполните следующий командлет:
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Этот командлет перемещает все службы в других серверов переднего плана в пуле и переводит этот сервер в автономный режим.
    
3. Примените к серверу обновление или исправление.
    
4. На обновленном сервере выполните следующий командлет:
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Сервер возвращается в режим нормальной работы.
    
5. Повторите шаги 2–4 для каждого сервера, требующего обновления.
    

