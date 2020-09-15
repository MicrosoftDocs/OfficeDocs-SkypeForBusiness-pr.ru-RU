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
  
Параметры политики клиента можно настроить на момент создания политики, а также можно использовать командлет **Set-CsClientPolicy** , чтобы изменить параметры существующей политики.
  
## <a name="set-your-client-policies"></a>Задание политик клиента

> [!NOTE]
> Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
        
    3. Если у вас нет версии 3,0 или более новой, вам нужно скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Перезагрузите компьютер после появления соответствующего запроса.
        
    4. Кроме того, вам потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online. 
    
    Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:
    
    > [!NOTE]
    > Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.
    >
    > Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений

- Чтобы создать политику для настроек, запустите следующую команду:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Дополнительные сведения о командлете [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Дополнительные сведения о командлете [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Если вы уже создали политику, вы можете использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) , чтобы применить параметры к вашим пользователям.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях

- Чтобы создать политику для настроек, запустите следующую команду:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Дополнительные сведения о командлете [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Дополнительные сведения о командлете [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Если вы уже создали политику, вы можете использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) , чтобы применить параметры к вашим пользователям.
  
### <a name="prevent-showing-recent-contacts"></a>Запрет отображения последних контактов

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Дополнительные сведения о командлете [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Дополнительные сведения о командлете [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
  Если вы уже создали политику, вы можете использовать командлет [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) , чтобы применить параметры к вашим пользователям.
  
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

[Настройка политик конференц-связи в Организации](set-up-conferencing-policies-for-your-organization.md)

  
 
