---
title: Управление настройками группы ответа на уровне приложения в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Корпоративная голосовая связь.
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830789"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Управление настройками группы ответа на уровне приложения в Skype для бизнеса
 
Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Корпоративная голосовая связь.
  
Параметры уровня приложения для приложения группы ответа включают конфигурацию музыки при удержании по умолчанию, аудиофайл музыки при удержании по умолчанию, льготный период воспроизведения агента и конфигурацию контекста вызова. Для каждого пула вы можете определить только один набор параметров уровня приложения. Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**. Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.
  
Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.
  
### <a name="to-modify-response-group-application-level-settings"></a>Изменение параметров уровня приложения группы ответа

1. Войдите как член группы RTCUniversalServerAdmins или как член одной из предопределеных административных ролей, которые поддерживают группу ответа.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
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

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
