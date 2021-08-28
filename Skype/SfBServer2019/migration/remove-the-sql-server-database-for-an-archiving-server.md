---
title: Удаление базы данных SQL Server для сервера архивирования
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
description: После удаления сервера архива можно удалить SQL Server баз данных, в которые были вмещаяся данные пула. Используйте следующие процедуры, чтобы удалить определения из Topology Builder, а затем удалить базы данных и файлы журнала с сервера базы данных.
ms.openlocfilehash: 9305109e38c265b919d9ec22fa626d27efb19225
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621921"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Удаление базы данных SQL Server для сервера архивирования

После удаления сервера архива можно удалить SQL Server баз данных, в которые были вмещаяся данные пула. Используйте следующие процедуры, чтобы удалить определения из Topology Builder, а затем удалить базы данных и файлы журнала с сервера базы данных.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью Topology Builder

1. На Skype для бизнеса Server 2019 front End Server откройте топологию Builder.
    
2. В Topology Builder перейдите к общим компонентам, а затем SQL Server **Stores** (Магазины) щелкните правой кнопкой мыши SQL Server экземпляр, связанный с удаленным или перенастроимным сервером архива, а затем нажмите кнопку **Удалить**. 
    
3. Опубликуйте топологию и проверьте состояние репликации. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1. Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных. 
    
2. Откройте оболочку Skype для бизнеса Server управления.
    
3. Введите в командной строке следующую команду:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где полностью квалифицированное доменное имя (FQDN) сервера базы данных и именуется экземпляром базы данных (то есть, если он  _\<FQDN\>_  _\<instance\>_ определен). 
    
4. Когда комлет **Uninstall-CsDataBase** подсказает вам подтвердить действия, прочитайте сведения, а затем нажмите кнопку Y (или введите), чтобы продолжить, или нажмите кнопку N, а затем введите, если вы хотите остановить его (если есть ошибки). 
    

