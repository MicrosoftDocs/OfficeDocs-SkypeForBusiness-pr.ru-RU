---
title: Удаление существующей коллекции параметров конфигурации версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a8925037643028e02975c4145e1e2593bc6608
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514656"
---
# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации версий клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Если вы хотите удалить параметры конфигурации клиента, ранее настроенные для сайта, можно удалить параметры из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>Удаление параметров конфигурации клиента с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .

4.  Выберите сайт, нажмите кнопку **изменить**, выберите команду **Удалить**, а затем нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации версий клиентов с помощью командлетов Windows PowerShell

Вы можете удалить параметры конфигурации версий клиентов с помощью командлета **Remove – CsClientVersionConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>Удаление указанной коллекции параметров конфигурации версии клиента

  - Следующая команда удаляет параметры конфигурации версии клиента, применяемые к сайту Redmond:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации версий клиентов, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации версий клиентов, настроенные на уровне сайта:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>Удаление всех параметров конфигурации версии клиента на основе значения свойства DefaultAction

  - Эта команда удаляет все параметры конфигурации версий клиентов, для которых в качестве действия по умолчанию задано значение "Block":
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

Дополнительные сведения см. в разделе справки для командлета [Remove – CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

