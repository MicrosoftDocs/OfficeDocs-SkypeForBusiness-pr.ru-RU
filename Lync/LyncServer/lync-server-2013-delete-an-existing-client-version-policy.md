---
title: 'Lync Server 2013: удаление существующей политики версии клиента'
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
ms.openlocfilehash: 99936b495075034e6eae3f90e6dd95325bf6e2be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Удаление существующей политики версии клиента в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Если вы хотите удалить политику версии клиента, настроенную ранее, вы можете удалить ее из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>Удаление политик версий клиента с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Переход на **политику версии клиента** .

4.  На странице **политики версия клиента** выберите политику или политики, которые вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик версий клиента с помощью командлетов Windows PowerShell

Вы можете удалить политики версии клиента с помощью командлета **Remove-ксклиентверсионполици** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>Удаление политики для определенной версии клиента

  - Эта команда удаляет политику версии клиента, примененную к сайту Redmond.
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>Удаление всех политик версии клиента, примененных к области сайта

  - Эта команда удаляет все политики версии клиента, настроенные на уровне сайта.
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>Удаление политик версий клиентов, которые не включают определенный агент пользователя

  - И эта команда удаляет все политики версий клиентов, которые не включают правило для агента пользователя Windows Phone Lync (Вплинк):
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

