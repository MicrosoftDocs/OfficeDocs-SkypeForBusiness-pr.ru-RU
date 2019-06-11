---
title: 'Lync Server 2013: Проверка серверных сертификатов Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Проверка серверных сертификатов Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежемесячно</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Get-Ксцертификате. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Get-Ксцертификате позволяет получить сведения о каждом из сертификатов сервера Lync Server. Это особенно важно, так как у сертификатов есть встроенная Дата окончания срока действия. Например, просроченные сертификаты, как правило, истекает через 12 месяцев. Если срок действия одного из сертификатов вашего сервера Lync Server истек, то все возможности будут потеряны до тех пор, пока сертификат не будет обновлен или заменен.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы получить сведения о каждом из ваших сертификатов сервера Lync Server, выполните следующую команду:

`Get-CsCertificate`

Вы также можете отфильтровать сведения о сертификате возврата на основе даты окончания срока действия. Например, эта команда ограничивает возвращаемые данные сертификатами с истекшим сроком действия (не может использоваться после) июня 1, 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Дополнительные сведения можно найти в справочной документации по командлету Get-Ксцертификате.

Обратите внимание, что несмотря на то, что командлет Test-Ксцертификатеконфигуратион существует, он не очень полезен администраторам. (Вместо этого этот командлет используется преимущественно мастером сертификатов.) Несмотря на то что командлет работает, возвращаемые им данные имеют минимальное значение, как показано в следующем примере вывода:

Использование отпечатка

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 по умолчанию

</div>

<div>

## <a name="reviewing-the-output"></a>Просмотр результатов

Командлет Get-Ксцертификате возвращает сведения о каждом из сертификатов сервера Lync Server, аналогичные приведенным ниже.

Issuer: CN = Фабрикамка

Нотафтер: 12/28/2015 3:35:41 PM

Нотбефоре: 1/2/2014 12:49:37 PM

SerialNumber: 611BB01200000000000C

Тема: CN = LYNC-SE.fabrikam.com

Алтернативенамес: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Отпечаток: A9D51A2911C74FABFF7F2A8A994B20857D399107

Использование: Default

Как правило, основные проблемы, связанные с сертификатами Lync Server, включают в себя даты и время, например время вступления в силу сертификатов (Нотбефоре) или срок их действия (Нотафтер). Поскольку эти значения даты и времени настолько важны, возможно, потребуется ограничить возвращаемые данные такими данными, как использование сертификата, серийный номер сертификата и Дата окончания срока действия сертификата; После этого вы сможете быстро просмотреть все сертификаты и срок их действия. Чтобы вернуть эти данные, используйте команду вместе с параметрами, как показано ниже.

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Эта команда возвращает данные, похожие на приведенные ниже, при этом сертификаты сортируются в порядке их истечения срока действия.

Использование Нотафтер SerialNumber

\--- ------------ --------

611BB01200000000000C по умолчанию 12/28/2015 3:35:41 PM

Вебсервицесинтерал 32980AA20BBB20000191 02/15/2016 2:16:12 PM

Вебсервицесекстернал 0451B012003872651A0C 02/20/2016 7:11:58 AM

Если у вас возникли проблемы с сертификатом, возможно, вы захотите просмотреть Алтернативенамес, настроенный для сертификата. На первый взгляд, это похоже на проблему. По умолчанию, в зависимости от размера окна консоли, Get-Ксцертификате может не отображать все имена:

Алтернативенамес: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. фабрика...}

Чтобы просмотреть все альтернативные имена, назначенные сертификату, используйте следующую команду:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Для отображения всех альтернативных имен в сертификате:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

