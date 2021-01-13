---
title: Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: Сводка. Сведения об управлении сопоставлением клавиш двухтональных многочастотных команд (DTMF) в Skype для бизнеса Server.
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828099"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять сопоставлением клавиш двухтональных многочастотных команд (DTMF) в Skype для бизнеса Server.
  
Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. 
  
To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration,** and **New-CsDialinConferencingDtmfConfiguration** cmdlets.
  
При создании новых параметров DTMF для сайтов параметры сайта имеют приоритет над глобальными. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Управление сопоставлением клавиш для команд DTMF

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Чтобы просмотреть параметры DTMF, используемые для телефонной связи, в командной области запустите следующую команду:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Чтобы изменить параметры DTMF, используемые для конференций с телефонной телефонной телефонией, запустите следующий cmdlet и укажите клавишу, которую необходимо нажать для каждого параметра, который требуется изменить:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Необязательно) Чтобы создать дополнительные наборы команд DTMF для определенных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration** с удостоверением сайта.
    
В следующем примере поменяется клавиша, нажатая для отключения объявлений, и клавиша, нажатая для отключения и отключения звука всех участников. Поскольку параметр Identity не указан, эти изменения применяются к глобальным настройкам DTMF:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Дополнительные сведения см. в настройках [Get-CsDialInConferencingDtmfConfiguration,](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)и [New-CsDialInConferencingDtmfConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)
  

