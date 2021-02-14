---
title: Удаление базы данных SQL Server для пула переднего плана
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После удаления пула переднего уровня или перенастройки пула для использования другой базы данных можно удалить SQL Server баз данных, в которые были велись данные пула. Чтобы удалить определения из построитель топологий, а затем удалить базы данных и файлы журналов с сервера баз данных, используйте следующие процедуры.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753411"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Удаление базы данных SQL Server для пула переднего плана

После удаления пула переднего уровня или перенастройки пула для использования другой базы данных можно удалить SQL Server баз данных, в которые были велись данные пула. Чтобы удалить определения из построитель топологий, а затем удалить базы данных и файлы журналов с сервера баз данных, используйте следующие процедуры.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построщика топологий

1. From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology. 
    
2. В построите топологию перейдите к общим компонентам и SQL Server **Хранилища,** щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным пулом переднего SQL Server, а затем нажмите кнопку  "Удалить". 
    
3. Опубликуйте топологию и проверьте состояние репликации. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Удаление баз данных пользователей и приложений с SQL сервера

1. Чтобы удалить базы данных на сервере SQL, необходимо быть членом группы SQL Server sysadmins для сервера SQL, на котором удаляются файлы базы данных. 
    
2. Откройте Skype для бизнеса Server Management Shell.
    
3. Чтобы удалить базу данных для хранилища пользователей пула, введите:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где находится полное доменное имя сервера базы данных и именуется экземпляр базы данных  _\<FQDN\>_  _\<instance\>_ (то есть, если он был определен). 
    
4. Чтобы удалить базу данных для хранилища приложений пула, введите:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где находится имя FQDN сервера базы данных и именоваемого экземпляра базы данных  _\<FQDN\>_  _\<instance\>_ (то есть, если он был определен). 
    
5. Когда  вам будет предложено подтвердить действия, ознакомьтесь с информацией, нажмите Y (или ВВОД), чтобы продолжить, или нажмите кнопку N, а затем введите, если вы хотите остановить его (если есть ошибки). 
    

