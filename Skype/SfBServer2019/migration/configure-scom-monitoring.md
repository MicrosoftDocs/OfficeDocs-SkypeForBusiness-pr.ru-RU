---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После миграции на Скайп Microsoft для Business Server 2019, необходимо выполнить несколько задач для настройки Скайп для 2019 Business Server для работы с System Center Operations Manager.
ms.openlocfilehash: 80ef737c57006550111331db7f46fd607f7cf1ed
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887416"
---
# <a name="configure-scom-monitoring"></a>Настройка мониторинга SCOM

После миграции на Скайп для Business Server 2019, необходимо выполнить несколько задач для настройки Скайп для 2019 Business Server для работы с System Center Operations Manager.
  
- Применение обновлений на сервере, выбранном для управления логикой централизованного обнаружения.
    
- Обновите раздел реестра потенциального сервера централизованного обнаружения.
    
- Настройте основной сервер управления System Center Operations Manager для переопределения кандидат центрального обнаружения.
    
Ниже приведены инструкции по выполнению каждой из этих задач.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Применение обновлений на сервере, выбранном для управления логикой централизованного обнаружения.

1. Выберите сервер, который имеет System Center Operations Manager файлы агента установлен и настроен как потенциальный узел обнаружения. 
    
2. Установка обновлений для данного сервера. В разделе [Применить обновления](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Обновите раздел реестра потенциального сервера централизованного обнаружения.

1. На сервере, выбранном для управления логикой централизованного обнаружения откройте окно командной строки Windows PowerShell. 
    
2. В командной строке введите следующую команду:
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > При изменении реестра может возникнуть ошибка, которая не удалось выполнить команду, если раздел реестра уже существует. При возникновении, можно игнорировать ошибки. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Настройте основной сервер управления System Center Operations Manager для переопределения узла-наблюдателя кандидат центрального обнаружения.

1. На компьютере, где была установлена консоль System Center Operations Manager разверните узел **Объекты пакета управления** и выберите **Обнаружение объектов**.
    
2. Нажмите кнопку **Изменить область**
    
3. На странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.
    
4. Переопределите **Эффективное значение LS Discovery Candidate** , имя сервера, выбранного в предыдущей процедуре. 
    
Чтобы завершить внесение изменений, перезапустите службу работоспособности на сервере управления корневой системы центр Operations Manager.
  

