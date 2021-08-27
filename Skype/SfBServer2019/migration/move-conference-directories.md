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
ms.localizationpriority: medium
description: Перед выводом пула из эксплуатации необходимо выполнить следующую процедуру для каждого каталога конференций в устаревшем пуле.
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596153"
---
# <a name="move-conference-directories"></a>Перемещение каталогов конференций

Перед выводом пула из эксплуатации необходимо выполнить следующую процедуру для каждого каталога конференций в устаревшем пуле.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Перемещение каталога конференций в Skype для бизнеса Server 2019 г.

1. Откройте оболочку Skype для бизнеса Server управления.
    
2. Чтобы получить удостоверения каталогов конференций в организации, запустите следующую команду:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    В предыдущей команде возвращаются все каталоги конференций в организации. Из-за этого может потребоваться ограничить результаты выводом из эксплуатации пула. Например, если вы выводит пул с полностью квалифицированным доменным именем (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращенные данные каталогами конференций из этого пула:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит FQDN pool01.contoso.net.
    
3. Чтобы переместить каталоги конференций, запустите следующую команду для каждого каталога конференции в пуле:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Например, чтобы переместить каталог конференций 3, используйте эту команду, указав пул 2019 Skype для бизнеса Server 2019 как TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Если вы хотите переместить все каталоги конференций в пул, используйте команду, аналогичную следующей:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Скачайте удаление устаревших [ролей Microsoft](https://go.microsoft.com/fwlink/p/?linkId=246227) и удаление ролей сервера для комплексных пошаговой инструкции по выводу из эксплуатации устаревших пулов.
  
При перемещении каталогов конференций может возникнуть следующая ошибка:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Эта ошибка обычно возникает, когда Skype для бизнеса Server для выполнения задачи требуется обновленный набор разрешений Active Directory. Чтобы устранить проблему, закрой текущий экземпляр командной оболочки, затем откройте новый экземпляр оболочки и повторно запустите команду для перемещения каталога конференций.
  

