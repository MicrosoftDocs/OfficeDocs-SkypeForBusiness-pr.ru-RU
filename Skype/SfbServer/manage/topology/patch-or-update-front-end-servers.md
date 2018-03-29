---
title: Применение исправления или обновления к серверам переднего плана в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Сводка: Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a>Применение исправления или обновления к серверам переднего плана в Skype для бизнеса Server 2015
 
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
    

