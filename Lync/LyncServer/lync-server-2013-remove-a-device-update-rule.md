---
title: 'Lync Server 2013: Удаление правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6db307572d72d11b73baa723405fd32da46b7c75
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Удаление правила обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

При удалении правила обновления устройства он удаляется навсегда из очереди обновления устройства.

Удаление правила отличается от удаления обновления с устройств в вашем развертывании или на тестовых устройствах. Чтобы удалить одобренное обновление из развертывания, *восстановите* правило обновления устройства. Для получения дополнительных сведений см. [Восстановление правила обновления устройств в Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Чтобы удалить обновление, которое не было утверждено на тестовых устройствах, необходимо *сбросить* его. Подробнее: " [Сброс правила обновления устройства" в Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Правило обновления устройства можно удалить с помощью панели управления Lync Server или Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Удаление правил обновления устройств с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **обновления устройства** .

4.  На странице **обновление устройства** выполните одно из следующих действий.
    
      - Чтобы удалить одно правило, выберите правило, которое нужно удалить.
    
      - Чтобы удалить все правила, щелкните меню **Правка** и выберите команду **выбрать все**.

5.  Щелкните **Изменить** и **Удалить**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Удаление правил обновления устройств с помощью командлетов Windows PowerShell

Правила обновления устройств также можно удалить с помощью Windows PowerShell и командлета **Remove – CsDeviceUpdateRule** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Удаление правила обновления одного устройства с сервера

  - Следующая команда удаляет правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 на веб-сервере в atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Удаление всех правил обновления устройств с сервера

  - Эта команда удаляет все правила обновления устройств с веб-сервера в atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Дополнительные сведения см. в разделе справки для командлета [Remove – CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

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

