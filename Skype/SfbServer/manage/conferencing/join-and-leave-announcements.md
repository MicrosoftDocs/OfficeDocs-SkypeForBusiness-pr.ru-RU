---
title: Управление оповещениями о присоединении к конференции и выходе из нее в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Сводка: Узнайте, как управлять присоединиться к конференции и передачи объявлений в Скайп для Business Server 2015.'
ms.openlocfilehash: 33e01efebc7d188fe329c1c39718aaf661af1e44
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server-2015"></a>Управление оповещениями о присоединении к конференции и выходе из нее в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как управлять присоединиться к конференции и оставлять объявлений в Скайп для Business Server 2015.
  
При удаленных пользователей присоединиться к или покинуть конференцию, объявлений конференц-связи приложения можно объявить их входные или выйти из, воспроизведения звуковой сигнал или о том, их имена. Можно изменить порядок работы оповещений с помощью Скайп для консоли Business Server и командлет **Set-CsDialinConferencing** со следующими параметрами:
  
- EnableNameRecording. Определяет, должны ли анонимные участники записать свое имя перед входом в конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)
    
- EntryExitAnnouncementsEnabledByDefault. Указывает, включены или отключены ли объявления по умолчанию. По умолчанию используется значение "$false". Это означает, что по умолчанию при присоединении или выходе участников никаких объявлений нет. Организатор собрания может переопределить этот параметр при планировании.
    
- EntryExitAnnouncementsType. Указывает действие, выполняемое всякий раз, когда один из участников подключается к конференции, для которой включены объявления, или выходит из нее. Значение по умолчанию — "UseNames", что означает, что воспроизводится объявление, аналогичное следующему: "Кен Майер присоединился к конференции", если объявления включены.
    
Эти параметры можно настроить в глобальной области или в области узла. Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1. Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду в командной строке:
    
  ```
  Get-CsDialinConferencingConfiguration
  ```

Этот командлет получает сведения о, должны ли участники записать их имя при подключении к конференции, а также Скайп для Business Server реакция при участников присоединиться к или выход из нее конференц-связи.
    
4. Выполните следующую команду в командной строке:
    
  ```
  Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
[-EnableNameRecording <$true | $false>]
[-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
[-EntryExitAnnouncementsType <UseNames | ToneOnly]
  ```

В примере ниже параметры настраиваются в области сайта Redmond. Объявления включены, но у участников не запрашивается имя при подключении к конференции. Когда участники присоединяются к конференции или выходят из нее, воспроизводится звуковой сигнал.
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Дополнительные сведения, включая синтаксиса и полный список параметров [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)см.
  

