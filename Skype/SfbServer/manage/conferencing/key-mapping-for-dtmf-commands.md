---
title: Управление сопоставлением ключей для команд DTMF в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: Сводка. Узнайте, как управлять сопоставлением ключей двухтонных многочастотных команд (DTMF) в Skype для бизнеса Server.
ms.openlocfilehash: f4b380bddb9a0bc244887c44c85f02157f75b0e6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837641"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Управление сопоставлением ключей для команд DTMF в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять сопоставлением ключей двухтонных многочастотных команд (DTMF) в Skype для бизнеса Server.
  
Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. 
  
Чтобы управлять ключами, используемыми для команд DTMF, используйте командлеты управления Skype для бизнеса Server с командлетами **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** и **New-CsDialinConferencingDtmfConfiguration.**
  
При создании новых параметров DTMF для сайтов параметры сайта имеют приоритет над глобальными настройками. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Управление сопоставлением ключей команд DTMF

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
3. Чтобы просмотреть параметры DTMF, используемые для телефонных конференций, запустите следующую команду в командной подсказке:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Чтобы изменить параметры DTMF, используемые для телефонных конференций, запустите следующий комдлет и укажите клавишу, которую необходимо нажать для каждого параметра, который необходимо изменить:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Необязательный) Чтобы создать дополнительные наборы команд DTMF для определенных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration** с идентификатором сайта.
    
В следующем примере подменяется клавиша, нажатая, чтобы включить или отключить объявления, а также клавишу, нажатую для отключения и отключения всех участников. Поскольку идентификатор не указан, эти изменения применяются к глобальным настройкам DTMF:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Дополнительные сведения см. в [рублях Get-CsDialInConferencingDtmfConfiguration,](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)и [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
