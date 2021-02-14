---
title: Развертывание общей линии в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: В этом разделе вы узнаете, как развернуть SLA в накопительном обновлении Skype для бизнеса Server 2015 за ноябрь 2015 г. SLA — это функция для обработки нескольких вызовов на определенный номер, называемый общим номером.
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812409"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Развертывание общей линии в Skype для бизнеса Server 2015

В этом разделе вы узнаете, как развернуть SLA в накопительном обновлении Skype для бизнеса Server 2015 за ноябрь 2015 г. SLA — это функция для обработки нескольких вызовов на определенный номер, называемый общим номером.

Дополнительные сведения об этой функции см. в подстройки [Plan for Shared Line Appearance in Skype for Business Server 2015.](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)

Shared Line Appearance (SLA) — это новая функция в Накопительном обновлении Skype для бизнеса Server за ноябрь 2015 г. Чтобы включить эту функцию, необходимо сначала развернуть это накопительное обновление.

### <a name="install-shared-line-appearance"></a>Установка внешнего вида общей линии

1. После развертывания накопительного обновления Skype для бизнеса Server за ноябрь 2015 г. запустите исправление на каждом сервере переднего сервера  `SkypeServerUpdateInstaller.exe` в пуле.

2. Установщик развернет последнюю версию приложения SLA, однако по умолчанию приложение не включено. Она включена с помощью описанных ниже действий.

    а. Зарегистрируйте SLA в качестве серверного приложения, выдав следующую команду для каждого пула:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   где %FQDN% — это полное доменное имя пула.

    б. Чтобы обновить роли RBAC для командлетов SLA, запустите следующую команду:

   ```powershell
   Update-CsAdminRole
   ```

    в. Перезапустите все серверы переднего сервера (служба RTCSRV) во всех пулах, где было установлено и включено SLA:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Создание группы SLA и добавление в нее пользователей

1. Создайте группу SLA с помощью [cmdlet Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Этот Set-CsSlaConfiguration пометит учетную запись Корпоративная голосовая связь SLAGroup1 как сущность SLA, а число SLAGroup1 станет номером для группы SLA. Все вызовы SLAGroup1 будут звонить всей группе SLA.

    В следующем примере создается группа SLA для существующего пользователя Корпоративная голосовая связь SLAGroup1 и используется номер, присвоенный SLAGroup1 в качестве номера основной линии SLA.

    Эта команда задает максимальное число одновременно звонков для новой группы SLA как 3, так и для вызовов, превышает которые, чтобы прослушать сигнал "занято":

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    С помощью Set-CsSlaConfiguration можно создать новую группу SLA или изменить существующую.

    > [!NOTE]
    > Обратите внимание, что указанная учетная запись должна быть действительной  `-Identity` Корпоративная голосовая связь с включенной поддержкой учетной записи пользователя.

2. Добавьте делегатов в группу с помощью [cmdlet Add-CsSlaDelegates:](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    В следующем примере пользователь добавляется в группу SLA. Каждый пользователь, добавленный в группу, должен быть действительным Корпоративная голосовая связь с включенной поддержкой:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Повторите этот действия для каждого пользователя, который требуется добавить в группу. Пользователи могут принадлежать только одной группе SLA.

### <a name="configure-the-sla-group-busy-option"></a>Настройка параметра занятости группы SLA

- Настройте параметр занятости группы SLA с помощью [cmdlet Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    В следующем примере задаются вызовы, превышающего максимальное количество одновременно переадреаментных вызовов на телефонный номер 202-555-1234. Целью может быть пользователь в организации, а не номер телефона; в этом случае синтаксис для лица, который будет принимать переад вперед вызовы, такой же, как при указании делегата:  `sip:<NameofDelegate@domain>` . Другой возможный `BusyOption` параметр: `Voicemail`

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Настройка параметра "Пропущенный звонок" для группы SLA

1. Настройте параметр "Пропущенный звонок" для группы SLA с помощью [cmdlet Set-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. В следующем примере указывается, что пропущенные вызовы необходимо переадлить пользователю с именем  `sla_forward_number` . Допустимые  `-MissedCallOption` параметры: `Forward`  `BusySignal` , , или  `Disconnect` . При выборе этого параметра необходимо также включить параметр с пользователем или номером телефона  `Forward`  `-MissedCallForwardTarget` в качестве целевого параметра:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

- Удалите делегата из группы с помощью [cmdlet Remove-CsSlaDelegates:](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Пример:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Удаление группы SLA

- Удалите группу SLA с помощью [cmdlet Remove-CsSlaConfiguration:](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Пример:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


