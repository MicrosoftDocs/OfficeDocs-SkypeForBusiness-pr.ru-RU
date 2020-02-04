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
ms.openlocfilehash: 36a85ed29f6bf4838428af302904d80a2f792388
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Сброс правила обновления устройства в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Если вы не хотите, чтобы обновление работало на тестовом устройстве, вы можете сбросить правило обновления устройства, которое удаляет состояние ожидания правила и удаление обновления с тестовых устройств.

Вы можете удалить правило обновления устройства с помощью панели управления Lync Server или Windows PowerShell.

<div>


> [!NOTE]  
> Чтобы удалить правило, которое вы уже утвердили (то есть выпало из него), восстановите его. Подробности можно найти <A href="lync-server-2013-restore-a-device-update-rule.md">в разделе Восстановление правила обновления устройства в Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Сброс правила обновления устройства с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **обновлению устройства** .

4.  На странице **обновление устройства** выполните одно из указанных ниже действий.
    
      - Чтобы сбросить одно правило, выберите правило, которое вы хотите сбросить.
    
      - Чтобы сбросить все правила, в меню **Правка** выберите команду **выделить все**.
    
      - Чтобы сбросить все правила для одной торговой марки, используйте меню столбец " **бренд** ".

5.  Нажмите кнопку **действие**и выберите пункт **отменить ожидающие обновления**.
    
    <div>
    

    > [!TIP]  
    > Если вы уверены в том, что вы не хотите выгрузить правила обновления устройства, которые вы отменили, возможно, потребуется удалить их. Подробности можно найти <A href="lync-server-2013-remove-a-device-update-rule.md">в разделе Удаление правила обновления устройства в Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Сброс правила обновления устройства с помощью командлетов Windows PowerShell

Кроме того, вы можете сбросить правила обновления устройства с помощью Windows PowerShell и командлета **Reset-ксдевицеупдатеруле** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Сброс правила обновления для определенного устройства на сервере

  - Следующая команда сбрасывает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 на веб-сервере atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Сброс всех правил обновления устройства на сервере

  - Эта команда сбрасывает все правила обновления устройства на веб-сервере atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Сброс всех правил обновления устройства, для которых определена фирменная символика

  - В этом примере все обновления для устройств, на которых установлен Межфирменная символика (Майкрософт), сбрасываются.
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Reset-ксдевицеупдатеруле](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>См. также


[Утверждение правила обновления устройства в Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

