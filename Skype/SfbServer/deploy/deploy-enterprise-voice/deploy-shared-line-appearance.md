---
title: Развертывание распределенной линии для Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: В этом разделе описывается развертывание Shared Line Appearance (SLA) в накопительном пакете обновления Skype для бизнеса Server 2015 от ноября 2015 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.
ms.openlocfilehash: c0da29e54f03a5c328f1b65807f438b63c14a68f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878650"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Развертывание распределенной линии для Skype для бизнеса Server 2015

В этом разделе описывается развертывание Shared Line Appearance (SLA) в накопительном пакете обновления Skype для бизнеса Server 2015 от ноября 2015 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.

Дополнительные сведения об этой функции см. в разделе [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Внешний вид общей строки (SLA) — это новая возможность в Скайп для Business Server 2015 ноября накопительного обновления. Для включения этой функции сначала требуется развернуть это обновление.

### <a name="install-shared-line-appearance"></a>Установка Shared Line Appearance

1. После Скайп для Business Server 2015 ноября развертывается накопительное обновление, запустите `SkypeServerUpdateInstaller.exe` исправлений на каждом сервере переднего плана в пуле.

2. Программа установки разворачивает последнюю версию приложения SLA, однако приложение не включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.

    а. Зарегистрировать SLA в качестве серверного приложения, запустив следующую команду для каждого пула:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   где %FQDN% — полное доменное имя пула.

    б. Запустить следующую команду для обновления ролей RBAC для командлетов SLA:

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
    > Обратите внимание на то, что указанное для `-Identity` должен быть допустимый существующей учетной записи пользователя с включенной поддержкой корпоративной голосовой связи.

2. Добавление делегатов в группы выполняется с помощью командлета [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps):

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    The following example adds a user to the SLA group. Каждый пользователь добавлен в группу по должен быть допустимый пользователя с включенной поддержкой корпоративной голосовой связи:

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Повторите командлет для каждого пользователя, которого необходимо добавить в группу. Пользователи могут принадлежать только одной группе SLA.

### <a name="configure-the-sla-group-busy-option"></a>Настройка опции "Занято" для группы SLA

- Настроить опцию "Занято" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    В следующем примере настраивается переадресация вызовов, превышающих максимальное количество одновременных вызовов, на телефонный номер 202-555-1234. Целевой объект может быть пользователей в вашей организации, а не номер телефона; в этом случае используется следующий синтаксис для пользователя принимать звонки, перенаправленные то же, что при указании делегата: `sip:<NameofDelegate@domain>`. Возможные параметра для `BusyOption` — это `Voicemail`:

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Настройка опции "Пропущенный вызов" для группы SLA

1. Настроить опцию "Пропущенный вызов" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. В следующем примере указывается, что пропущенных звонков должны перенаправляться пользователю с именем `sla_forward_number`. Допустимые параметры для `-MissedCallOption` , параметр `Forward`, `BusySignal`, или `Disconnect`. Если выбрано `Forward`, необходимо также включить `-MissedCallForwardTarget` параметр с пользователя или на телефонный номер целевым:

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


