---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: После перехода в Microsoft Skype для бизнеса Server 2019 г. необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 г. для работы с System Center Operations Manager.
ms.openlocfilehash: 756e83ad0a8c964954f43518dc8603802d45c40d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590663"
---
# <a name="configure-scom-monitoring"></a>Настройка мониторинга SCOM

После переноса Skype для бизнеса Server 2019 г. необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 г. для работы с System Center Operations Manager.
  
- Применение обновлений к серверу, избранному для управления центральной логикой обнаружения.
    
- Обновите раздел реестра потенциального сервера централизованного обнаружения.
    
- Настройка основного сервера System Center диспетчера операций для переопределения центрального узла обнаружения кандидата.
    
Инструкции по выполнению каждой задачи приведены ниже.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Применение обновлений к серверу, избранному для управления центральной логикой обнаружения.

1. Выберите сервер, на котором установлены файлы агента System Center Operations Manager и который настроен как потенциальный узел обнаружения. 
    
2. Применение обновлений на этом сервере. См. в разделе [Применение обновлений](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Обновите раздел реестра потенциального сервера централизованного обнаружения.

1. На сервере, избранном для управления центральной логикой обнаружения, откройте окно Windows PowerShell команды. 
    
2. В командной строке введите следующую команду:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > При редактировании реестра может возникнуть ошибка выполнения команды, если раздел реестра уже существует. Эту ошибку можно игнорировать. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Настройте основной сервер System Center диспетчера операций, чтобы переопредить узел центрального узла просмотра обнаружения кандидатов.

1. На компьютере с установленной консолью System Center Operations Manager разверните **Объекты пакета управления** и выберите **Обнаружение объектов**.
    
2. Щелкните **Область изменения**
    
3. на странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.
    
4. Переопределите **Эффективное значение LS Discovery Candidate**, указав имя сервера, выбранного ранее. 
    
Чтобы доумножать изменения, перезапустите службу здравоохранения на сервере корневого управления System Center operations Manager.
  

