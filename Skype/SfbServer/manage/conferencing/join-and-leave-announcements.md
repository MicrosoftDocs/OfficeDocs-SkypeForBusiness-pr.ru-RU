---
title: Управление объявлениями о подступах к конференции и отправляемой из нее в Skype для бизнеса Server
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
description: Сводка. Узнайте, как управлять объявлениями о под подступах к конференции и оставьте их в Skype для бизнеса Server.
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828109"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Управление объявлениями о подступах к конференции и отправляемой из нее в Skype для бизнеса Server
 
**Сводка:** Learn how to manage conference join and leave announcements in Skype for Business Server.
  
Когда пользователи с телефонным входом присоединяются к конференции или покидают ее, приложение "Извещание о конференции" может объявлять о входе или выходе из нее, выступая в звуковом сигнале или сообщая свои имена. Вы можете изменить работу объявлений с помощью skype для бизнеса Server Management Shell и с помощью команды **Set-CsDialinConferencing** со следующими параметрами:
  
- EnableNameRecording — определяет, требуется ли анонимным участникам записать свое имя перед входом в конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)
    
- EntryExitAnnouncementsEnabledByDefault — указывает, включено ли по умолчанию объявление. Значение по умолчанию — "$false". Это означает, что по умолчанию, когда участники присоединяются к конференции или покидают ее, нет объявлений. Организатор собрания может переопредить этот параметр при планировании собрания.
    
- EntryExitAnnouncementsType — указывает действие, которое происходит, когда участник присоединяется к конференции или покидает ее, для которой включены объявления. Значение по умолчанию — "UseNames", которое означает, что при включании объявлений имеется следующее сообщение: "Ken Myer has joined the conference".
    
Эти параметры можно настроить на глобальном уровне или на уровне сайта. Параметры, настроенные на уровне сайта, имеют приоритет над настройками, настроенными на глобальном уровне.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Выполните в командной строке следующую команду:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Этот cmdlet извлекает сведения о том, должны ли участники записывать свое имя при присоединении к конференции и как Skype для бизнеса Server реагирует, когда участники присоединяются к конференции или покидают ее.
    
4. Выполните в командной строке следующую команду:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

В следующем примере параметры настраиваются на уровне сайта для Redmond. Объявления будут включены, но участникам не будет предложено ввести свое имя при подмыве конференции. Когда участники входят в конференцию или покидают ее, будет заиметь тон:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Дополнительные сведения, включая синтаксис и полный список параметров, см. в подстроке [Set-CsDialInConferencingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)
  

