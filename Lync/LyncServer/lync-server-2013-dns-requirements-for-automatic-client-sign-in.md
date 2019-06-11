---
title: 'Lync Server 2013: требования DNS для автоматического входа клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Требования DNS для автоматического входа клиента в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-19_

В этом разделе объясняются DNS-записи, необходимые для автоматического входа в систему клиента. При развертывании серверов стандартных выпусков или пулов переднего плана можно настроить клиентские компьютеры на использование автоматического обнаружения для входа на соответствующий сервер Standard Edition или пул внешних интерфейсов. Если требуется, чтобы клиенты подключались к Lync Server 2013 вручную, вы можете пропустить этот раздел.

Для поддержки автоматического входа в клиент необходимо выполнить указанные ниже действия.

  - Назначение одного сервера или пула для распространения и проверки подлинности запросов на вход в клиент. Это может быть существующий сервер или пул в Организации, на котором размещаются пользователи, или вы можете назначить выделенный сервер или пул для этой цели, где нет пользователей. Для обеспечения высокой доступности мы рекомендуем указать пул переднего плана для этой функции.

  - Создание внутренней записи SRV DNS для поддержки автоматического входа клиента для этого сервера или пула.
    
    <div>
    

    > [!NOTE]  
    > В следующих требованиях к записям домен SIP относится к части URI SIP, назначенной пользователям. Например, если URI SIP имеет форму * @contoso. com, contoso.com — это домен SIP. Домен SIP часто отличается от внутреннего домена Active Directory. Организация также может поддерживать несколько доменов SIP.

    
    </div>

Чтобы включить автоматическую настройку для клиентов, необходимо создать внутреннюю запись DNS SRV, которая сопоставляет одну из указанных ниже записей с полным доменным именем (FQDN) переднего плана или сервера Standard Edition, который распространяет запросы на вход из Lync. клиентов

  - \_сипинтерналтлс. \_протокол TCP. \<домен\> — для внутренних TLS-подключений

Вам нужно только создать единственную запись SRV для пула переднего плана или сервера Standard Edition либо которая будет распространять запросы на вход.

В следующей таблице показаны некоторые примеры записей, необходимых для вымышленной компании Contoso, которая поддерживает домены SIP для contoso.com и retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Пример DNS-записей, необходимых для автоматического входа в клиент с несколькими доменами SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Полное доменное имя пула переднего плана, используемое для распространения запросов на вход</th>
<th>Домен SIP</th>
<th>SRV-запись DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>SRV-запись для домена _сипинтерналтлс. _tcp. contoso. com по порту 5061, сопоставленная с pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>SRV-запись для домена _сипинтерналтлс. _tcp. Retail. contoso. com по порту 5061, сопоставленная с pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> По умолчанию запросы DNS-записей соответствуют строгому сопоставлению доменных имен между доменом в имени пользователя и записи SRV. Если вы предпочитаете, чтобы клиентские DNS-запросы вместо этого использовали соответствующие суффиксы, вы можете настроить групповую политику Дисаблестриктднснаминг. Подробные сведения можно найти <A href="lync-server-2013-planning-for-clients-and-devices.md">в разделе Планирование клиентов и устройств в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Пример сертификатов и записей DNS, необходимых для автоматического входа в клиент

В этом примере используются те же примеры имен из приведенной выше таблицы. Организация Contoso поддерживает домены SIP для contoso.com и retail.contoso.com, а все его пользователи имеют URI SIP в одной из следующих форм:

  - \<User\>@retail. contoso.com

  - \<User\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

