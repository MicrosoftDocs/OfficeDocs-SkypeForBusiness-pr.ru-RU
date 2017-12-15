---
title: "Настройка политик клиента в организации"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
description: "Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям."
---

# Настройка политик клиента в организации

Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
  
Параметры политики клиента можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет Set-CsClientPolicy.
  
## Задание политик клиента

> [!NOTE]
> Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
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
    
### Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

    Дополнительные сведения о командлете [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx).
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

    Дополнительные сведения о командлете [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx).
    
Если политика уже создана, используйте командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx), чтобы применить настройки к пользователям.
  
### Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

    Дополнительные сведения о командлете [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx).
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

    Дополнительные сведения о командлете [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx).
    
Если политика уже создана, используйте командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx), чтобы применить настройки к пользователям.
  
### Запрет отображения последних контактов

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

    Дополнительные сведения о командлете [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx).
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

    Дополнительные сведения о командлете [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx).
    
Если политика уже создана, используйте командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx), чтобы применить настройки к пользователям.
  
## Хотите узнать больше о Windows PowerShell?

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    

