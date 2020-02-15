---
title: 'Lync Server 2013: Проверка серверных сертификатов Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebdbfdc4ed0f88d78fc78037a3522c73bd220270
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Проверка серверных сертификатов Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Monthly Channel</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Get – CsCertificate. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Get – CsCertificate позволяет получить сведения о каждом из сертификатов Lync Server. Это особенно важно, так как сертификаты имеют встроенную дату истечения срока действия. Например, срок действия сертификатов, выданных частными, обычно истечет через 12 месяцев. Если какой-либо из ваших сертификатов Lync Server истечет, все функции будут потеряны до тех пор, пока сертификат не будет обновлен или заменен.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы получить сведения о каждом из ваших сертификатов Lync Server, выполните следующую команду:

`Get-CsCertificate`

Вы также можете отфильтровать сведения о сертификате возврата на основе даты истечения срока действия. Например, эта команда позволяет ограничить возвращаемые данные сертификатами, срок действия которых истечет (нельзя использовать после 1 июня 2014 г.).

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Для получения дополнительных сведений обратитесь к справочной документации по командлету Get – CsCertificate.

Обратите внимание, что несмотря на то, что командлет Test-Ксцертификатеконфигуратион существует, он не очень полезен администраторам. (Вместо этого этот командлет используется в основном мастером сертификатов.) Несмотря на то, что командлет работает, возвращаемые им данные имеют минимальное значение, как показано в следующем примере вывода:

Использование отпечатков

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 по умолчанию

</div>

<div>

## <a name="reviewing-the-output"></a>Просмотр выходных данных

Командлет Get – CsCertificate возвращает сведения, аналогичные приведенным ниже, для каждого сертификата сервера Lync Server.

Издатель: CN = Фабрикамка

NotAfter: 12/28/2015 3:35:41 PM

Свойстве NotBefore: 1/2/2014 12:49:37 PM

SerialNumber: 611BB01200000000000C

Subject: CN = LYNC — SE.fabrikam.com

Алтернативенамес: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Отпечаток: A9D51A2911C74FABFF7F2A8A994B20857D399107

Использовать: по умолчанию

Как правило, основные проблемы, связанные с сертификатами Lync Server, включают даты и время, например время, когда сертификаты вступают в силу (свойстве NotBefore) или когда истечет срок их действия (NotAfter). Так как эти значения дат и времени важны, вы можете ограничить возвращаемые данные сведениями, такими как использование сертификата, серийный номер сертификата и Дата окончания срока действия сертификата; После этого вы сможете быстро просмотреть все сертификаты и срок их действия. Чтобы получить только эти сведения, используйте команду вместе с параметрами, как показано ниже.

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Эта команда возвращает данные, аналогичные приведенным ниже, при этом сертификаты сортируются в порядке их истечения срока действия.

Использование NotAfter SerialNumber

\--- ------------ --------

611BB01200000000000C по умолчанию 12/28/2015 3:35:41 PM

Вебсервицесинтерал 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

Если у вас возникнут проблемы с сертификатом, вам может потребоваться просмотреть Алтернативенамес, настроенный для сертификата. На первый взгляд кажется, что проблема. По умолчанию, в зависимости от размера окна консоли, Get – CsCertificate может не отображать все имена:

Алтернативенамес: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. фабрика...}

Чтобы просмотреть все альтернативные имена, назначенные для сертификата, используйте команду, аналогичную следующей:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Должны отображаться все альтернативные имена сертификата:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

