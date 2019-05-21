---
title: Исправление или обновление сервера обратного или стандартного выпуска Standard в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Сводка: сведения о том, как установить обновление или исправление на сервер с обратной стороны в Skype для бизнеса Server.'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275124"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Исправление или обновление сервера обратного или стандартного выпуска Standard в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как установить обновление или исправление на сервер с веб-интерфейсом в Skype для бизнеса Server.
  
В этой статье объясняется, как установить обновление на обратном сервере Enterprise Edition или стандартном сервере Standard Edition.
  
Если сервер выходит за частоту не менее 30 минут после его обновления, пользователи могут перейти в режим устойчивости. После завершения обновления и повторного подключения серверов к внешним серверам из пула пользователи будут возвращены в полную функциональность. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Обновление внутреннего сервера или сервера Standard Edition

1. Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.
    
2. Загрузите обновление и извлеките его на локальный жесткий диск.
    
3. Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **консоль управления Skype для бизнеса Server**...
    
4. Остановите службы Skype для бизнеса Server. В командной строке выполните следующую команду:
    
    ```
    Stop-CsWindowsService
    ```

5. Остановите службу Интернета. В командной строке выполните следующую команду:
    
    ```
    net stop w3svc
   ```

6. Закройте все окна командной консоли Skype для бизнеса Server.
    
7. Установите обновление.
    
8. Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **Командная консоль управления Skype для бизнеса Server**.
    
9. Остановите службы Skype для бизнеса Server, чтобы перехватить сборки d глобального кэша сборок (GAC). В командной строке выполните следующую команду:
    
    ```
    Stop-CsWindowsService
    ```

10. Перезапустите службу Интернета. В командной строке выполните следующую команду:
    
    ```
    net start w3svc
    ```

11. Примените изменения, внесенные в базы данных SQL Server, выполнив одно из следующих действий.
    
    - Если это сервер выпуска Enterprise Edition и на нем нет размещенных на нем баз данных, таких как архивация и мониторинг баз данных, введите в командной строке следующую команду:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Если этот сервер выпуска Enterprise Edition и на нем есть размещенные на сервере базы данных, введите в командной строке следующее:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Если это сервер Standard Edition, введите в командной строке следующее:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
