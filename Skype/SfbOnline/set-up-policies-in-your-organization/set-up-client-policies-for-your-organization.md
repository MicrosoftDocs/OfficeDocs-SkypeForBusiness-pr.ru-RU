---
title: Настройка политик клиента в организации
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814358"
---
# <a name="set-up-client-policies-for-your-organization"></a>Настройка политик клиента в организации

[] Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
  
Параметры политики клиента можно настроить во время ее создания или с помощью cmdlet **Set-CsClientPolicy** изменить параметры существующей политики.
  
## <a name="set-your-client-policies"></a>Задание политик клиента

> [!NOTE]
> Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
        
    3. Если у вас нет версии 3.0 или более высокой, необходимо скачать и установить обновления для Windows PowerShell. Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0. Перезагрузите компьютер, когда вам будет предложено.
        
    4. Вам также потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online. 
    
    Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.
    
- **Запуск сеанса Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:
    
    > [!NOTE]
    > Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.
    >
    > Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений

- Чтобы создать политику для настроек, запустите следующую команду:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  См. дополнительные [функции для new-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Дополнительные узнать о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](https://technet.microsoft.com/library/mt779153.aspx) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях

- Чтобы создать политику для настроек, запустите следующую команду:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  См. дополнительные [функции для new-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Дополнительные узнать о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](https://technet.microsoft.com/library/mt779153.aspx) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
  
### <a name="prevent-showing-recent-contacts"></a>Запрет отображения последних контактов

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  См. дополнительные [функции для new-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Дополнительные узнать о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
  Если вы уже создали политику, то можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](https://technet.microsoft.com/library/mt779153.aspx) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Блокировать передачу файлов по точкам](block-point-to-point-file-transfers.md)

[Настройка политик для организации](set-up-conferencing-policies-for-your-organization.md)

  
 
