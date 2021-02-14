---
title: Исправление или обновление тыл сервера или сервера Standard Edition в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: Сводка. Узнайте, как установить обновление или исправление на тыловом сервере в Skype для бизнеса Server.
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826309"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Исправление или обновление тыл сервера или сервера Standard Edition в Skype для бизнеса Server
 
**Сводка:** Узнайте, как установить обновление или исправление на тыловом сервере в Skype для бизнеса Server.
  
В этом разделе объясняется, как установить обновление на тылевом сервере Enterprise Edition или на сервере Standard Edition.
  
Если во время обновления внутренний сервер отключается хотя бы на 30 минут, пользователи могут перейти в режим устойчивости. После завершения обновления и подключения внутреннего сервера к серверам переднего плана в пуле пользователи снова получают полный набор функциональных возможностей. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Обновление тыл сервера или сервера Standard Edition

1. Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.
    
2. Загрузите обновление и извлеките его на локальный жесткий диск.
    
3. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", **"Skype** для бизнеса" и "Skype для бизнеса **Server Management Shell".** 
    
4. Остановите службы Skype для бизнеса Server. В командной строке выполните следующую команду:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Остановите службу Интернета. В командной строке выполните следующую команду:
    
    ```PowerShell
    net stop w3svc
   ```

6. Закроем все окна в оболочке управления Skype для бизнеса Server.
    
7. Установите обновление.
    
8. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", **"Skype** для бизнеса" и "Skype для бизнеса **Server Management Shell".** 
    
9. Снова остановите службы Skype для бизнеса Server, чтобы перехватить сборки -d глобального кэша сборок (GAC). В командной строке выполните следующую команду:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Перезапустите службу Интернета. В командной строке выполните следующую команду:
    
    ```PowerShell
    net start w3svc
    ```

11. Применив изменения, внесенные в SQL Server баз данных, с помощью одного из следующих ок.
    
    - Если это сервер Enterprise Edition и на этом сервере нет совместок баз данных, таких как базы данных архива или мониторинга, введите в командной строке следующую команду:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Если это сервер Enterprise Edition с размещенной базой данных на этом сервере, введите в командной строке следующую команду:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Если это сервер Standard Edition, введите в командной строке следующую команду:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
