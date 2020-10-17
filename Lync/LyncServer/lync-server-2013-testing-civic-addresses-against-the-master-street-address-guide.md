---
title: Проверка административного адреса для основного почтового руководства по адресу
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d03647df3752860c114a16967a3bea5271a89d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527816"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Тестирование административных адресов для главного почтового руководства по адресу в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневное</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsRegistration. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsLisCivicAddress используется для проверки расположений, добавленных в базу данных службы сведений о местоположении (LIS). Командлет выполняет сравнение расположений с местоположениями в главном руководстве по адресам (MSAG), которые относятся к поставщику маршрутизации сети E9-1-1. Если у вас нет поставщика сетевой маршрутизации или если поставщик недоступен, то тесты завершатся с ошибками.

Если вы добавите необязательный параметр переключателя Упдатевалидатионстатус к команде, то для соответствующего свойства базы данных Мсагвалид будет задано значение true для каждого адреса, пройденного тест.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsLisCivicAddress можно использовать для проверки отдельных адресов или для проверки нескольких адресов. Например, эта команда проверяет один адрес, расположенный в Редмонде, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

При сравнении эта команда тестирует все адреса, которые в настоящее время находятся в базе данных LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Test-CsLisCivicAddress будет сообщать об успехе или неудаче для указанных адресов. Если не удается найти адрес или не удается связаться с поставщиком услуг, тест адреса завершится ошибкой.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsLisCivicAddress:

  - Поставщик услуг LIS может быть недоступен. Вы можете получить URL-адрес поставщика службы LIS, выполнив командлет Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    После этого вы можете проверить связь с этим URL-адресом, чтобы проверить, доступен ли поставщик услуг.

</div>

</div>

<span> </span>

</div>

</div>

</div>

