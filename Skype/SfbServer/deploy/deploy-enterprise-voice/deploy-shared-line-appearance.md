---
title: Развертывание общих строк в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
description: Ознакомьтесь с этой темой, чтобы узнать, как развернуть общий внешний вид (SLA) в Skype для бизнеса Server 2015 г., ноябрь 2015 г. Накопительное обновление. SLA — это функция для обработки нескольких вызовов на определенном номере, называемом общим номером.
ms.openlocfilehash: edf731976ae9fbf36f99266f0d993c9e4e78fa34
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749448"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Развертывание общих строк в Skype для бизнеса Server 2015 г.

Ознакомьтесь с этой темой, чтобы узнать, как развернуть общий внешний вид (SLA) в Skype для бизнеса Server 2015 г., ноябрь 2015 г. Накопительное обновление. SLA — это функция для обработки нескольких вызовов на определенном номере, называемом общим номером.

Дополнительные сведения об этой функции см. в раздел [Plan for Shared Line Appearance in Skype для бизнеса Server 2015.](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)

Общий внешний вид строки (SLA) — это новая функция в Skype для бизнеса Server, ноябрь 2015 г. Накопительное обновление. Чтобы включить эту функцию, необходимо сначала развернуть это накопительное обновление.

### <a name="install-shared-line-appearance"></a>Установка общего внешнего вида строки

1. После Skype для бизнеса Server ноября 2015 года развертывание накопительного обновления запустите исправление на каждом переднем сервере `SkypeServerUpdateInstaller.exe` пула.

2. Установщик развернет последнюю версию приложения SLA, однако по умолчанию приложение не включено. Она включена, следуя описанным ниже шагам:

    А. Зарегистрируйте SLA в качестве серверного приложения, задав следующую команду для каждого пула:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   где %FQDN% — это полностью квалифицированное доменное имя пула.

    Б. Запустите следующую команду, чтобы обновить роли RBAC для командлетов SLA:

   ```powershell
   Update-CsAdminRole
   ```

    c. Перезапустите все серверы переднего конца (служба RTCSRV) во всех пулах, где была установлена и включена SLA:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Создание группы SLA и добавление пользователей в нее

1. Создайте группу SLA с помощью [комлета Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    В Set-CsSlaConfiguration см. в Корпоративная голосовая связь учетной записи SLAGroup1 как объекта SLA, а число SLAGroup1 становится номером для группы SLA. Все вызовы в SLAGroup1 обзывают всю группу SLA.

    В следующем примере создается группа SLA для существующего Корпоративная голосовая связь, SLAGroup1, и используется номер, назначенный для SLAGroup1 в качестве основного номера SLA.

    Команда задает максимальное количество одновременного вызова для новой группы SLA до 3, а для вызовов, превышает это, чтобы услышать сигнал загруженного:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Вы можете Set-CsSlaConfiguration создать новую группу SLA или изменить существующую.

    > [!NOTE]
    > Обратите внимание, что указанная вами учетная запись должна быть действительной Корпоративная голосовая связь `-Identity` учетной записи пользователя с включенной поддержкой.

2. Добавление делегатов в группу с помощью [cmdlet Add-CsSlaDelegates:](/powershell/module/skype/add-cssladelegates?view=skype-ps)

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    В следующем примере пользователь добавляется в группу SLA. Каждый пользователь, добавленный в группу, должен быть действительным Корпоративная голосовая связь с включенной поддержкой:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Повторите cmdlet для каждого пользователя, который необходимо добавить в группу. Пользователи могут принадлежать только к одной группе SLA.

### <a name="configure-the-sla-group-busy-option"></a>Настройка параметра занятости группы SLA

- Настройка параметра занятости группы SLA с помощью группы [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    В следующем примере задаются вызовы, которые превышают максимальное количество одновременно переадверяемых вызовов на телефонный номер 202-555-1234. Целью может быть пользователь в организации, а не номер телефона; в этом случае синтаксис для лица, получаюющего переададные вызовы, такой же, как при указании делегата:  `sip:<NameofDelegate@domain>` . Другой возможный `BusyOption` параметр: `Voicemail`

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Настройка параметра пропущенных вызовов группы SLA

1. Настройка параметра пропущенных вызовов группы SLA с помощью комлета [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. В следующем примере указывается, что пропущенные вызовы должны быть переад. `sla_forward_number` Допустимые  `-MissedCallOption` параметры `Forward` :  `BusySignal` , или  `Disconnect` . Если вы  `Forward` решите, необходимо также включить параметр, с пользователем или номером телефона  `-MissedCallForwardTarget` в качестве цели:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

- Удаление делегата из группы с помощью группы [Remove-CsSlaDelegates:](/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Например:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Удаление группы SLA

- Удалите группу SLA с помощью [комлета Remove-CsSlaConfiguration:](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Пример:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```