---
title: Управление присоединиться к конференции и оставить объявления в Skype для бизнеса Server
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: Сводка. Узнайте, как управлять регистрациями на конференции и оставлять объявления в Skype для бизнеса Server.
ms.openlocfilehash: ee624ee347bb52f4bbdf4fbfae42f5303c8b6a54
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837671"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Управление присоединиться к конференции и оставить объявления в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять присоединиться к конференции и оставить объявления в Skype для бизнеса Server.
  
Когда пользователи со звонками присоединяются к конференции или покидают ее, приложение могут объявить о входе или выходе, играя в тон или говоря их имена. Вы можете изменить работу объявлений с помощью Skype для бизнеса Server и команды **Set-CsDialinConferencing** со следующими параметрами:
  
- EnableNameRecording — определяет, просят ли анонимные участники записывать свое имя перед входом на конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)
    
- EntryExitAnnouncementsEnabledByDefault — указывает, включено или отключено объявление по умолчанию. По умолчанию значение "$false", что означает, что по умолчанию нет объявлений, когда участники присоединяются к конференции или покидают ее. Организатор собрания может переопредить этот параметр при планировании собрания.
    
- EntryExitAnnouncementsType — указывает действия, которые принимаются, когда участник присоединяется или покидает конференцию, для которой включены объявления. Значение по умолчанию — "UseNames", что означает объявление, аналогичное следующему: "Кен Мойер присоединился к конференции" при включении объявлений.
    
Эти параметры можно настроить в глобальном масштабе или в области сайта. Параметры, настроенные в области сайта, имеют приоритет над настройками, настроенными в глобальном масштабе.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
3. Выполните в командной строке следующую команду:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Этот список извлекает сведения о том, требуется ли участникам записывать свое имя при присоединении к конференции и как Skype для бизнеса Server, когда участники присоединяются к конференции или покидают ее.
    
4. Выполните в командной строке следующую команду:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

В следующем примере параметры настраиваются в области сайта Redmond. Объявления включены, но участникам не предложено назвать свое имя, когда они присоединяются к конференции. Тон играется, когда участники входят или покидают конференцию:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Дополнительные сведения, включая синтаксис и полный список параметров, см. в [обзоре Set-CsDialInConferencingConfiguration.](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)
