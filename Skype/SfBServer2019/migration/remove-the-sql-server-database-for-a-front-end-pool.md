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
ms.localizationpriority: medium
description: После удаления пула переднего конца или перенастройки пула для использования другой базы данных можно удалить SQL Server баз данных, в которые были организованы данные пула. Используйте следующие процедуры, чтобы удалить определения из Topology Builder, а затем удалить базы данных и файлы журнала с сервера базы данных.
ms.openlocfilehash: 2a11057811035b0dc51810d3a6b7eb8220c7df1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580113"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Удаление базы данных SQL Server для пула переднего плана

После удаления пула переднего конца или перенастройки пула для использования другой базы данных можно удалить SQL Server баз данных, в которые были организованы данные пула. Используйте следующие процедуры, чтобы удалить определения из Topology Builder, а затем удалить базы данных и файлы журнала с сервера базы данных.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью Topology Builder

1. С Skype для бизнеса Server 2019 front End Server откройте топологию Builder и скачайте существующую топологию. 
    
2. В Topology Builder  перейдите к общим компонентам, а затем **SQL Server Магазинам** нажмите правой кнопкой мыши SQL Server экземпляра, связанного с удаленным или перенастроимным пулом переднего конца, а затем нажмите кнопку **Удалить**.
    
3. Опубликуйте топологию и проверьте состояние репликации. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Удаление баз данных пользователей и приложений с SQL сервера

1. Чтобы удалить базы данных на сервере SQL, необходимо быть членом группы SQL Server sysadmins для сервера SQL, где удаляются файлы баз данных. 
    
2. Откройте Skype для бизнеса Server управленческой оболочки.
    
3. Чтобы удалить базу данных для хранилища пользователей пула, введите:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где полностью квалифицированное доменное имя (FQDN) сервера базы данных и именуется экземпляром базы данных (то есть, если он  _\<FQDN\>_  _\<instance\>_ определен). 
    
4. Чтобы удалить базу данных для хранилища приложений пула, введите:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где находится FQDN сервера базы данных и именуется экземпляром базы данных  _\<FQDN\>_  _\<instance\>_ (то есть, если он был определен). 
    
5. Когда комлет **Uninstall-CsDataBase** подсказает вам подтвердить действия, прочитайте сведения, а затем нажмите кнопку Y (или введите), чтобы продолжить, или нажмите кнопку N, а затем введите, если вы хотите остановить его (если есть ошибки). 
    

