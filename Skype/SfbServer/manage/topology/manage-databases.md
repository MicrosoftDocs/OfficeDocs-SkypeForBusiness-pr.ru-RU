---
title: Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server
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
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: Сводка. Сведения о добавлении дополнительных Skype для бизнеса Server баз данных в существующую группу доступности AlwaysOn и сведения о необходимых дополнительных действиях после исправления или обновления back end Server, который входит в группу доступности AlwaysOn в Skype для бизнеса Server.
ms.openlocfilehash: c47d5833b7569faa424415b1e5b7315bab4d4aae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756996"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Управление базами данных с помощью группы доступности AlwaysOn в Skype для бизнеса Server

Используйте шаги в этой статье, чтобы добавить больше Skype для бизнеса Server баз данных в существующую группу доступности AlwaysOn в Skype для бизнеса Server году и узнать о необходимых дополнительных действиях после исправления или обновления back end Server, который входит в группу доступности AlwaysOn в Skype для бизнеса Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Добавление баз данных в группу доступности AlwaysOn 

1. Откройте SQL Server Management Studio и перейдите в группу доступности AlwaysOn. Перенаправь его в основную реплику.
    
2. В Topology Builder установите SQL Server FQDN группы доступности AlwaysOn в FQDN основного узла этой группы.
    
   - Откройте топологию Builder, выберите **топологию загрузки** из существующего развертывания и нажмите **кнопку ОК.**
    
   - Расширяйте Skype для бизнеса Server, расширяйте топологию и **расширяйте SQL Server Магазины.** Щелкните правой кнопкой мыши SQL магазина новой группы доступности AlwaysOn и нажмите **кнопку Изменить свойства**.
    
   - В нижней части страницы в поле **SQL Server FQDN** введите в FQDN основной узел группы доступности AlwaysOn.
    
3. Опубликуйте топологию. Из меню **Действия** нажмите **топологию** и опубликуй .  Затем на странице подтверждения нажмите **кнопку Далее**.
    
4. Используйте SQL Server Management Studio, чтобы добавить новую базу данных в группу доступности AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Исправление или обновление SQL Server в группе доступности AlwaysOn

После исправления back end Server, который входит в группу доступности AlwaysOn, необходимо переопубликовать топологию.

1. Установите обновление на Skype для бизнеса или серверах.
    
2. Выполните следующую команду PowerShell в Skype для бизнеса Management Shell (вошел в систему с соответствующей учетной записью, которая имеет соответствующее разрешение на применение изменений к базам данных SQL AlwaysOn) следующим образом:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Где [sqlpool.contoso.com] заменяется полностью квалифицированным доменным именем (FQDN) группы доступности AlwaysOn.
