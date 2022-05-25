---
title: Развертывание общего внешнего вида строки в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: В этом разделе описано, как развернуть общее соглашение об уровне обслуживания (SLA) Skype для бизнеса Server 2015 г., накопительное обновление за ноябрь 2015 г. Соглашение об уровне обслуживания — это функция для обработки нескольких вызовов на определенном номере, называемом общим номером.
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671595"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Развертывание общего внешнего вида строки в Skype для бизнеса Server 2015

В этом разделе описано, как развернуть общее соглашение об уровне обслуживания (SLA) Skype для бизнеса Server 2015 г., накопительное обновление за ноябрь 2015 г. Соглашение об уровне обслуживания — это функция для обработки нескольких вызовов на определенном номере, называемом общим номером.

Дополнительные сведения об этой функции см. в разделе [Plan for Shared Line Appearance in Skype для бизнеса Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Общее соглашение об уровне обслуживания (SLA) — это новая функция в накопительном Skype для бизнеса Server за ноябрь 2015 г. Чтобы включить эту функцию, необходимо сначала развернуть это накопительное обновление.

## <a name="install-shared-line-appearance"></a>Установка общего внешнего вида строки

1. После Skype для бизнеса Server обновления за ноябрь 2015 `SkypeServerUpdateInstaller.exe` г. запустите исправление на каждом сервере переднего плана в пуле.

2. Установщик развернет последнюю версию приложения SLA, однако приложение не включено по умолчанию. Она включена, выполнив описанные ниже действия.

    а. Зарегистрируйте соглашение об уровне обслуживания в качестве серверного приложения, выполнив следующую команду для каждого пула:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   где %FQDN% — это полное доменное имя пула.

    б. Выполните следующую команду, чтобы обновить роли RBAC для командлетов соглашения об уровне обслуживания:

   ```powershell
   Update-CsAdminRole
   ```

    c. Перезапустите все серверы переднего плана (служба RTCSRV) во всех пулах, где было установлено и включено соглашение об уровне обслуживания:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>Создание группы соглашений об уровне обслуживания и добавление пользователей в нее

1. Создайте группу соглашений об уровне обслуживания с помощью командлета [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Командлет Set-CsSlaConfiguration помечает учетную запись Корпоративная голосовая связь SLAGroup1 как сущность соглашения об уровне обслуживания, а число SLAGroup1 становится номером для группы соглашений об уровне обслуживания. Все вызовы SLAGroup1 будут вызывать всю группу соглашений об уровне обслуживания.

    В следующем примере создается группа соглашений об уровне обслуживания для существующего пользователя Корпоративная голосовая связь SLAGroup1 и используется номер, назначенный для SLAGroup1 в качестве номера основной строки соглашения об уровне обслуживания.

    Эта команда задает максимальное число одновременных вызовов для новой группы соглашений об уровне обслуживания в 3, а для вызовов, превышающее это значение, для прослушивания сигнала занятости:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Вы можете использовать Set-CsSlaConfiguration, чтобы создать новую группу соглашений об уровне обслуживания или изменить существующую.

    > [!NOTE]
    > Обратите внимание, что задаваемая учетная `-Identity` запись должна быть действительной Корпоративная голосовая связь с поддержкой учетной записи пользователя.

2. Добавьте делегатов в группу с помощью [командлета Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    В следующем примере пользователь добавляется в группу соглашений об уровне обслуживания. Каждый пользователь, добавленный в группу, должен быть допустимым Корпоративная голосовая связь с поддержкой:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Повторите командлет для каждого пользователя, которого вы хотите добавить в группу. Пользователи могут принадлежать только к одной группе соглашений об уровне обслуживания.

## <a name="configure-the-sla-group-busy-option"></a>Настройка параметра занятости группы SLA

- Настройте параметр занятости группы SLA с помощью [командлета Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    В следующем примере задается число вызовов, превышающее максимальное количество одновременных вызовов, которые будут перенаправлены на номер телефона 202-555-1234. Целевым объектом может быть пользователь в организации, а не номер телефона; В этом случае синтаксис для пользователя, который будет получать перенаправленные вызовы, такой же, как при указании делегата:  `sip:<NameofDelegate@domain>`. Другой возможный параметр:`BusyOption` `Voicemail`

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>Настройка параметра "Пропущенный звонок" для группы SLA

1. Настройте параметр пропускаемого вызова группы SLA с помощью командлета [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. В следующем примере указывается, что пропущенные вызовы должны перенаправляться пользователю с именем  `sla_forward_number`. Допустимые параметры`-MissedCallOption`: `Forward`, или `BusySignal``Disconnect`. При выборе параметра  `Forward`необходимо  `-MissedCallForwardTarget` также указать в качестве целевого объекта номер пользователя или телефона:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

- Удалите делегат из группы с помощью командлета [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Например:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>Удаление группы соглашений об уровне обслуживания

- Удалите группу соглашений об уровне обслуживания с помощью командлета [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Пример:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
