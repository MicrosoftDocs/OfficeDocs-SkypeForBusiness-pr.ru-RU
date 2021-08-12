---
title: Исправление или обновление серверов back end или выпуск Standard в Skype для бизнеса Server
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
description: Сводка. Узнайте, как установить обновление или исправление на сервере back end в Skype для бизнеса Server.
ms.openlocfilehash: 6da04dda24400e8dfa00bcaac5d3620cbf6509a5f4bef2d7d988682597b732f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290287"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Исправление или обновление серверов back end или выпуск Standard в Skype для бизнеса Server
 
**Сводка:** Узнайте, как установить обновление или исправление на сервере back end в Skype для бизнеса Server.
  
В этом разделе рассказывается, как установить обновление на сервере выпуск Enterprise или выпуск Standard сервере.
  
Если во время обновления внутренний сервер отключается хотя бы на 30 минут, пользователи могут перейти в режим устойчивости. После завершения обновления и подключения внутреннего сервера к серверам переднего плана в пуле пользователи снова получают полный набор функциональных возможностей. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Обновление заднего или выпуск Standard сервера

1. Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.
    
2. Загрузите обновление и извлеките его на локальный жесткий диск.
    
3. Запустите Skype для бизнеса Server: нажмите кнопку Начните, нажмите кнопку Все **программы,** нажмите кнопку **Skype для бизнеса,** а затем нажмите кнопку Skype для бизнеса Server **shell**..
    
4. Остановка Skype для бизнеса Server служб. В командной строке выполните следующую команду:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Остановите службу Интернета. В командной строке выполните следующую команду:
    
    ```PowerShell
    net stop w3svc
   ```

6. Закрой Skype для бизнеса Server windows management Shell.
    
7. Установите обновление.
    
8. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку **Skype для бизнеса,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
9. Остановите Skype для бизнеса Server служб снова, чтобы поймать сборки кэша Глобальной сборки (GAC). В командной строке выполните следующую команду:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Перезапустите службу Интернета. В командной строке выполните следующую команду:
    
    ```PowerShell
    net start w3svc
    ```

11. Применить изменения, внесенные в SQL Server базы данных, выполив одно из следующих изменений:
    
    - Если это сервер выпуск Enterprise и на этом сервере нет командных баз данных, например баз данных архива или мониторинга, введите следующую строку в командной строке:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Если это сервер выпуск Enterprise и на этом сервере находятся collocated базы данных, введите следующее в командной строке:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Если это сервер выпуск Standard, введите следующую строку в командной строке:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
