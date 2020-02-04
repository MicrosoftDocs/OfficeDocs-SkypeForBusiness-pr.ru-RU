---
title: 'Lync Server 2013: удаление сайта или пользовательской политики для доступа внешних пользователей'
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
ms.openlocfilehash: b928fcb1347fdbc89099a5b0dc649deefffa19e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Вы можете удалить политику сайта или пользователя, указанную на панели управления Lync Server на странице " **политика внешней доступа** ". При удалении глобальной политики фактически она не удаляется, но только восстанавливает параметры, заданные по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей. Дополнительные сведения о сбросе глобальной политики можно найти [в разделе Восстановление глобальной политики доступа внешних пользователей в Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Удаление политики сайта или пользователя для доступа внешних пользователей

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Выберите **внешний доступ пользователей**и нажмите кнопку **Политика внешних доступа**.

4.  На вкладке **внешняя политика доступа** выберите сайт или политику пользователей, которые вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.

5.  Когда появится запрос на подтверждение удаления, нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик закрепления с помощью командлетов Windows PowerShell

Внешние политики доступа можно удалить с помощью Windows PowerShell и командлета Remove-Ксекстерналакцессполици. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>Удаление особой политики внешнего доступа

  - Эта команда удаляет политику внешней политики доступа, примененную к сайту Redmond.
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Чтобы удалить все внешние политики доступа, примененные к области "на пользователя"

  - Эта команда удаляет все политики внешней доступа, настроенные для области "на пользователя".
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех внешних политик доступа, для которых отключен доступ за пределами пользователей

  - Эта команда удаляет все внешние политики доступа, в которых отключен доступ за пределы пользователей.
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксекстерналакцессполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

