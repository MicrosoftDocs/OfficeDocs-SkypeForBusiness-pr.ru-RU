---
title: 'Lync Server 2013: сброс правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa5bd589a6368e99401f2f84d702756d595f9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Сброс правила обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Если вы не хотите, чтобы обновление работала на тестовых устройствах, можно сбросить правило обновления устройства, которое удаляет состояние ожидания правила и удаляет обновление с тестовых устройств.

Правило обновления устройства можно удалить с помощью панели управления Lync Server или Windows PowerShell.

<div>


> [!NOTE]  
> Чтобы удалить правило, которое вы уже утвердили (то есть выполните откат), восстановите его. Для получения дополнительных сведений см. <A href="lync-server-2013-restore-a-device-update-rule.md">Восстановление правила обновления устройств в Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Сброс правила обновления устройства с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **обновления устройства** .

4.  На странице **обновление устройства** выполните одно из следующих действий.
    
      - Чтобы сбросить одно правило, выберите правило, которое нужно сбросить.
    
      - Чтобы сбросить все правила, в меню **Правка** выберите пункт **выделить все**.
    
      - Чтобы сбросить все правила для одной фирменной символики, используйте меню столбец " **фирменная символика** ".

5.  Щелкните **действие**, а затем — **Отмена ожидающих обновлений**.
    
    <div>
    

    > [!TIP]  
    > Если вы уверены, что вы никогда не хотите развертывать правила обновления устройств, которые вы отменили, можете удалить их. Дополнительные сведения см. <A href="lync-server-2013-remove-a-device-update-rule.md">в разделе Удаление правила обновления устройств в Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Сброс правила обновления устройства с помощью командлетов Windows PowerShell

Кроме того, можно сбросить правила обновления устройств с помощью Windows PowerShell и командлета **Reset – CsDeviceUpdateRule** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Чтобы сбросить конкретное правило обновления устройства на сервере

  - Следующая команда сбрасывает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 на веб-сервере atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Сброс всех правил обновления устройств на сервере

  - Эта команда сбрасывает все правила обновления устройств на веб-сервере atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Сброс всех правил обновления устройств с определенной фирменной символикой

  - В этом примере выполняется сброс всех обновлений для всех устройств в Организации, имеющей торговую марку, равную корпорации Майкрософт:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Дополнительные сведения см. в разделе справки для командлета [Reset – CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>См. также


[Утверждение правила обновления устройств в Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

