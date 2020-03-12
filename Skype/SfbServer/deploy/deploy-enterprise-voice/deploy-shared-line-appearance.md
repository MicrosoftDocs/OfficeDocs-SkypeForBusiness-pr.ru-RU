---
title: Развертывание общего внешнего вида линии в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этом разделе рассказывается, как развернуть общий внешний вид линии (SLA) в Skype для бизнеса Server 2015 с накопительным пакетом обновления за Ноябрь 2015 г. SLA — это функция для обработки нескольких звонков по определенному номеру, который называется общим номером.
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604226"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Развертывание общего внешнего вида линии в Skype для бизнеса Server 2015

В этом разделе рассказывается, как развернуть общий внешний вид линии (SLA) в Skype для бизнеса Server 2015 с накопительным пакетом обновления за Ноябрь 2015 г. SLA — это функция для обработки нескольких звонков по определенному номеру, который называется общим номером.

Дополнительные сведения об этой функции можно найти [в статье Plan for Shared Line Appearance в Skype для бизнеса Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Общий вид линии (SLA) — это новая функция в Skype для бизнеса Server, накопительный пакет обновления за Ноябрь 2015 ноября. Чтобы включить эту функцию, сначала необходимо развернуть это накопительное обновление.

### <a name="install-shared-line-appearance"></a>Установка внешнего вида общей линии

1. После установки накопительного пакета обновления для Skype для бизнеса Server с 2015 ноября выполните `SkypeServerUpdateInstaller.exe` обновление на каждом сервере переднего плана в пуле.

2. Установщик будет развертывать последнюю версию приложения SLA, но приложение по умолчанию отключено. Он включен, выполнив действия, описанные ниже.

    а. Зарегистрируйте SLA как серверное приложение, выполнив следующую команду для каждого пула:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   где% FQDN% — полное доменное имя пула.

    б. Выполните следующую команду, чтобы обновить роли RBAC для командлетов SLA:

   ```powershell
   Update-CsAdminRole
   ```

    в. Перезапустите все серверы переднего плана (служба RTCSRV) во всех пулах, где установлено и включено соглашение об уровне обслуживания:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Создание группы SLA и добавление в нее пользователей

1. Создайте группу SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Командлет Set – CsSlaConfiguration помечает учетную запись корпоративного голоса SLAGroup1 как сущность SLA, а число SLAGroup1 становится номером для группы SLA. Все звонки на SLAGroup1 будут звонить всей группе SLA.

    В следующем примере создается группа SLA для существующего пользователя корпоративной голосовой связи, SLAGroup1, и используется номер, назначенный для SLAGroup1, в качестве номера магистрали SLA.

    Команда устанавливает максимальное количество одновременных вызовов для новой группы SLA равным 3, а для звонков, передаваемых по сигналу занятости:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Set – CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.

    > [!NOTE]
    > Обратите внимание, что вы `-Identity` указали действительную учетную запись пользователя с включенной поддержкой корпоративной голосовой связи.

2. Добавьте делегатов для группы с помощью командлета [Add – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    В примере ниже показано, как добавить пользователя в группу SLA. Каждый пользователь, добавляемый в группу, должен быть действительным пользователем корпоративной голосовой связи:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Повторите командлет для каждого пользователя, которого вы хотите добавить в группу. Пользователи могут принадлежать только одной группе SLA.

### <a name="configure-the-sla-group-busy-option"></a>Настройка параметра "занято" для группы SLA

- Настройте параметр "занято" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    В следующем примере задаются вызовы, которые превышают максимальное число одновременных вызовов, перенаправляемых на номер телефона 202-555-1234. Целевой объект может быть пользователем в вашей организации, а не номером телефона; в этом случае синтаксис для человека, получающего переадресованные звонки, совпадает с тем, что при указании делегата: `sip:<NameofDelegate@domain>`. Второй возможный параметр `BusyOption` `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Настройка функции "Пропущенный вызов" для группы SLA

1. Настройте параметр "Пропущенный вызов" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. В приведенном ниже примере указывается, что пропущенные звонки пересылаются пользователю с `sla_forward_number`именем. `-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect` `Forward`Если выбран этот `-MissedCallForwardTarget` параметр, необходимо также включить параметр с номером пользователя или телефона в качестве целевого значения:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

- Удаление делегата из группы с помощью командлета [Remove – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Пример.

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Удаление группы SLA

- Удалить группу SLA можно с помощью командлета [Remove – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Пример:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


