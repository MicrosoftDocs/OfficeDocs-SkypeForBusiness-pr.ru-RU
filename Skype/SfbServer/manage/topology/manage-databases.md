---
title: Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server
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
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: Сводка. Узнайте, как добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn и узнать о необходимых дополнительных действиях после исправления или обновления тылого сервера, который входит в группу доступности AlwaysOn в Skype для бизнеса Server.
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826369"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server

Воспользуйтесь действиями в этой статье, чтобы добавить дополнительные базы данных Skype для бизнеса Server в существующую группу доступности AlwaysOn в Skype для бизнеса Server, а также узнать о необходимых дополнительных действиях после исправления или обновления тылого сервера, который входит в группу доступности AlwaysOn в Skype для бизнеса Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Добавление баз данных в группу доступности AlwaysOn 

1. Откройте SQL Server Management Studio и перейдите в группу доступности AlwaysOn. Перенаправь его в первичную реплику.
    
2. В построителе топологий SQL Server FQDN группы доступности AlwaysOn в качестве FQDN основного узла этой группы.
    
   - Откройте построитель топологий, выберите **"Загрузить топологию" из** существующего развертывания и нажмите кнопку **"ОК".**
    
   - Разверите Skype для бизнеса Server, развяйте топологию и SQL Server **хранилищах.** Щелкните правой кнопкой мыши SQL новой группы доступности AlwaysOn и выберите "Изменить **свойства".**
    
   - В нижней части страницы в поле **SQL Server Введите FQDN** основного узла группы доступности AlwaysOn.
    
3. Опубликуйте топологию. В меню **"Действие"** **щелкните "Топология",** а затем **"Опубликовать".** Затем на странице подтверждения нажмите кнопку **"Далее".**
    
4. Используйте SQL Server Management Studio для добавления новой базы данных в группу доступности AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Исправление или обновление SQL Server в группе доступности AlwaysOn

После исправления тыловых серверов, в которые входит группа доступности AlwaysOn, необходимо повторно опубликовать топологию.

1. Установите обновление на сервер или серверы Skype для бизнеса.
    
2. Выполните следующую команду PowerShell в командной оболочке Skype для бизнеса (во время входа с использованием учетной записи, которая имеет соответствующее разрешение на применение изменений к базам данных AlwaysOn SQL) следующим образом:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Где [sqlpool.contoso.com] заменяется на полное доменное имя группы доступности AlwaysOn.
