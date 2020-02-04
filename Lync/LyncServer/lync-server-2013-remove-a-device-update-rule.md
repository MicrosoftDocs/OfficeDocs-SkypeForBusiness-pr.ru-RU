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
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Удаление правила обновления устройства в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

При удалении правила обновления устройства все равно удаляются из очереди обновления устройства.

Удаление правила отличается от удаления обновления с устройств в вашем развертывании или с тестовых устройств. Чтобы удалить одобренное обновление из развертывания, *восстановите* правило обновления устройства. Подробности можно найти [в разделе Восстановление правила обновления устройства в Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Для удаления обновления, которое вы еще не утвердили на тестовых устройствах, вы можете *сбросить* его. Подробности можно найти [в разделе Сброс правила обновления устройства в Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Вы можете удалить правило обновления устройства с помощью панели управления Lync Server или Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Удаление правил обновления устройства с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **обновлению устройства** .

4.  На странице **обновление устройства** выполните одно из указанных ниже действий.
    
      - Чтобы удалить одно правило, выберите правило, которое вы хотите удалить.
    
      - Чтобы удалить все правила, откройте меню **Правка** и выберите команду **выделить все**.

5.  Нажмите **Изменить**, затем кнопку **Удалить**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Удаление правил обновления устройства с помощью командлетов Windows PowerShell

Кроме того, вы можете удалить правила обновления устройства с помощью Windows PowerShell и командлета **Remove-ксдевицеупдатеруле** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Удаление правила обновления отдельного устройства с сервера

  - Следующая команда удаляет правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 с веб-сервера в atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Удаление всех правил обновления устройства с сервера

  - Эта команда удаляет все правила обновления устройства на веб-сервере atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксдевицеупдатеруле](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

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

