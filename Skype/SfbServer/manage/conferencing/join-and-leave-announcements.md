---
title: Управление регистрациями на конференции и оглашение сообщений в Skype для бизнеса Server
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: Сводка. Узнайте, как управлять регистрациями на конференции и оставлять объявления в Skype для бизнеса Server.
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119458"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Управление регистрациями на конференции и оглашение сообщений в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять регистрациями на конференции и оставлять объявления в Skype для бизнеса Server.
  
Когда пользователи, вступив в диалог, присоединяются к конференции или покидают конференцию, приложение Conferencing Announcement может объявить о своем входе или выходе, играя в тон или говоря их имена. Вы можете изменить работу объявлений с помощью оболочки управления Skype для бизнес-серверов и команды **Set-CsDialinConferencing** со следующими параметрами:
  
- EnableNameRecording — определяет, просят ли анонимные участники записывать свое имя перед входом на конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)
    
- EntryExitAnnouncementsEnabledByDefault — указывает, включено или отключено объявление по умолчанию. По умолчанию значение "$false", что означает, что по умолчанию нет объявлений, когда участники присоединяются к конференции или покидают ее. Организатор собрания может переопредить этот параметр при планировании собрания.
    
- EntryExitAnnouncementsType — указывает действия, которые принимаются, когда участник присоединяется или покидает конференцию, для которой включены объявления. Значение по умолчанию — "UseNames", что означает объявление, аналогичное следующему: "Кен Мойер присоединился к конференции" при включении объявлений.
    
Эти параметры можно настроить в глобальном масштабе или в области сайта. Параметры, настроенные в области сайта, имеют приоритет над настройками, настроенными в глобальной области.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
3. Выполните в командной строке следующую команду:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Этот кодлет извлекает сведения о том, требуется ли участникам записывать свое имя при присоединении к конференции и как Skype для бизнеса Server реагирует, когда участники присоединяются к конференции по вызову или покидают ее.
    
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
