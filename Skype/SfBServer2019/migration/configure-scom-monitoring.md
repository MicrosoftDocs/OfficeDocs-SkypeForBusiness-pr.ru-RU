---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После перехода на Microsoft Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284503"
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
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
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
  

