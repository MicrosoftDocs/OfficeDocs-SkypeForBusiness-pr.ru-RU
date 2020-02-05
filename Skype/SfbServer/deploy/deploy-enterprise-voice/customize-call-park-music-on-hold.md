---
title: Настройка музыкального сопровождения для приема звонков на удержание в Skype для бизнеса
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Настройка музыкального сопровождения для остановки звонка на удержании в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 61c82a9ba6c817eb3c61e93ae28d76208855e089
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767742"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Настройка музыкального сопровождения для приема звонков на удержание в Skype для бизнеса
 
Настройка музыкального сопровождения для остановки звонка на удержании в корпоративной голосовой связи Skype для бизнеса Server.
  
Вы можете указать свой музыкальный файл, который будет использоваться для сохранения музыки, вместо музыкального файла по умолчанию, который входит в состав Skype для бизнеса Server. Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Если вы настроите музыку на удержании и хотите использовать одну и ту же музыку для нескольких сайтов, необходимо настроить музыкальный файл для каждого сайта, на котором запущено приложение для парковки звонков. 
  
### <a name="to-customize-the-music-file"></a>Чтобы настроить файл музыки, выполните следующие действия

1. Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Используйте командлет **Get-CsService** для идентификации службы. Подробности можно найти в [статьях Get-кссервице](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной. Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова. Подробности можно найти в разделе [Set-кскаллпарксервицемусиконхолдфиле](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>См. также

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
