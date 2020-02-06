---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Перед списанием пула необходимо выполнить описанные ниже действия для каждой из каталогов конференций в пуле старого.
ms.openlocfilehash: bdcb816a91f6bc4a4372141595e46ba2369618a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813287"
---
# <a name="move-conference-directories"></a>Перемещение каталогов конференций

Перед списанием пула необходимо выполнить описанные ниже действия для каждой из каталогов конференций в пуле старого.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Перемещение каталога конференций в Skype для бизнеса Server 2019

1. Откройте консоль управления Skype для бизнеса Server.
    
2. Чтобы получить удостоверение каталогов конференции в Организации, выполните следующую команду:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Предыдущая команда возвращает все каталоги конференций в Организации. По этой причине вам может потребоваться ограничить результаты для пула. Например, если вы собираетесь списать пул с полным доменным именем (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращаемые данные каталогам конференций из этого пула.
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Эта команда возвращает только каталоги конференций, в которых свойство Сервицеид имеет полное доменное имя (FQDN) pool01.contoso.net.
    
3. Чтобы переместить каталоги конференций, выполните для каждой из каталогов конференций в пуле следующую команду:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Например, чтобы переместить каталог конференций 3, используйте эту команду, указав в качестве Таржетпул пул 2019 в Skype для бизнеса Server.
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Если вы хотите переместить все каталоги конференций в пуле, выполните команду, подобную следующей:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Скачайте раздел [Удаление старой версии Microsoft и удалите роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227) , чтобы получить исчерпывающие пошаговые инструкции по списанию устаревших пулов.
  
При перемещении каталогов конференций может появиться следующее сообщение об ошибке:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Как правило, эта ошибка возникает, когда для выполнения задачи в командной консоли Skype для бизнеса Server требуется обновленный набор разрешений Active Directory. Чтобы устранить эту проблему, закройте текущий экземпляр интерпретатора команд, а затем откройте новый экземпляр оболочки и повторно выполните команду, чтобы переместить каталог конференций.
  

