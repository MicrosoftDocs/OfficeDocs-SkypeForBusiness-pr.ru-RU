---
title: 'Lync Server 2013: удаление существующей политики версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8915d828dd81c61e7d0c94f01fb7fdcb70e43a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525616"
---
# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Удаление существующей политики версий клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Если вы хотите удалить ранее настроенную политику версий клиентов, вы можете удалить ее из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>Удаление политик версий клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации для **политики версий клиентов** .

4.  На странице **Политика версий клиентов** выберите политику или политики версий клиентов, которые нужно удалить, нажмите кнопку **изменить**, а затем нажмите кнопку **Удалить**.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик версий клиентов с помощью командлетов Windows PowerShell

Политики версий клиентов можно удалить с помощью командлета **Remove – CsClientVersionPolicy** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>Удаление определенной политики версий клиентов

  - Эта команда удаляет политику версий клиентов, примененную к сайту Redmond:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>Удаление всех политик версий клиентов, примененных к области сайта

  - Эта команда удаляет все политики версий клиентов, настроенные на уровне сайта:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>Удаление политик версий клиентов, не включающих определенный агент пользователя

  - Эта команда удаляет все политики версий клиентов, которые не включают правило для агента пользователя Windows Phone Lync (Вплинк):
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

Дополнительные сведения см. в разделе справки для командлета [Remove – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

