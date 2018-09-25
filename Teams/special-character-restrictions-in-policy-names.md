---
title: Какие существуют ограничения специального символа в политиках групп?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
- skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: В разделе проблемы в имена политик и что можно сделать для fix it для есть со специальными знаками.
ms.openlocfilehash: e1d46f70b42b96b2f3811c97d0110946fd013cd7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017505"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Какие существуют ограничения специального символа в политиках групп?

**Не удается создать или изменить политики (для обмена мгновенными сообщениями, собраний, и т.д.), которые имеют специальных символов в поле имя в группами Майкрософт и Скайп по центру администрирования бизнес.** 

Если имя политики содержит специальные символы, вам будет ограничен в управлении эти политики в Microsoft групп и Скайп по центру администрирования бизнес. **Таким образом, мы настоятельно рекомендуем, что имена политики не включать специальные символы**. 

Имена политик, которые были созданы с помощью PowerShell для собраний и системы обмена сообщениями в группах может иметь специальные символы такие как @, #, $. Тем не менее если которых требуется внести изменения в политике в группами Майкрософт и Скайп по центру администрирования Business, не будут иметь возможность. 

Если у вас есть политики со специальными знаками, необходимо будет либо изменить политику, с помощью Windows PowerShell (всегда), или создать новую политику в группами Майкрософт и Скайп по центру администрирования бизнес с теми же настройками, как старая политика и назначьте его же груп p пользователей.

## <a name="to-remove-special-characters"></a>Для удаления специальных символов



**Шаг 1 - удаленного подключения с помощью PowerShell.** 
 [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , если она еще не установлена.
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Шаг 2 — получить параметры для старой политики и записывать выходные данные.**

> [!NOTE]
> В этом примере — для политики [системы обмена сообщениями](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  Действия будут иметь одинаковые для других типов политики, но необходимо использовать правильный командлета. 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Шаг 3 — Создание новой политики.**

Можно создать новую политику с тот же параметр, с помощью групп Майкрософт и Скайп для бизнеса центра администрирования или PowerShell.

Выполнение этого можно создать новую политику, но необходимо добавить правильные параметры, ознакомившись [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) и затем запустить его:

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Шаг 4 - назначьте политику.**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Отображается, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) для получения дополнительных сведений о этот командлет.

**Шаг 5 – удаление старой политики.**

Это приведет к удалению старая политика со специальными знаками.
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Отображается, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) для получения дополнительных сведений о этот командлет.

Если эта команда выполнена успешно, все готово. Приведенная выше команда возвращает ошибку, вызвано тем, что старая политика назначена пользователям, поэтому необходимо запустить для удаления всех для пользователей из политики:

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Почему необходимо использовать Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Скайп для бизнеса в Интернет позволяет создавать удаленного сеанса Windows PowerShell, который подключается к Скайп для бизнеса в Интернет и рабочих групп Microsoft. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
### <a name="related-topics"></a>Связанные разделы
