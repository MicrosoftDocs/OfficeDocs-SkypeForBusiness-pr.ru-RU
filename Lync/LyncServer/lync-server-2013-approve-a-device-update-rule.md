---
title: 'Lync Server 2013: утверждение правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5112f4be1f6c192d78d3b87b21094c2b04c4df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504917"
---
# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Утверждение правила обновления устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

После импорта правила обновления устройств оно устанавливается на тестовые устройства. Если проверка прошла успешно, и вы хотите развернуть обновление в Организации, утвердите его с помощью панели управления Lync Server или Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Утверждение правила обновления устройства с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На странице **обновление устройства** выполните одно из следующих действий.
    
      - Чтобы утвердить одно правило, выберите это правило.
    
      - Чтобы утвердить все правила, нажмите кнопку **изменить**, а затем выберите пункт **выбрать все**.

4.  Щелкните **действие**, а затем нажмите кнопку **утвердить**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Утверждение правила обновления устройства с помощью командлетов Windows PowerShell

Правила обновления устройств также могут быть утверждены с помощью Windows PowerShell и командлета **утвержденного CsDeviceUpdateRule** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Утверждение правила обновления одного устройства

  - Следующая команда утверждает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9, обнаруженное на веб-сервере atl-cs-001.litwareinc.com:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Утверждение нескольких правил обновления устройств

  - Эта команда утверждает все правила обновления устройств для устройств с фирменной символикой Майкрософт:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [утверждений CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>См. также


[Импорт правил обновления устройств в Lync Server 2013](lync-server-2013-import-device-update-rules.md)  
[Восстановление правила обновления устройств в Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

