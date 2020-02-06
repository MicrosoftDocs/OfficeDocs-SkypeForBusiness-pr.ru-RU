---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После перехода на Microsoft Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
ms.openlocfilehash: 79398336bf372fd2ca779d2ec2ff58dc5219da61
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813807"
---
# <a name="configure-scom-monitoring"></a>Настройка мониторинга SCOM

После перехода на Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
  
- Примените обновления к серверу, выбранному для управления логикой центрального обнаружения.
    
- Обновите раздел реестра для основного сервера поиска кандидатов.
    
- Настройка основного сервера System Center Operations Manager для переопределения узла центра обнаружения кандидатов.
    
Ниже приведены инструкции по переносу каждой из этих задач.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Примените обновления к серверу, выбранному для управления логикой центрального обнаружения.

1. Выровняйте сервер, на котором установлены файлы агента System Center Operations Manager и настроен как узел обнаружения кандидатов. 
    
2. Примените обновления к этому серверу. Ознакомьтесь с разделом [применение обновлений](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Обновите раздел реестра для основного сервера поиска кандидатов.

1. На сервере, выбранном для управления логикой центрального обнаружения, Откройте командное окно Windows PowerShell. 
    
2. В командной строке введите следующую команду:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > При внесении изменений в реестр может возникнуть сообщение о том, что команда завершилась сбоем, если раздел реестра уже существует. Если вы столкнетесь с этим, вы можете спокойно проигнорировать ошибку. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Настройка основного сервера System Center Operations Manager для переопределения узла наблюдения за центральным обнаружением.

1. На компьютере с установленной консолью System Center Operations Manager разверните **объект пакета управления** , а затем выберите пункт **Обнаружение объектов**.
    
2. Выберите команду **изменить область**
    
3. На странице " **объекты пакета управления областью** " выберите **кандидат на обнаружение Ls**.
    
4. Переопределение **действующего значения-кандидата на обнаружение Ls** на имя сервера-кандидата, выбранное в предыдущей процедуре. 
    
Чтобы завершить изменения, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.
  

