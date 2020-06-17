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
description: После удаления сервера архивации можно удалить базы данных SQL Server, на которых размещены данные пула. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753311"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Удаление базы данных SQL Server для сервера архивирования

После удаления сервера архивации можно удалить базы данных SQL Server, на которых размещены данные пула. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построителя топологий

1. На сервере переднего плана Skype для бизнеса Server 2019 откройте построитель топологий.
    
2. В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером архивации, а затем выберите команду **Удалить**.
    
3. Опубликуйте топологию и проверьте состояние репликации. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1. Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных. 
    
2. Откройте консоль управления Skype для бизнеса Server.
    
3. Введите в командной строке следующую команду:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Где _\<FQDN\>_ — полное доменное имя сервера базы данных, а _\<instance\>_ — это именованный экземпляр базы данных (то есть, если он определен). 
    
4. Когда командлет **uninstall-CsDataBase** запрашивает подтверждение действий, прочитайте информацию, а затем нажмите клавишу Y (или ввод), чтобы продолжить, или нажмите клавишу N, а затем ВВОД, чтобы остановить командлет (при наличии ошибок). 
    

