---
title: Настройка музыки Парка вызовов на удержание вSkype для бизнеса
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка музыки Парка вызовов на удержание в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 87dea58d9e339293b047373ac6c44a16bed3bdb3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093047"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Настройка музыки Парка вызовов на удержание вSkype для бизнеса
 
Настройка музыки Парка вызовов на удержание в Skype для бизнеса Server Корпоративная голосовая связь.
  
Вы можете указать собственный музыкальный файл, который можно использовать для удержания музыки, а не музыкальный файл по умолчанию, который используется в Skype для бизнеса Server. Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Если вы настраиваете музыку на удержание и хотите, чтобы та же музыка для нескольких сайтов, необходимо настроить музыкальный файл для каждого сайта, который запускает приложение Call Park. 
  
### <a name="to-customize-the-music-file"></a>Чтобы настроить файл музыки, выполните следующие действия

1. Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**
    
2. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
3. Выполните команду: 
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Используйте командлет **Get-CsService** для идентификации службы. Подробные сведения [см. в материале Get-CsService.](/powershell/module/skype/get-csservice?view=skype-ps) 
  
    В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной. Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова. Подробные сведения см. [в материале Set-CsCallParkServiceMusicOnHoldFile.](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>См. также

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)