---
title: Перемещение каталогов конференций
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
description: Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в устаревшем пуле.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752501"
---
# <a name="move-conference-directories"></a>Перемещение каталогов конференций

Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в устаревшем пуле.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Перемещение каталога конференций в Skype для бизнеса Server 2019

1. Откройте оболочку управления Skype для бизнеса Server.
    
2. Чтобы получить идентификатор каталогов конференций в организации, запустите следующую команду:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    В предыдущей команде возвращаются все каталоги конференций в организации. По этой причине может потребоваться ограничить результаты списанием пула. Например, если списание пула с использованием полного доменного имени (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращаемую информацию каталогами конференций из этого пула:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Эта команда возвращает только каталоги конференций, свойство ServiceID которых содержит pool01.contoso.net.
    
3. Чтобы переместить каталоги конференций, запустите следующую команду для каждого каталога конференции в пуле:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Например, чтобы переместить каталог конференции 3, используйте эту команду, указав пул Skype для бизнеса Server 2019 в качестве TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Чтобы переместить все каталоги конференций в пул, используйте команду, аналогичную следующей:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Скачайте [удаление устаревших](https://go.microsoft.com/fwlink/p/?linkId=246227) ролей Майкрософт и удаление ролей сервера для комплексных пошаговой инструкций по выводу устаревших пулов из эксплуатации.
  
При перемещении каталогов конференций может возникнуть следующая ошибка:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Эта ошибка обычно возникает, когда для выполнения задачи в оболочке управления Skype для бизнеса Server требуется обновленный набор разрешений Active Directory. Чтобы устранить проблему, закроем текущий экземпляр командной оболочки, а затем откройте новый экземпляр оболочки и повторно запустите команду для перемещения каталога конференции.
  

