---
title: Исправление или обновление серверов back end или выпуск Standard в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: Сводка. Узнайте, как установить обновление или исправление на сервере back end в Skype для бизнеса Server.
ms.openlocfilehash: 6c2a03358f5fc5f1253f65d1ff2bc202871da678
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737785"
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
