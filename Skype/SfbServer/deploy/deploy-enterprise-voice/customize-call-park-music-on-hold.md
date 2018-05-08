---
title: Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка парковки вызовов, музыки на хранение в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 95e332aad7d96c366cfc73ca1bcf3f289b5f14ab
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a>Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Skype для бизнеса 2015
 
Настройка парковки вызовов, музыки на хранение в Скайп Business Server корпоративной голосовой связи.
  
Можно указать собственный файл музыки для использования при удержании, вместо файлов музыку по умолчанию, которое поставляется с Скайп для Business Server. Чтобы настроить музыку при удержании, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile** .
  
> [!NOTE]
> Если настроить музыку при удержании и должно же музыки для нескольких сайтов, необходимо настроить файл музыки для каждого сайта, на котором выполняется приложение парковки вызовов. 
  
### <a name="to-customize-the-music-file"></a>Чтобы настроить файл музыки, выполните следующие действия

1. Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду:
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Командлет **Get-CsService** для идентификации службы. Дополнительные сведения см [Командлет Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной. Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова. Дополнительные сведения см [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>См. также

#### 

[SET-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Командлет Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

