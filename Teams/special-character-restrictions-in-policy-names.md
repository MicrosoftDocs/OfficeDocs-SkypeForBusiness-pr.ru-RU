---
title: Ограничения для специальных знаков в политиках Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Узнайте о проблемах со специальными символами в именах политик и о том, что можно сделать для их устранения.
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860082"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Каковы ограничения для специальных знаков в политиках Teams?

**Вы не можете** создавать или изменять политики (для обмена сообщениями, собраний и т. д.), которые имеют специальный символ в имени в Microsoft Teams администрирования. 

Если имя политики содержит специальные символы, вы будете ограничены в управлении этими политиками в Microsoft Teams администрирования. **Поэтому мы настоятельно рекомендуем** не включать специальные символы в имена политик. 

Имена политик, созданные с помощью PowerShell для собраний и обмена сообщениями в Teams могут иметь специальные символы, такие как @,#,$. Однако если вы хотите внести изменения в политику в центре Microsoft Teams администрирования, вы не сможете этого сделать. 

Если у вас есть политика со специальными символами, вам потребуется либо изменить политику с помощью Windows PowerShell (навсегда), либо создать новую политику в центре администрирования Microsoft Teams с тем же параметром, что и старая политика, и назначить ее той же группе пользователей.

## <a name="to-remove-special-characters"></a>Удаление специальных символов

**Шаг 1. Создание удаленного подключения с помощью PowerShell.**
> [!NOTE]
> Skype для бизнеса Online Connector в настоящее время является частью последней версии Teams PowerShell.
>
> Если вы используете последнюю версию [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), устанавливать соединитель Skype для бизнеса Online не требуется.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Шаг 2. Получение параметров старой политики и запись выходных данных.**

> [!NOTE]
> Этот пример предназначен для политики [обмена сообщениями](/powershell/module/skype/get-csteamsmessagingpolicy) .  Эти действия будут одинаковыми для других типов политик, но необходимо использовать правильный командлет. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Шаг 3. Создание новой политики.**

Вы можете создать новую политику с тем же параметром с помощью Microsoft Teams центра администрирования или PowerShell.

При выполнении этой команды будет создаваться новая политика, но вам потребуется добавить правильные параметры, просмотрев [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) и запустив ее:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Шаг 4. Назначение политики.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Дополнительные [сведения об этом командлете см. в разделе Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) .

**Шаг 5. Удаление старой политики.**

При этом будет удалена старая политика со специальными символами.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Дополнительные [сведения об этом командлете см. в разделе Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) .

Если эта команда выполнена успешно, все готово. Если приведенная выше команда возвращает ошибку, это вызвано тем, что старая политика назначена пользователям, поэтому необходимо выполнить команду, чтобы удалить всех назначенных пользователей из политики:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Почему необходимо использовать Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и производительности по сравнению с использованием только Центр администрирования Microsoft 365, например при одновременном изменении параметров для многих пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса Online позволяет создать удаленный сеанс Windows PowerShell, который подключается к Skype для бизнеса Online и Microsoft Teams. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector).
