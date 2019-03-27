---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед ликвидацией пула необходимо выполнить следующую процедуру для каждого каталога конференции в устаревшем пуле.
ms.openlocfilehash: 32ebe22c54585a206c90888238d96e41fce30a58
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895721"
---
# <a name="move-conference-directories"></a>Перемещение каталогов конференций

Перед ликвидацией пула необходимо выполнить следующую процедуру для каждого каталога конференции в устаревшем пуле.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Перемещение каталога конференции Скайп для Business Server 2019

1. Откройте Скайп для консоли Business Server.
    
2. Чтобы получить идентификатор каталогов конференций в вашей организации, выполните следующую команду:
    
   ```
   Get-CsConferenceDirectory
   ```

    Предыдущая команда возвращает все каталоги конференций в организации. Из-за, можно ограничить результаты в пул списан. Например если ликвидации пула с pool01.contoso.net полное доменное имя (FQDN), чтобы ограничить возвращаемые данные для каталогов конференций из этого пула используйте следующую команду:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит полное доменное имя pool01.contoso.net.
    
3. Для перемещения каталогов конференций, выполните следующую команду для каждого каталога конференции в пуле:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    К примеру перемещение каталога конференции 3, используйте следующую команду, указав в качестве TargetPool Скайп для пула Business Server 2019:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Если вы хотите переместить все каталоги конференций в пуле, используйте команду, аналогичную следующей:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Загрузите [Microsoft Удаление прежних версий и удаление роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227) для подробные пошаговые инструкции по ликвидация старых пулов.
  
После перемещения каталогов конференций, может появиться следующее сообщение об ошибке:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Как правило, эта ошибка возникает при Скайп оболочки управления Business Server требуется обновленный набор разрешений Active Directory для выполнения задачи. Для устранения этой проблемы, закрыть текущий экземпляр консоли, а затем откройте новый экземпляр объекта командной консоли и повторно выполните команду, чтобы переместить каталог конференции.
  

