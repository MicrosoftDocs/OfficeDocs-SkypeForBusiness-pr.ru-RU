---
title: Развертывание распределенной линии для Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: В этом разделе описывается развертывание Shared Line Appearance (SLA) в накопительном пакете обновления Skype для бизнеса Server 2015 от ноября 2015 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.
ms.openlocfilehash: 040801c08490edb103fa195098ef8aa3483fc2e0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924860"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Развертывание распределенной линии для Skype для бизнеса Server 2015

В этом разделе описывается развертывание Shared Line Appearance (SLA) в накопительном пакете обновления Skype для бизнеса Server 2015 от ноября 2015 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.

Дополнительные сведения об этой функции см. в разделе [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Общий вид линии (SLA) — это новая функция в Skype для бизнеса Server, Накопительное обновление для 2015 ноября. Для включения этой функции сначала требуется развернуть это обновление.

### <a name="install-shared-line-appearance"></a>Установка Shared Line Appearance

1. После установки накопительного обновления для Skype для бизнеса на сервере 2015, запустите его `SkypeServerUpdateInstaller.exe` на каждом сервере переднего плана в пуле.

2. Программа установки разворачивает последнюю версию приложения SLA, однако приложение не включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.

    a) Зарегистрировать SLA в качестве серверного приложения, запустив следующую команду для каждого пула:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   где %FQDN% — полное доменное имя пула.

    б) Запустить следующую команду для обновления ролей RBAC для командлетов SLA:

   ```
   Update-CsAdminRole
   ```

    в. Перезагрузить все серверы переднего плана (служба RTCSRV) во всех пулах, в которых установлено и включено приложение SLA:

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Создать группу SLA и добавить в нее пользователей

1. Создать группу SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Командлет Set-CsSlaConfiguration отмечает SLAGroup1 учетной записи корпоративной голосовой связи в качестве объекта SLA, а номер SLAGroup1 становится номером группы SLA. Все вызовы в SLAGroup1 будут направлены всей группе SLA.

    В следующем примере группа SLA создается для существующего пользователя корпоративной голосовой связи, SLAGroup1. Номер, назначенный для SLAGroup1, используется в качестве магистрального номера SLA.

    Команда устанавливает максимальное количество одновременных звонков для новой группы SLA: 3. Четвертый и последующие вызовы будут получать сигнал "занято".

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Set-CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.

    > [!NOTE]
    > Обратите внимание, что заданное вами значение `-Identity` должно быть действительной существующей учетной записью пользователя, поддерживающего голосовую почту.

2. Добавление делегатов в группы выполняется с помощью командлета [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps):

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    The following example adds a user to the SLA group. Каждый пользователь, добавленный в группу, должен быть допустимым корпоративным пользователям с поддержкой голосовой связи:

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Повторите командлет для каждого пользователя, которого необходимо добавить в группу. Пользователи могут принадлежать только одной группе SLA.

### <a name="configure-the-sla-group-busy-option"></a>Настройка опции "Занято" для группы SLA

- Настроить опцию "Занято" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    В следующем примере настраивается переадресация вызовов, превышающих максимальное количество одновременных вызовов, на телефонный номер 202-555-1234. Конечный объект может быть пользователем в вашей организации вместо номера телефона; в этом случае синтаксис для абонента, получающего переадресованные звонки, такой же, как и при указании делегата `sip:<NameofDelegate@domain>`:. Другой возможный параметр `BusyOption` `Voicemail`:

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Настройка опции "Пропущенный вызов" для группы SLA

1. Настроить опцию "Пропущенный вызов" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. В следующем примере задается, что пропущенные звонки будут переадресованы пользователю `sla_forward_number`с именем. `-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect` Если выбрать `Forward`, необходимо также указать `-MissedCallForwardTarget` параметр, указав в качестве целевого номера пользователя или номер телефона.

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

- Удалить делегата из группы можно с помощью командлета [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps):

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Например:

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Удаление группы SLA

- Удалить группу SLA можно с помощью командлета [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps).

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Например:

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


