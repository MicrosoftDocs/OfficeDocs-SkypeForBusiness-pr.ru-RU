---
title: Управление настройками группы реагирования на уровне приложений в Skype для бизнеса
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Управление настройками группы реагирования на уровне приложений, такими как параметры "музыка на удержание" и "звон" в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 05ff86de40efe4d75b9d7fcb54b50615ae7245a8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394311"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Управление настройками группы реагирования на уровне приложений в Skype для бизнеса
 
Управление настройками группы реагирования на уровне приложений, такими как параметры "музыка на удержание" и "звон" в Skype для бизнеса Server Корпоративная голосовая связь.
  
Параметры уровня приложений для приложения Response Group включают конфигурацию музыки на удержание по умолчанию, аудиофайл с музыкой на удержании по умолчанию, период благодати агента и конфигурацию контекста вызовов. Для каждого пула вы можете определить только один набор параметров уровня приложения. Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**. Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.
  
Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.
  
### <a name="to-modify-response-group-application-level-settings"></a>Изменение параметров уровня приложений группы реагирования

1. Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
3. В командной строке выполните следующую команду:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Пример:
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>См. также

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)