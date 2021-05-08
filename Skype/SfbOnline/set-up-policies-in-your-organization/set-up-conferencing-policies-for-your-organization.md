---
title: Настройка политик аудиоконференций в организации
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: "Конференц-связь \x97 это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами."
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240081"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Настройка политик аудиоконференций в организации

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Конференц-связь  это важная часть Skype для бизнеса online: она позволяет группам пользователей объединяться, чтобы просматривать презентации и видео, делиться приложениями, обмениваться файлами, общаться и совместно работать другими способами.
  
Конференциями и их настройками нужно управлять. В некоторых случаях могут возникать проблемы безопасности: по умолчанию в собраниях могут участвовать все (даже не прошедшие проверку подлинности пользователи). Они могут сохранять презентации или раздаточный материал. Кроме того, могут возникать юридические вопросы. Например, по умолчанию участники собрания могут добавлять заметки к общедоступному содержимому. Но эти заметки не сохраняются после архивации собрания. Если вашей организации нужно сохранять переписку, отключите заметки. 
  
В Skype для бизнеса online конференции управляются с помощью политик. Политики конференций определяют доступные функции и возможности, в том числе то, разрешена ли передача звука и видео по протоколу IP максимальному числу участников собрания. Политики можно настроить глобально или для каждого пользователя, что дает администраторам большую гибкость.
  
Параметры политики можно настроить во время ее создания. Чтобы изменить параметры существующей политики, используйте командлет **Set-CsConferencingPolicy**.
  
## <a name="set-your-conferencing-policies"></a>Задание политик конференц-связи

> [!NOTE]
> Для всех параметров политики конференц-связи в Skype для бизнеса online нужно использовать Windows PowerShell. **Нельзя использовать** **Центр администрирования Skype для бизнеса**. 

### <a name="start-windows-powershell"></a>Начните Windows PowerShell

 > [!Note]
> Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell. Если вы используете последний общедоступный Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Блокирование перемещения файлов и демонстрации рабочего стола во время собраний

- Чтобы создать политику для настроек, запустите следующую команду:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   См. дополнительные новости о [новом csConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   См. дополнительные новости [о cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
  Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy), чтобы применить настройки к пользователям.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Блокирование записи конференций и запрет анонимных участников собрания

- Чтобы создать политику для настроек, запустите следующую команду: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   См. дополнительные новости о [новом csConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Чтобы предоставить новую политику Amos Marble, запустите следующую команду:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   См. дополнительные новости [о cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Если вы уже создали политику, вы можете применить параметры к пользователям с помощью cmdlet [Set-CsConferencingPolicy,](/powershell/module/skype/Set-CsConferencingPolicy) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Запрет записи собраний анонимными участниками и сохранения содержимого собрания внешними пользователями

- Чтобы создать политику для настроек, запустите следующую команду:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   См. дополнительные новости о [новом csConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Чтобы предоставить новую политику всем пользователям в организации, запустите следующую команду:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

См. дополнительные новости [о cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Если политика уже создана, используйте командлет [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy), чтобы применить настройки к пользователям.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Блокировка передачи файлов по точкам](block-point-to-point-file-transfers.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

  
