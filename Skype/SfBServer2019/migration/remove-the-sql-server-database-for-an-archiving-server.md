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
localization_priority: Normal
description: После удаления сервера архива можно удалить SQL Server базы данных, в которой были данные пула. Для удаления определений из построитель топологий и удаления файлов базы данных и журналов с сервера баз данных используйте следующие процедуры.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753311"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Удаление базы данных SQL Server для сервера архивирования

После удаления сервера архива можно удалить SQL Server баз данных, в которые были велись данные пула. Для удаления определений из построитель топологий и удаления файлов базы данных и журналов с сервера баз данных используйте следующие процедуры.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построщика топологий

1. On the Skype for Business Server 2019 Front End Server, open Topology Builder.
    
2. В построите топологию перейдите к общим компонентам, а затем SQL Server **Хранилища,** щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером архива, а затем нажмите кнопку **"Удалить".** 
    
3. Опубликуйте топологию и проверьте состояние репликации. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1. Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных. 
    
2. Откройте оболочку управления Skype для бизнеса Server.
    
3. Введите в командной строке следующую команду:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где находится полное доменное имя сервера базы данных и именовалось экземпляром базы данных (то есть, если он  _\<FQDN\>_  _\<instance\>_ был определен). 
    
4. Когда  вам будет предложено подтвердить действия, ознакомьтесь с информацией, нажмите Y (или ВВОД), чтобы продолжить, или нажмите кнопку "Н", а затем введите, если необходимо остановить его (если имеются ошибки). 
    

