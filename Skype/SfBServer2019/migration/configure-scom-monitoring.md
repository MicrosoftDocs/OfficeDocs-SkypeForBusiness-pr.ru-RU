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
localization_priority: Normal
description: После перехода на Microsoft Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754049"
---
# <a name="configure-scom-monitoring"></a>Настройка мониторинга SCOM

После перехода на Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
  
- Применение обновлений к серверу, который выбран для управления логикой центрального обнаружения.
    
- Обновите раздел реестра потенциального сервера централизованного обнаружения.
    
- Настройте основной сервер управления System Center Operations Manager для переопределения кандидата центрального узла обнаружения.
    
Инструкции по выполнению каждой задачи приведены ниже.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Применение обновлений к серверу, который выбран для управления логикой центрального обнаружения.

1. Выберите сервер, на котором установлены файлы агента System Center Operations Manager и который настроен как потенциальный узел обнаружения. 
    
2. Применение обновлений к этому серверу. См. раздел ["Применение обновлений".](apply-updates.md)
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Обновите раздел реестра потенциального сервера централизованного обнаружения.

1. На сервере, который выбран для управления логикой центрального обнаружения, откройте Windows PowerShell командной окне. 
    
2. В командной строке введите следующую команду:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > При редактировании реестра может возникнуть ошибка выполнения команды, если раздел реестра уже существует. Эту ошибку можно игнорировать. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Настройте основной сервер управления System Center Operations Manager для переопределения узла-кандидата центрального узла-контрольщика обнаружения.

1. На компьютере с установленной консолью System Center Operations Manager разверните **Объекты пакета управления** и выберите **Обнаружение объектов**.
    
2. Щелкните **"Изменить область"**
    
3. на странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.
    
4. Переопределите **Эффективное значение LS Discovery Candidate**, указав имя сервера, выбранного ранее. 
    
Чтобы донести изменения, перезапустите службу здравоохранения на корневом сервере управления System Center Operations Manager.
  

