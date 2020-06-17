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

1. Откройте консоль управления Skype для бизнеса Server.
    
2. Чтобы получить удостоверение каталогов конференций в Организации, выполните следующую команду:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Предыдущая команда возвращает все каталоги конференций в Организации. Из-за этого может потребоваться ограничить результаты для пула, который будет списан. Например, при списании пула с полным доменным именем (FQDN) pool01.contoso.net используйте следующую команду, чтобы ограничить возвращаемые данные каталогами конференций из этого пула:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит полное доменное имя pool01.contoso.net.
    
3. Чтобы переместить каталоги конференций, выполните следующую команду для каждого каталога конференции в пуле:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Например, чтобы переместить каталог конференций 3, выполните следующую команду, указав пул Skype для бизнеса Server 2019 в качестве TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Если вы хотите переместить все каталоги конференций в пуле, используйте команду, аналогичную следующей:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Скачайте пакет удаление [устаревших Microsoft и удалите роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227) , чтобы получить исчерпывающие пошаговые инструкции по списанию устаревших пулов.
  
При перемещении каталогов конференций может возникнуть следующая ошибка:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Эта ошибка обычно возникает, если для выполнения задачи в командной консоли Skype для бизнеса Server требуется обновленный набор разрешений Active Directory. Чтобы устранить эту проблему, закройте текущий экземпляр командной консоли, а затем откройте новый экземпляр командной консоли и повторно выполните команду, чтобы переместить каталог конференции.
  

