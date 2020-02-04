---
title: 'Lync Server 2013: развертывание представления общей линии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e0f6aeb7d235ea7691c6878a4f21e6ec98f531e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Развертывание представления общей линии в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-06-13_

В этой статье рассказывается о том, как развернуть общий вид линии (SLA) в Lync Server 2013, Накопительное обновление от апреля 2016 г. SLA является функцией для обработки нескольких вызовов на определенный номер, который называется общим.

Подробнее об этой функции можно найти в разделе [планирование отображения общей линии в Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

Общий вид линии (SLA) — это новая функция в Lync Server 2013, Накопительное обновление от 2016 апреля. Для включения этой функции сначала требуется развернуть это обновление.

<div>

## <a name="install-shared-line-appearance"></a>Установка Shared Line Appearance

1.  После того как Lync Server 2013, Накопительное обновление от апреля 2016 развернуто, приложение SLA по умолчанию отключено. Чтобы включить приложение, выполните указанные ниже действия.
    
    1.  Зарегистрировать SLA в качестве серверного приложения, запустив следующую команду для каждого пула:
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        где %FQDN% — полное доменное имя пула.
    
    2.  Запустить следующую команду для обновления ролей RBAC для командлетов SLA:
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Перезагрузить все серверы переднего плана (служба RTCSRV) во всех пулах, в которых установлено и включено приложение SLA:
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Создать группу SLA и добавить в нее пользователей

1.  Создать группу SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Командлет Set-CsSlaConfiguration отмечает SLAGroup1 учетной записи корпоративной голосовой связи в качестве объекта SLA, а номер SLAGroup1 становится номером группы SLA. Все вызовы в SLAGroup1 будут направлены всей группе SLA.
    
    В следующем примере группа SLA создается для существующего пользователя корпоративной голосовой связи, SLAGroup1. Номер, назначенный для SLAGroup1, используется в качестве магистрального номера SLA.
    
    Команда устанавливает максимальное количество одновременных звонков для новой группы SLA: 3. Четвертый и последующие вызовы будут получать сигнал "занято".
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Set-CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.
    
    <div>
    

    > [!NOTE]  
    > Обратите внимание, что заданное вами значение <CODE>-Identity</CODE> должно быть действительной существующей учетной записью пользователя, поддерживающего голосовую почту.

    
    </div>

2.  Добавление делегатов в группы выполняется с помощью командлета [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates):
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    The following example adds a user to the SLA group. Каждый пользователь, добавленный в группу, должен быть допустимым корпоративным пользователям с поддержкой голосовой связи:
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Повторите командлет для каждого пользователя, которого необходимо добавить в группу. Пользователи могут принадлежать только одной группе SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Настройка опции "Занято" для группы SLA

1.  Настроить опцию "Занято" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    В следующем примере настраивается переадресация вызовов, превышающих максимальное количество одновременных вызовов, на телефонный номер 202-555-1234. Конечный объект может быть пользователем в вашей организации вместо номера телефона; в этом случае синтаксис для абонента, получающего переадресованные звонки, такой же, как и при указании делегата `sip:<NameofDelegate@domain>`:. Другой возможный параметр `BusyOption` `Voicemail`:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Настройка опции "Пропущенный вызов" для группы SLA

1.  Настроить опцию "Пропущенный вызов" для группы SLA можно с помощью командлета [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    В следующем примере задается, что пропущенные звонки будут переадресованы пользователю `sla_forward_number`с именем. `-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect` Если выбрать `Forward`, необходимо также указать `-MissedCallForwardTarget` параметр, указав в качестве целевого номера пользователя или номер телефона.
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

1.  Удалить делегата из группы можно с помощью командлета [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates):
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Например:
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>Удаление группы SLA

1.  Удалить группу SLA можно с помощью командлета [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps).
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Например:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

