---
title: Управление присоединением к Конференции и выход из объявлений в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Сводка: сведения о том, как управлять присоединением к Конференции и оставлять объявления в Skype для бизнеса Server.'
ms.openlocfilehash: 5c2bc7175f99ee50e94bee26ef0e6d54a6a8db5a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991834"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Управление присоединением к Конференции и выход из объявлений в Skype для бизнеса Server
 
**Сводка:** Здесь вы узнаете, как управлять присоединением к Конференции и оставлять объявления в Skype для бизнеса Server.
  
При присоединении к Конференции или выходе из нее пользователи могут сообщать о своем входе в приложение и выходить из него с помощью звукового сопровождения или произнесения их имен. Вы можете изменить способ работы объявлений с помощью командной консоли Skype для бизнеса Server и командлета **Set-ксдиалинконференЦинг** со следующими параметрами:
  
- EnableNameRecording. Определяет, должны ли анонимные участники записать свое имя перед входом в конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)
    
- EntryExitAnnouncementsEnabledByDefault. Указывает, включены или отключены ли объявления по умолчанию. По умолчанию используется значение "$false". Это означает, что по умолчанию при присоединении или выходе участников никаких объявлений нет. Организатор собрания может переопределить этот параметр при планировании.
    
- EntryExitAnnouncementsType. Указывает действие, выполняемое всякий раз, когда один из участников подключается к конференции, для которой включены объявления, или выходит из нее. Значение по умолчанию — "UseNames", что означает, что воспроизводится объявление, аналогичное следующему: "Кен Майер присоединился к конференции", если объявления включены.
    
Эти параметры можно настроить в глобальной области или в области узла. Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Изменение объявлений при присоединении к конференции и выходе из нее

1. Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду в командной строке:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Этот командлет извлекает сведения о том, требуется ли участникам записывать свое имя при присоединении к Конференции и о том, как Skype для бизнеса Server отвечает на присоединение или выход из конференции с телефонным подключением.
    
4. Выполните следующую команду в командной строке:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

В примере ниже параметры настраиваются в области сайта Redmond. Объявления включены, но у участников не запрашивается имя при подключении к конференции. Когда участники присоединяются к конференции или выходят из нее, воспроизводится звуковой сигнал.
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Дополнительные сведения, в том числе синтаксис и полный список параметров, приведены в разделе [Set-ксдиалинконференЦингконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

