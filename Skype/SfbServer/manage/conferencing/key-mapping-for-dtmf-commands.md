---
title: Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Сводка: сведения о том, как управлять сопоставлением клавиш с однодневными командами многочастотной связи (DTMF) в Skype для бизнеса Server.'
ms.openlocfilehash: 713c72941a8cc147b751c82b9dbbfbc2c2d16837
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283762"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как управлять сопоставлением клавиш с однодневными командами многочастотной связи (DTMF) в Skype для бизнеса Server.
  
Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. 
  
Для управления ключами, используемыми для команд DTMF, используйте командную консоль управления Skype для бизнеса Server с параметрами **Get-ксдиалинконференЦингдтмфконфигуратион**, **Set-ксдиалинконференЦингдтмфконфигуратион**и ** Командлеты New-КсдиалинконференЦингдтмфконфигуратион** .
  
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

Дополнительные сведения можно найти в [статьях Get-ксдиалинконференЦингдтмфконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-ксдиалинконференЦингдтмфконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)и [New-ксдиалинконференЦингдтмфконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

