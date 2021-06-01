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
ms.openlocfilehash: 59bc9ab406d530bc09803b61cfc4341617dc911d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240091"
---
# <a name="set-up-client-policies-for-your-organization"></a>Настройка политик клиента в организации

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Политики клиента помогают определить функции Skype для бизнеса online, доступные пользователям. Например, вы можете предоставить одним пользователям право передавать файлы и запретить это другим пользователям.
  
Параметры политики клиента можно настроить во время создания политики или изменить параметры существующей политики с помощью cmdlet **Set-CsClientPolicy.**
  
## <a name="set-your-client-policies"></a>Задание политик клиента

> [!NOTE]
> Для всех настроек политики клиента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="start-windows-powershell"></a>Начните Windows PowerShell

> [!NOTE]
> Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell. Если вы используете последнюю версию Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Отключение эмотиконов, уведомлений о присутствии и запрет на сохранение мгновенных сообщений

- Чтобы создать политику для настроек, запустите следующую команду:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Дополнительные возможности [см. в поле New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  См. дополнительные [новости о cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Если вы уже создали политику, вы можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](/powershell/module/skype/Set-CsClientPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Разрешение перехода по URL-адресам или гиперссылкам в мгновенных сообщениях

- Чтобы создать политику для настроек, запустите следующую команду:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Дополнительные возможности [см. в поле New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  См. дополнительные [новости о cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Если вы уже создали политику, вы можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](/powershell/module/skype/Set-CsClientPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
  
### <a name="prevent-showing-recent-contacts"></a>Запрет отображения последних контактов

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Дополнительные возможности [см. в поле New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  См. дополнительные [новости о cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
  Если вы уже создали политику, вы можете изменить существующую политику с помощью cmdlet [Set-CsClientPolicy,](/powershell/module/skype/Set-CsClientPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Блокировка передачи файлов по точкам](block-point-to-point-file-transfers.md)

[Настройка политик conferencing в организации](set-up-conferencing-policies-for-your-organization.md)

  
