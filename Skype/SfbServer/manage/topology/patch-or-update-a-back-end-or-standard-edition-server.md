---
title: Модернизация или обновление внутреннего сервера или сервера Standard Edition в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Сводка: Узнайте, как для установки обновления или исправления на Тыловой сервер в Скайп для Business Server.'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a>Модернизация или обновление внутреннего сервера или сервера Standard Edition в Skype для бизнеса Server 2015
 
**Сводка:** Сведения об установке обновления или исправления на Тыловой сервер в Скайп для Business Server.
  
В этом разделе объясняется, как установить обновление на сервере Standard Edition или Enterprise Edition Тыловой сервер.
  
Если Тыловой сервер не работает в течение 30 минут при обновлении ее, пользователи могут зарегистрироваться в режиме устойчивости. После завершения обновления и внутренними серверами попытку подключения с сервера переднего плана в пуле, пользователи, возвращаются все функциональные возможности. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Обновление внутреннего сервера или сервера Standard Edition

1. Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.
    
2. Загрузите обновление и извлеките его на локальный жесткий диск.
    
3. Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса 2015**и нажмите кнопку **Скайп для консоли Business Server**.
    
4. Остановите Скайп для служб Business Server. В командной строке выполните следующую команду:
    
    ```
    Stop-CsWindowsService
    ```

5. Остановите службу Интернета. В командной строке выполните следующую команду:
    
    ```
    net stop w3svc
   ```

6. Закройте все Скайп для Business Server Командная консоль windows.
    
7. Установите обновление.
    
8. Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса 2015**и нажмите кнопку **Скайп для консоли Business Server**.
    
9. Остановите Скайп для служб Business Server еще раз, чтобы захватить -d сборки глобального кэша сборок (GAC). В командной строке выполните следующую команду:
    
    ```
    Stop-CsWindowsService
    ```

10. Перезапустите службу Интернета. В командной строке выполните следующую команду:
    
    ```
    net start w3svc
    ```

11. Примените изменения, внесенные в базы данных SQL Server, выполнив одно из следующих действий.
    
    - Если это Enterprise Edition Тыловой сервер и нет выровненных баз данных на этом сервере, такие как архивации или баз данных мониторинга, введите следующую команду в командной строке:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Если это Enterprise Edition Тыловой сервер и есть выровненные базы данных на этом сервере, введите следующую команду в командной строке:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Если это сервер Standard Edition, введите следующую команду в командной строке:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


