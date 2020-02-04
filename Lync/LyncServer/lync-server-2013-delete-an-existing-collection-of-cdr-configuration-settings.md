---
title: 'Lync Server 2013: удаление существующей коллекции параметров конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50df73d59c588094693009ab4c84f2a7809ba5f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации CDR в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.

При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации CDR. Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам. Параметры, настроенные на уровне сайта, переопределяют глобальные параметры. Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.

Обратите внимание, что глобальные параметры также можно "удалить", однако на самом деле они не удаляются. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, в коллекции параметров конфигурации CDR по умолчанию очистка включена. Предположим, что глобальная коллекция изменена и очистка отключена. Если удалить глобальные параметры, все свойства будут сброшены на значения по умолчанию и очистка снова будет включена.

Вы можете удалить параметры конфигурации CDR с помощью панели управления Lync Server или командлета [Remove-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Удаление параметров конфигурации CDR с помощью панели управления Lync Server

1.  На панели управления Lync Server щелкните элемент **мониторинг и архивация**.

2.  На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, выберите первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.

3.  Нажмите **Изменить**, затем кнопку **Удалить**.

4.  В диалоговом окне "Панель управления Lync Server" нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации CDR с помощью командлетов Windows PowerShell

Вы можете удалить параметры конфигурации для записи сведений о вызовах с помощью Windows PowerShell и командлета **Remove-кскдрконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Удаление определенной коллекции параметров конфигурации CDR

  - Эта команда удаляет параметры конфигурации CDR, которые относятся к сайту Redmond:
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации CDR, применяемых на уровне сайта

  - Эта команда удаляет все параметры конфигурации CDR, применяемые на уровне сайта:
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Удаление всех параметров конфигурации CDR, которые отключают регистрацию вызовов

  - Эта команда удаляет все параметры конфигурации CDR, которые отключают регистрацию вызовов:
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

