---
title: Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Сводка: Сведения об управлении сопоставления клавиш для команд тонального (двухтональный) в Скайп для Business Server 2015.'
ms.openlocfilehash: 0dca7143b59b7cf4ded0302f763053e71be3bb2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server-2015"></a>Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server 2015
 
**Сводка:** Сведения об управлении сопоставления клавиш для команд тонального (двухтональный) в Скайп для Business Server 2015.
  
Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. 
  
Чтобы управлять клавиш, используемые для команд DTMF, используйте Скайп оболочки управления Business Server с **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**и ** Новые CsDialinConferencingDtmfConfiguration** командлетов.
  
При создании новых параметров DTMF для сайтов эти параметры сайтов имеют приоритет перед глобальными параметрами. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Управление сопоставлением клавиш для команд DTMF

1. Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Для просмотра параметров DTMF, используемых для конференц-связи с телефонным подключением, выполните следующую команду в окне командной строки:
    
  ```
  Get-CsDialinConferencingDtmfConfiguration
  ```

4. Для изменения параметров DTMF, используемых для конференц-связи с телефонным подключением, выполните следующий командлет и укажите клавишу, назначаемую каждому параметру, который требуется изменить:
    
  ```
  Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
[-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
[-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
[-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
[-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
  ```

5. (Дополнительно). Чтобы создать дополнительные наборы команд DTMF для конкретных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration**, указав идентификатор сайта.
    
В следующем примере функции клавиш включения и отключения объявлений, а также включения и отключения звука всех участников меняются местами. Поскольку идентификатор не указан, эти изменения применяются к глобальным параметрам DTMF.
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Для получения дополнительных сведений см [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)и [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

