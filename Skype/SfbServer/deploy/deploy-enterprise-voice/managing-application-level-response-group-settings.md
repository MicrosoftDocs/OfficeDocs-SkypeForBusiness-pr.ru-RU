---
title: Управление параметрами группы ответа уровня приложения в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Управление параметрами группы ответа уровня приложения, такие как параметры обратного вызова и музыка при удержании, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 1aa3234860193cac40e6ca8a39323013847606fb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012304"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Управление параметрами группы ответа уровня приложения в Скайп для бизнеса
 
Управление параметрами группы ответа уровня приложения, такие как параметры обратного вызова и музыка при удержании, в Скайп Business Server корпоративной голосовой связи.
  
Конфигурация музыки при удержании по умолчанию, звуковой файл музыки при удержании по умолчанию, длительности периода обратного вызова агента и контекста вызова следующие параметры уровня приложения для приложения группы ответа. Для каждого пула можно задать на уровне приложения только один набор параметров. Чтобы просмотреть параметры на уровне приложения, командлет **Get-CsRgsConfiguration** . Для изменения параметров уровня приложения, используйте командлет **Set-CsRgsConfiguration** .
  
Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.
  
### <a name="to-modify-response-group-application-level-settings"></a>Для изменения параметров уровня приложения группы ответа

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. В командной строке выполните следующую команду:
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Например:
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>См. также

[Командлет Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Командлет Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)