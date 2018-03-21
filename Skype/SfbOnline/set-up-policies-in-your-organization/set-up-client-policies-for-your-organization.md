---
title: "Настройка политик клиента в организации"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям."
ms.openlocfilehash: 82fa2c828af9aed01652870ea5d3db02ca8248c3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-client-policies-for-your-organization"></a>Настройка политик клиента в организации

[] Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
  
Во время создания политики можно настроить параметры политики клиента или командлет **Set-CsClientPolicy** для изменения параметров существующей политики.
  
## <a name="set-your-client-policies"></a>Задание политик клиента

> [!NOTE]
> Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  В разделе Дополнительные с параметрами командлета [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  Просмотрите Дополнительные сведения о командлета [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Если вы уже создали политику, можно использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) для внесения изменений в существующую политику и затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) для применения параметров для пользователей.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях

- Чтобы создать политику для настроек, запустите следующую команду:
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  В разделе Дополнительные с параметрами командлета [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  Просмотрите Дополнительные сведения о командлета [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Если вы уже создали политику, можно использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) для внесения изменений в существующую политику и затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) для применения параметров для пользователей.
  
### <a name="prevent-showing-recent-contacts"></a>Запрет отображения последних контактов

- Чтобы создать политику для настроек, запустите следующую команду:
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  В разделе Дополнительные с параметрами командлета [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  Просмотрите Дополнительные сведения о командлета [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
  Если вы уже создали политику, можно использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) для внесения изменений в существующую политику и затем используйте командлет [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) для применения параметров для пользователей.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Передача файлов точка-точка блока](block-point-to-point-file-transfers.md)

[Настройка политик конференц-связи в вашей организации](set-up-conferencing-policies-for-your-organization.md)
