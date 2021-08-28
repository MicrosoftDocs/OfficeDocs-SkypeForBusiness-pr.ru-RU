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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
ms.openlocfilehash: 9113c5852d731a12f428e8f53724a5f66b4b8b9a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587861"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Настройка политик мобильных устройств в организации

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Можно настроить способ подключения к Skype для бизнеса Online с помощью приложения Skype для бизнеса на мобильных устройствах, например с помощью функции, которая позволяет пользователям совершать и принимать звонки по рабочим, а не личным номерам мобильных телефонов. Можно также использовать политики мобильных устройств, чтобы запросить подключение Wi-Fi при звонках.
  
Параметры политики мобильных устройств можно настроить во время создания политики. Чтобы изменить настройки существующей политики, используйте командлет **Set-CsMobilityPolicy**.
  
## <a name="set-your-mobile-policies"></a>Задание политик мобильных устройств

> [!NOTE]
> Для всех параметров политики мобильных устройств в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 
  
### <a name="start-windows-powershell"></a>Начать Windows PowerShell

> [!NOTE]
> Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или Office 365 в одном окне [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Требование подключения Wi-Fi для видеосвязи с пользователем

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   См. дополнительные [новости о новом CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   См. дополнительные [новости о cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy), чтобы применить настройки к пользователям.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Запрет на использование приложения Skype для бизнеса

- Чтобы создать политику для настроек, запустите следующую команду:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  См. дополнительные [новости о новом CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   См. дополнительные [новости о cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Если вы уже создали политику, вы можете изменить существующую политику с помощью cmdlet [Set-CsMobilityPolicy,](/powershell/module/skype/Set-CsMobilityPolicy) а затем применить этот параметр к пользователям с помощью cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Запрет звонков по VoIP на мобильных устройствах

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   См. дополнительные [новости о новом CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  См. дополнительные [новости о cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
Если политика уже создана, используйте командлет [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy), чтобы применить настройки к пользователям.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Блокировка передачи файлов по точкам](block-point-to-point-file-transfers.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик conferencing в организации](set-up-conferencing-policies-for-your-organization.md)

  
