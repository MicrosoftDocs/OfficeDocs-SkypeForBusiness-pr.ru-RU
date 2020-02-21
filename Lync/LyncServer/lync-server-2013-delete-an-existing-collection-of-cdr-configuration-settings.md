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
ms.openlocfilehash: e1fdfe0829f33061b9af25a6478435964545570d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации CDR в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.

При установке Microsoft Lync Server 2013 создается одна глобальная коллекция параметров конфигурации CDR. Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам. Параметры, настроенные на уровне сайта, переопределяют глобальные параметры. Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.

Обратите внимание, что глобальные параметры также можно "удалить", однако на самом деле они не удаляются. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, в коллекции параметров конфигурации CDR по умолчанию очистка включена. Предположим, что глобальная коллекция изменена и очистка отключена. Если удалить глобальные параметры, все свойства будут сброшены на значения по умолчанию и очистка снова будет включена.

Параметры конфигурации CDR можно удалить с помощью панели управления Lync Server или командлета [Remove – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Удаление параметров конфигурации CDR с помощью панели управления Lync Server

1.  В панели управления Lync Server щелкните **мониторинг и архивация**.

2.  На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, щелкните первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.

3.  Щелкните **Изменить** и **Удалить**.

4.  В диалоговом окне "Панель управления Lync Server" нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации CDR с помощью командлетов Windows PowerShell

Параметры конфигурации регистрации вызовов можно удалить с помощью Windows PowerShell и командлета **Remove – CsCdrConfiguration** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

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

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

