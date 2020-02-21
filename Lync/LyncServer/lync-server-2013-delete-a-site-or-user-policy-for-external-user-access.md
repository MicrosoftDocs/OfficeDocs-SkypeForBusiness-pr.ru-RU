---
title: 'Lync Server 2013: Удаление политики сайта или пользователя для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b7cadad0e914104a8392d1f6b36167780a2b759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Вы можете удалить любую политику сайта или пользователя, указанную в панели управления Lync Server на странице " **Политика внешнего доступа** ". При удалении глобальной политики она на самом деле не удаляется, а восстанавливаются параметры по умолчанию, не включающие поддержку доступа внешних пользователей. Дополнительные сведения о сбросе глобальной политики приведены в статье [Reset The Global Policy for External User Access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Удаление политика узла или пользователя для доступа внешних пользователей

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Щелкните **Доступ для внешних пользователей** и выберите **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните политику узла или пользователя, которую нужно удалить, нажмите кнопку **Изменить** и затем нажмите **Удалить**.

5.  При отображении запроса на подтверждение нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кодов с помощью командлетов Windows PowerShell

Политики внешнего доступа можно удалить с помощью Windows PowerShell и командлета Remove – CsExternalAccessPolicy. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>Удаление определенной политики внешнего доступа

  - Эта команда удаляет политику внешнего доступа для узла Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Удаление всех политик внешнего доступа, примененных к области "на пользователя"

  - Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех политик внешнего доступа, для которых отключен доступ извне пользователя

  - Эта команда удаляет все политики внешнего доступа, в который доступ внешних пользователей отключен:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

