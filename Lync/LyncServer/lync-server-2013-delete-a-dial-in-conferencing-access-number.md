---
title: 'Lync Server 2013: Удаление номера доступа к конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5d0e51486ed6dca7c9ac17a991b0154c2f1135
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Удаление номера доступа к конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Выполните следующие действия, чтобы удалить номер доступа к конференции с телефонным подключением.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Удаление номера доступа к конференции с телефонным подключением

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.

4.  На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем нажмите **Удалить**.

5.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Удаление номеров доступа к конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell

Номера доступа к конференц-связи с телефонным подключением можно удалить с помощью Windows PowerShell и командлета **Remove-CsDialInConferencingAccessNumber** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Удаление определенного номера доступа к конференц-связи с телефонным подключением

  - Эта команда служит для удаления номера доступа к конференц-связи с телефонным подключением с идентификатором sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Удаление всех номеров доступа к конференц-связи с телефонным подключением, назначенных определенному региону

  - Эта команда служит для удаления всех номеров доступа к конференц-связи с телефонным подключением, связанных с регионом "Северо-запад":
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Удаление номеров доступа к конференц-связи с телефонным подключением на основе основного языка

  - Эта команда удаляет все номера доступа к конференц-связи с телефонным подключением, где основной язык — итальянский:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

