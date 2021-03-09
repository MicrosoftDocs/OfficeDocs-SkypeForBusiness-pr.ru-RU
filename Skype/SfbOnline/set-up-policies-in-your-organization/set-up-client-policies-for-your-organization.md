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
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569231"
---
# <a name="set-up-client-policies-for-your-organization"></a>Настройка политик клиента в организации

Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
  
Параметры политики клиента можно настроить во время создания политики или с помощью cmdlet **Set-CsClientPolicy** изменить параметры существующей политики.
  
## <a name="set-your-client-policies"></a>Задание политик клиента

> [!NOTE]
> Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="start-windows-powershell"></a>Начать Windows PowerShell

> [!NOTE]
> Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.
1. Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Откройте Windows PowerShell и запустите следующие команды: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
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

  Подробнее о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
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

  Подробнее о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
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

  Подробнее о [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
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

  
 
