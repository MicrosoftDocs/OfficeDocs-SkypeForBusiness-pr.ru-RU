---
title: Удаление базы данных SQL Server для сервера мониторинга
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
description: После удаления сервера мониторинга можно удалить SQL Server баз данных, в которые были вмещая данные сервера. Используйте следующие процедуры, чтобы удалить определения из Topology Builder, а затем удалить базы данных и файлы журнала с сервера базы данных.
ms.openlocfilehash: 23f58166c6a24680772d50c6bc484ba1bd02d754
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605758"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Удаление базы данных SQL Server для сервера мониторинга

После удаления сервера мониторинга можно удалить SQL Server баз данных, в которые были вмещая данные сервера. Используйте следующие процедуры, чтобы удалить определения из Topology Builder, а затем удалить базы данных и файлы журнала с сервера базы данных.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью Topology Builder

1. На Skype для бизнеса Server 2019 front End Server откройте топологию Builder.
    
2. В topology Builder перейдите к общим компонентам, а затем SQL Server **Stores** (Магазины) щелкните правой кнопкой мыши SQL Server экземпляра, связанного с удаленным или перенастроимным сервером мониторинга, а затем нажмите кнопку **Удалить**. 
    
3. Опубликуйте топологию и проверьте состояние репликации.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1. Для удаления баз данных на сервере SQL Server вы должны быть членом группы администраторов системы SQL Server на этом сервере.
    
2. Откройте оболочку Skype для бизнеса Server управления.
    
3. Введите в командной строке следующую команду:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где  _\<FQDN\>_ полностью квалифицированное доменное имя (FQDN) сервера базы данных и необязательный экземпляр  _\<instance\>_ базы данных. 
    
4. Когда комлет **Uninstall-CsDataBase** подсказает вам подтвердить действия, прочитайте сведения, а затем нажмите кнопку Y (или введите), чтобы продолжить, или нажмите кнопку N, а затем введите, если вы хотите остановить его (если есть ошибки). 
    

