---
title: 'Lync Server 2013: развертывание общей линии внешнего вида'
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
ms.openlocfilehash: 3be8c6610d27040d608070ca1e7dfb50a29a0cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Развертывание общего внешнего вида линии в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-06-13_

В этом разделе рассказывается, как развернуть общий вид линии (SLA) в Lync Server 2013, накопительный пакет обновления от 2016 апреля. SLA — это функция для обработки нескольких звонков по определенному номеру, который называется общим номером.

Дополнительные сведения об этой функции можно найти [в статье Plan for Shared Line Appearance в Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

Общий вид линии (SLA) — это новая функция в Lync Server 2013, накопительный пакет обновления от 2016 апреля. Чтобы включить эту функцию, сначала необходимо развернуть это накопительное обновление.

<div>

## <a name="install-shared-line-appearance"></a>Установка внешнего вида общей линии

1.  После развертывания Lync Server 2013 обновление до 2016 апреля не включается по умолчанию. Чтобы включить приложение, выполните указанные ниже действия.
    
    1.  Зарегистрируйте SLA как серверное приложение, выполнив следующую команду для каждого пула:
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        где% FQDN% — полное доменное имя пула.
    
    2.  Выполните следующую команду, чтобы обновить роли RBAC для командлетов SLA:
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Перезапустите все серверы переднего плана (служба RTCSRV) во всех пулах, где установлено и включено соглашение об уровне обслуживания:
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Создание группы SLA и добавление в нее пользователей

1.  Создайте группу SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Командлет Set – CsSlaConfiguration помечает учетную запись корпоративного голоса SLAGroup1 как сущность SLA, а число SLAGroup1 становится номером для группы SLA. Все звонки на SLAGroup1 будут звонить всей группе SLA.
    
    В следующем примере создается группа SLA для существующего пользователя корпоративной голосовой связи, SLAGroup1, и используется номер, назначенный для SLAGroup1, в качестве номера магистрали SLA.
    
    Команда устанавливает максимальное количество одновременных вызовов для новой группы SLA равным 3, а для звонков, передаваемых по сигналу занятости:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Set – CsSlaConfiguration можно использовать для создания новой группы SLA или изменения существующей.
    
    <div>
    

    > [!NOTE]  
    > Обратите внимание, что вы <CODE>-Identity</CODE> указали действительную учетную запись пользователя с включенной поддержкой корпоративной голосовой связи.

    
    </div>

2.  Добавьте делегатов для группы с помощью командлета [Add – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    В примере ниже показано, как добавить пользователя в группу SLA. Каждый пользователь, добавляемый в группу, должен быть действительным пользователем корпоративной голосовой связи:
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Повторите командлет для каждого пользователя, которого вы хотите добавить в группу. Пользователи могут принадлежать только одной группе SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Настройка параметра "занято" для группы SLA

1.  Настройте параметр "занято" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    В следующем примере задаются вызовы, которые превышают максимальное число одновременных вызовов, перенаправляемых на номер телефона 202-555-1234. Целевой объект может быть пользователем в вашей организации, а не номером телефона; в этом случае синтаксис для человека, получающего переадресованные звонки, совпадает с тем, что при указании делегата: `sip:<NameofDelegate@domain>`. Второй возможный параметр `BusyOption` `Voicemail`:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Настройка функции "Пропущенный вызов" для группы SLA

1.  Настройте параметр "Пропущенный вызов" для группы SLA с помощью командлета [Set – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    В приведенном ниже примере указывается, что пропущенные звонки пересылаются пользователю с `sla_forward_number`именем. `-MissedCallOption` Допустимые параметры для параметра `Forward`:, `BusySignal`или. `Disconnect` `Forward`Если выбран этот `-MissedCallForwardTarget` параметр, необходимо также включить параметр с номером пользователя или телефона в качестве целевого значения:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Удаление делегата из группы

1.  Удаление делегата из группы с помощью командлета [Remove – CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :
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

1.  Удалить группу SLA можно с помощью командлета [Remove – CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Пример:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

