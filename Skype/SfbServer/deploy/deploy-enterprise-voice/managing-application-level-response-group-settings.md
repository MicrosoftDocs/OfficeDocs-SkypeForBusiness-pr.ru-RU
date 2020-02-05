---
title: Управление параметрами группы ответа уровня приложения в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Управление параметрами группы ответа уровня приложения, такими как музыка на удержании и параметры рингбакк, в Skype для бизнеса Server Enterprise Voice.
ms.openlocfilehash: 99a3d6bc82cffd39608d2da0be013d4fbb8389e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767112"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Управление параметрами группы ответа уровня приложения в Skype для бизнеса
 
Управление параметрами группы ответа уровня приложения, такими как музыка на удержании и параметры рингбакк, в Skype для бизнеса Server Enterprise Voice.
  
Параметры уровня приложения для приложения "группа ответа" включают стандартную конфигурацию хранения музыкальных файлов, используемую по умолчанию, а также звуковой файл на хранение по умолчанию, период отсрочки агента рингбакк и контекстную конфигурацию вызова. Для каждого пула можно задать на уровне приложения только один набор параметров. Для просмотра параметров, заданных на уровне приложения, выполните командлет **Get-CsRgsConfiguration**. Для изменения параметров, заданных на уровне приложения, выполните командлет**Set-CsRgsConfiguration**.
  
Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.
  
### <a name="to-modify-response-group-application-level-settings"></a>Изменение параметров уровня приложения для группы ответа

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. В командной строке выполните следующую команду:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Например:
    
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
