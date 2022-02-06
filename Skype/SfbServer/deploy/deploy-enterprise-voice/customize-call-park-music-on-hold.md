---
title: Настройка музыки Парка вызовов на удержание вSkype для бизнеса
ms.reviewer: null
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
ms.custom: null
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка музыки Call Park на удержание в Skype для бизнеса Server Корпоративная голосовая связь.
---

# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Настройка музыки Парка вызовов на удержание вSkype для бизнеса
 
Настройка музыки Call Park на удержание в Skype для бизнеса Server Корпоративная голосовая связь.
  
Вы можете указать собственный музыкальный файл для использования для музыки на удержании, а не файл музыки по умолчанию, который Skype для бизнеса Server. Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Если вы настраиваете музыку на удержание и хотите, чтобы та же музыка для нескольких сайтов, необходимо настроить музыкальный файл для каждого сайта, который запускает приложение Call Park. 
  
### <a name="to-customize-the-music-file"></a>Чтобы настроить файл музыки, выполните следующие действия

1. Войдите на компьютер, на котором Skype для бизнеса Server в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**
    
2. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
3. Запуск:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Используйте командлет **Get-CsService** для идентификации службы. Подробные сведения см [. в материале Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps). 
  
    В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной. Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова. Подробные сведения см. [в материале Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>См. также

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)