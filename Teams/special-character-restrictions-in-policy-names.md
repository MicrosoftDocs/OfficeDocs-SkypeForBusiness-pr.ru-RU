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
description: Узнайте о проблемах со специальными знаками в именах политик и о том, как их устранить.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116987"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Каковы ограничения для специальных знаков в политиках Teams?

**В Центре администрирования Microsoft Teams** нельзя создавать и изменять политики (для сообщений, собраний и т. д.), которые имеют специальный знак в имени. 

Если имя политики содержит специальные знаки, управление этими политиками будет ограничено в Центре администрирования Microsoft Teams. Поэтому мы настоятельно рекомендуем не использовать специальные **символы.** 

Имена политик, созданные с помощью PowerShell для собраний и обмена сообщениями в Teams, могут иметь специальные символы, такие как @,#,$. Однако если вы хотите внести изменения в политику в Центре администрирования Microsoft Teams, вы не сможете этого сделать. 

Если у вас есть политика со специальными символами, ее необходимо изменить с помощью Windows PowerShell (навсегда) или создать новую политику в Центре администрирования Microsoft Teams с тем же параметром, что и для старой политики, и назначить ее той же группе пользователей.

## <a name="to-remove-special-characters"></a>Удаление специальных символов

**Шаг 1. Удаленное подключение с помощью PowerShell.**
> [!NOTE]
> Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.
>
> Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Шаг 2. Просмотр параметров старой политики и создание выходных данных.**

> [!NOTE]
> Это пример для политики [обмена сообщениями.](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)  Действия будут одинаковыми для других типов политик, но необходимо использовать правильный cmdlet. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Шаг 3. Создание политики.**

Новую политику с тем же параметром можно создать с помощью Центра администрирования Microsoft Teams или PowerShell.

При запуске этой функции создается новая политика, но вам потребуется добавить правильные параметры, задав [параметры Set-CsTeamsMessagingPolicy,](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) а затем за запуск:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Шаг 4. Назначение политики.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Дополнительные сведения об этом cmdlet см. в подменю [Grant-CsTeamsMessagingPolicy.](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**Шаг 5. Удаление старой политики.**

При этом будет удалена старая политика со специальными символами.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Дополнительные сведения об этом cmdlet см. в [remove-CsTeamsMessagingPolicy.](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

Если эта команда будет успешной, все готово. Если вышеуказанная команда возвращает ошибку, это значит, что пользователям назначена старая политика, поэтому вам нужно выполнить ее, чтобы удалить из нее всех пользователей:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужна служба Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Модуль Windows PowerShell Skype для бизнеса Online позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online и Microsoft Teams. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
