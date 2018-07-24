---
title: Исправление или обновление SQL Server в группы обеспечения доступности AlwaysOn в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Сводка: Узнайте о необходимости дополнительных действий после обновления вы или обновить Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn в Скайп для Business Server.'
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982988"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a>Исправление или обновление SQL Server в группы обеспечения доступности AlwaysOn в Скайп для Business Server
 
**Сводка:** Узнайте о необходимости дополнительные действия, после исправлений или обновления Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn в Скайп для Business Server.
  
После установки исправлений Тыловой сервер, который является частью группы обеспечения доступности AlwaysOn, необходимо повторно опубликовать эту топологию.
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn

1. Установите обновления на сервер или серверы Skype для бизнеса.
    
2. Выполните следующую команду PowerShell в командной консоли Skype для бизнеса (необходимо выполнить вход с использованием учетной записи с разрешениями на применение изменений к базам данных SQL AlwaysOn).
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Здесь [sqlpool.contoso.com] заменяется FQDN группы доступности AlwaysOn.
    

