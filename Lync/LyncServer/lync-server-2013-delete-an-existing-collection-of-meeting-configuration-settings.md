---
title: Удаление существующей коллекции параметров конфигурации собраний
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b649efc1241522f583e438690ebdf2035e424344
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации собраний в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Можно удалить конфигурацию сайта или пользователя. Глобальную конфигурацию невозможно удалить. При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию.

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>Удаление конфигурации собрания для сайта или пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Conferencing** (Конференц-связь), а затем **Meeting Configuration** (Конфигурация собрания).

4.  В списке конфигураций собрания выберите конфигурацию сайта или пула, которую необходимо удалить, нажмите кнопку **изменить**, а затем нажмите кнопку **Удалить**.

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации собраний с помощью командлетов Windows PowerShell

Параметры собрания можно удалить с помощью Windows PowerShell и командлета Remove – CsMeetingConfiguration. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>Удаление указанной коллекции параметров конфигурации собраний

  - Эта команда удаляет параметры конфигурации собрания, примененные к сайту Redmond:
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации собрания, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации собрания, примененные к области сайта:
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>Удаление всех параметров конфигурации собраний, которые допускают анонимных пользователей по умолчанию

  - Эта команда удаляет все параметры, которые допускают анонимных пользователей по умолчанию:
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

