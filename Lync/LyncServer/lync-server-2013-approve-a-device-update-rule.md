---
title: 'Lync Server 2013: утверждение правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Утверждение правила обновления устройства в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

После импорта правила обновления устройства оно будет установлено на тестовых устройствах. Если тестирование прошло успешно и вы хотите развернуть обновление в своей организации, утвердите его с помощью панели управления Lync Server или Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Утверждение правила обновления устройства с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На странице **обновление устройства** выполните одно из указанных ниже действий.
    
      - Чтобы утвердить одно правило, выберите это правило.
    
      - Чтобы утвердить все правила, нажмите кнопку **изменить**, а затем выберите команду **выделить все**.

4.  Нажмите кнопку **действие**и выберите пункт **утвердить**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Утверждение правила обновления устройства с помощью командлетов Windows PowerShell

Вы также можете утвердить правила обновления устройства с помощью Windows PowerShell и командлета **утвержденных ксдевицеупдатеруле** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Утверждение отдельного правила обновления устройства

  - Следующая команда утверждает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9, обнаруженное на веб-сервере atl-cs-001.litwareinc.com:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Утверждение нескольких правил обновления устройства

  - Эта команда утверждает все правила обновления устройств для устройств с фирменной символикой Майкрософт:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Дополнительные сведения можно найти в разделе справки по командлету [утвержденных ксдевицеупдатеруле](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>См. также


[Импорт правил обновления устройств в Lync Server 2013](lync-server-2013-import-device-update-rules.md)  
[Восстановление правила обновления устройства в Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

