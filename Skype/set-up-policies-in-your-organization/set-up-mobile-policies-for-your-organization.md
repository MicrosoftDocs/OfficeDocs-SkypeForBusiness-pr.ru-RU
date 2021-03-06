---
title: "Настройка политик мобильных устройств в организации"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
description: "Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках."
---

# Настройка политик мобильных устройств в организации

Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
  
Параметры политики мобильных устройств можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет **Set-CsMobilityPolicy**.
  
## Задание политик мобильных устройств

> [!NOTE]
> Для всех параметров политики мобильных устройств в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. Чтобы проверить, установлена ли у вас версия 3.0 или более поздняя, в меню **Пуск** выберите пункт **Windows PowerShell**.
    
2. Проверьте версию, введя в окне **Windows PowerShell** команду _Get-Host_.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. В меню **Пуск** выберите пункт **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

    Дополнительные сведения о запуске Windows PowerShell см. в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или[Подключение к Skype для бизнеса с использованием Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
### Требование подключения Wi-Fi для видеосвязи с пользователем

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```

    Дополнительные сведения о командлете [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```

    Дополнительные сведения о командлете [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx), чтобы применить настройки к пользователям.
  
### Запрет на использование приложения Skype для бизнеса

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```

    Дополнительные сведения о командлете [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
    
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```

    Дополнительные сведения о командлете [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx), чтобы применить настройки к пользователям.
  
### Запрет звонков по VoIP на мобильных устройствах

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```

    Дополнительные сведения о командлете [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

    Дополнительные сведения о командлете [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx), чтобы применить настройки к пользователям.
  
## Хотите узнать больше о Windows PowerShell?

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    

