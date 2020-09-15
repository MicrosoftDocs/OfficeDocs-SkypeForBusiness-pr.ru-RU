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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Посмотрите, какие проблемы имеют специальные символы в именах политик и что можно сделать для их исправления.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814718"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Каковы ограничения для специальных знаков в политиках Teams?

**Вы не можете создавать и изменять политики (для сообщений, собраний и т. д.), у которых есть специальный символ в имени в центре администрирования Microsoft Teams**. 

Если имя политики содержат специальные символы, вы будете ограничиваться управлением этими политиками в центре администрирования Microsoft Teams. Поэтому **мы настоятельно рекомендуем использовать в именах политик специальные символы**. 

Имена политик, созданные с помощью PowerShell для собраний и обмена сообщениями в Teams, могут содержать специальные символы, такие как @, #, $. Тем не менее, если вы хотите внести изменения в политику в центре администрирования Microsoft Teams, вам не удастся. 

Если у вас есть политика со специальными символами, вам нужно либо изменить политику с помощью Windows PowerShell (бессрочно), либо создать новую политику в центре администрирования Microsoft Teams с теми же параметрами, что и у старой политики, и назначить ее той же группе пользователей.

## <a name="to-remove-special-characters"></a>Удаление специальных знаков

**Шаг 1: Создание удаленного подключения с помощью PowerShell.**
> [!NOTE]
> Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.
>
> Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Шаг 2: получение параметров для старой политики и запись выходных данных.**

> [!NOTE]
> Этот пример предназначен для политики [обмена сообщениями](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  Эти шаги будут одинаковыми для других типов политик, но необходимо использовать правильный командлет. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Шаг 3: создание новой политики.**

Вы можете создать новую политику с тем же параметром, используя центр администрирования Microsoft Teams или PowerShell.

При выполнении этой команды будет создана новая политика, но вам потребуется добавить правильные параметры, просмотрев параметр [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) , а затем запустить его:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Шаг 4: назначение политики.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Дополнительные сведения об этом командлете: [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .

**Шаг 5 — Удаление старой политики.**

Старая политика будет удалена с использованием специальных символов.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Для получения дополнительных сведений о данном командлете, щелкните ссылку [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .

Если эта команда выполнена успешно, все готово. Если команда выше возвращает сообщение об ошибке, это связано с тем, что старая политика назначается пользователям, поэтому для удаления всех назначенных пользователей из политики необходимо выполнить указанные ниже действия.

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем использовать Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности при использовании только в центре администрирования Microsoft 365, например при изменении параметров для нескольких пользователей за один раз. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса Online позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online и Microsoft Teams. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  

