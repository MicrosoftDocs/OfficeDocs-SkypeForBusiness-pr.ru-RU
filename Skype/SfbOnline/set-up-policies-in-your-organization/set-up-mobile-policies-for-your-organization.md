---
title: Настройка политик мобильных устройств в организации
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
ms.openlocfilehash: cfd9232943aebc9e4565b0ebfe1b46872c4bad65
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164848"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Настройка политик мобильных устройств в организации

[] Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
  
Параметры политики мобильных устройств можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет **Set-CsMobilityPolicy**.
  
## <a name="set-your-mobile-policies"></a>Задание политик мобильных устройств

> [!NOTE]
> Для всех параметров политики мобильных устройств в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
        
    3. Если у вас нет версии 3,0 или более новой, вам нужно скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Перезагрузите компьютер после появления соответствующего запроса.
        
    4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:
        
        > [!NOTE]
        > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Требование подключения Wi-Fi для видеосвязи с пользователем

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Дополнительные сведения о командлете [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Дополнительные сведения о командлете [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx), чтобы применить настройки к пользователям.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Запрет на использование приложения Skype для бизнеса

- Чтобы создать политику для настроек, запустите следующую команду:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Дополнительные сведения о командлете [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Дополнительные сведения о командлете [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Если вы уже создали политику, вы можете использовать командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) , чтобы применить этот параметр к вашим пользователям.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Запрет звонков по VoIP на мобильных устройствах

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Дополнительные сведения о командлете [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Дополнительные сведения о командлете [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx), чтобы применить настройки к пользователям.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин, по которым вам может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>См. также
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Блокировка передачи файлов между точками](block-point-to-point-file-transfers.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик конференц-связи в Организации](set-up-conferencing-policies-for-your-organization.md)

  
 
