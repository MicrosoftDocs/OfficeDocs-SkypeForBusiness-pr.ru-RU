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
localization_priority: Normal
description: После удаления сервера мониторинга можно удалить базы данных SQL Server, в которой были данные сервера. Для удаления определений из построитель топологий и удаления файлов базы данных и журналов с сервера баз данных используйте следующие процедуры.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753331"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Удаление базы данных SQL Server для сервера мониторинга

После удаления сервера мониторинга можно удалить базы данных SQL Server, в которой были данные сервера. Для удаления определений из построитель топологий и удаления файлов базы данных и журналов с сервера баз данных используйте следующие процедуры.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построщика топологий

1. On the Skype for Business Server 2019 Front End Server, open Topology Builder.
    
2. В построите топологию перейдите к общим компонентам, а затем SQL Server **"Хранилища",** щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, а затем нажмите кнопку **"Удалить".** 
    
3. Опубликуйте топологию и проверьте состояние репликации.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1. Для удаления баз данных на сервере SQL Server вы должны быть членом группы администраторов системы SQL Server на этом сервере.
    
2. Откройте оболочку управления Skype для бизнеса Server.
    
3. Введите в командной строке следующую команду:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где находится полное доменное имя сервера базы данных и является необязательным  _\<FQDN\>_ именовательным  _\<instance\>_ экземпляром базы данных. 
    
4. Когда  вам будет предложено подтвердить действия, ознакомьтесь с информацией, нажмите Y (или ВВОД), чтобы продолжить, или нажмите кнопку N, а затем введите, если вы хотите остановить его (если есть ошибки). 
    

