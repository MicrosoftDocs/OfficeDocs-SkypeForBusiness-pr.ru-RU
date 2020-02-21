---
title: 'Lync Server 2013: требования к DNS для автоматического входа клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e49d50173439e36bd5bb7f35f668837fe04b46b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Требования DNS для автоматического входа клиентов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-19_

В данном разделе описываются записи службы доменных имен (DNS), необходимые для автоматического входа клиентов. При развертывании серверов Standard Edition или интерфейсных пулов вы можете настроить клиентов на использование автоматического обнаружения для входа на соответствующий сервер Standard Edition или в интерфейсный пул. Если вы планируете, чтобы клиенты могли подключаться к Lync Server 2013 вручную, вы можете пропустить этот раздел.

Чтобы обеспечить поддержку автоматического входа клиентов, вам следует выполнить следующие действия:

  - Назначить отдельный сервер или пул для распространения и проверки подлинности запросов входа от клиентов. Это может быть существующий в организации сервер или пул с размещенными пользователями, либо вы можете назначить для этой цели выделенный сервер или пул без размещенных пользователей. Для обеспечения высокой доступности мы рекомендуем назначить для этого интерфейсный пул.

  - Создать внутреннюю DNS-запись SRV, чтобы обеспечить поддержку автоматического входа клиентов для этого сервера или пула.
    
    <div>
    

    > [!NOTE]  
    > В приведенных ниже требованиях к записи домен SIP относится к той части кодов URI SIP, назначенных пользователям, которая обозначает узел. Например, если коды URI SIP имеют форму *@contoso.com, то contoso.com — это домен SIP. Этот домен SIP часто отличается от внутреннего домена Active Directory. Кроме того, организация может поддерживать несколько доменов SIP.

    
    </div>

Чтобы включить автоматическую настройку клиентов, необходимо создать внутреннюю DNS-запись SRV, которая сопоставляет одну из следующих записей с полным доменным именем (FQDN) интерфейсного пула или сервера Standard Edition, который распространяет запросы на вход из Lync. заказчика

  - \_сипинтерналтлс. \_TCP. \<домен\> — для внутренних подключений TLS

Вам требуется только создать одну запись SRV для интерфейсного пула или сервера Standard Edition, который будет распространять запросы на вход.

В следующей таблице приведено несколько примеров записей, требуемых для вымышленной компании Contoso, осуществляющей поддержку доменов SIP contoso.com и retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Пример DNS-записей, необходимых для автоматического входа клиентов с несколькими доменами SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Полное доменное имя интерфейсного пула, используемого для распространения запросов на вход</th>
<th>Домен SIP</th>
<th>DNS-запись SRV</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Запись SRV для домена _sipinternaltls._tcp.contoso.com через порт 5061, которая сопоставлена с pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Запись SRV для домена _sipinternaltls._tcp.retail.contoso.com через порт 5061, которая сопоставлена с pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> По умолчанию запросы для DNS-записей придерживаются строгого совпадения имен доменов между доменом в имени пользователя и в записи SRV. Если вы предпочитаете, чтобы DNS-запросы клиентов вместо этого использовали совпадение суффиксов, то можете настроить групповую политику DisableStrictDNSNaming. Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-clients-and-devices.md">планирование для клиентов и устройств в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Пример сертификатов и DNS-записей, необходимых для автоматического входа клиентов

В данном примере используются образцы имен из предыдущей таблицы. Организация Contoso поддерживает домены SIP contoso.com и retail.contoso.com, и все ее пользователи имеют код URI SIP в одной из следующих форм:

  - \<пользователь\>@retail. contoso.com

  - \<пользователь\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

