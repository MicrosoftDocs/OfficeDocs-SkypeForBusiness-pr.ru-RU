---
title: Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Сводка: Узнайте, как добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn и ознакомиться с необходимыми дополнительными инструкциями после исправления или обновления сервера, который входит в группу доступности AlwaysOn в Skype для Business Server.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275187"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server

Выполните действия, описанные в этой статье, чтобы добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn в Skype для бизнеса Server, и ознакомьтесь с необходимыми дополнительными инструкциями после исправления или обновления сервера, который входит в состав AlwaysOn. Группа "доступность" в Skype для бизнеса Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Добавление баз данных в группу доступности AlwaysOn 

1. Откройте центр SQL Server Management Studio и перейдите в группу доступности AlwaysOn. Переключиться на основную реплику.
    
2. В построителе топологии Настройте полное доменное имя SQL Server группы доступности AlwaysOn на полное доменное имя основного узла этой группы.
    
   - Откройте конфигуратор топологии, выберите пункт **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.
    
   - Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**. Щелкните правой кнопкой мыши хранилище SQL для новой группы доступности AlwaysOn и выберите команду **изменить свойства**.
    
   - В нижней части страницы в поле **полное доменное имя сервера SQL Server** введите полное доменное имя основного узла группы доступности AlwaysOn.
    
3. Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. Затем на странице подтверждения нажмите кнопку **Далее**.
    
4. С помощью SQL Server Management Studio вы можете добавить новую базу данных в группу доступности AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Установка исправления или обновления SQL Server в составе группы доступности AlwaysOn

После внесения исправлений на сервер, который входит в группу доступности AlwaysOn, необходимо повторно опубликовать топологию.

1. Установите обновления на сервер или серверы Skype для бизнеса.
    
2. Выполните следующую команду PowerShell в командной консоли Skype для бизнеса (необходимо выполнить вход с использованием учетной записи с разрешениями на применение изменений к базам данных SQL AlwaysOn).
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Здесь [sqlpool.contoso.com] заменяется FQDN группы доступности AlwaysOn.
