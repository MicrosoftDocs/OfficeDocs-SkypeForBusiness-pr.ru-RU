---
title: 'Lync Server 2013: сброс глобальной политики для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Сброс глобальной политики для доступа внешних пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Вы не можете полностью удалить глобальную политику. Параметр " **Удалить** " в глобальной политике используется только для сброса глобальной политики в параметры по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Восстановление параметров глобальной политики по умолчанию

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **внешний пользовательский доступ**и нажмите кнопку **Политика внешних доступа**.

4.  На вкладке **внешняя политика доступа** выберите глобальную политику, нажмите кнопку **изменить**, а затем выберите команду **Удалить**.

5.  Когда появится запрос на подтверждение удаления, нажмите кнопку **ОК**. В верхней части страницы появится сообщение о том, что была выполнена сброс глобальной политики.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Сброс глобальной политики внешнего доступа с помощью командлетов Windows PowerShell

Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и командлета Remove-Ксекстерналакцессполици. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Сброс глобальной политики внешнего доступа

  - Эта команда сбрасывает глобальную политику внешнего доступа:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксекстерналакцессполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

