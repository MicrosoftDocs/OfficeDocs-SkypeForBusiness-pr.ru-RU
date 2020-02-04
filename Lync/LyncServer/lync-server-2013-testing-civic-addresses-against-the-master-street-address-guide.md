---
title: Тестирование многоадресных адресов в главном руководстве почтового адреса
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
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Проверка многоадресных адресов в главном руководстве почтового адреса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневно</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксрегистратион. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-КслисЦивикаддресс используется для проверки местоположений, добавленных в базу данных службы сведений о расположении (LIS). Командлет выполняет сравнение расположений с расположениями в главном руководстве по адресу (МСАГ), которые относятся к поставщику сетевой маршрутизации E9-1-1. Если у вас нет провайдера сетевой маршрутизации или если поставщик недоступен, тесты завершатся сбоем.

Если вы добавите в команду необязательный параметр ключа Упдатевалидатионстатус, для соответствующего свойства базы данных Мсагвалид будет задано значение "true" для каждого адреса, продающего проверку.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-КслисЦивикаддресс можно использовать для проверки отдельных адресов или проверки нескольких адресов. Например, эта команда проверяет один адрес, указанный в Редмонде, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

По сравнению с этой командой проверяются все адреса, находящиеся в базе данных LIS.

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксрегистратион](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Тест-КслисЦивикаддресс сообщит об успешном завершении или сбое для указанных адресов. Если адрес не удается найти или не удается связаться с поставщиком услуг, проверка адреса завершится сбоем.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-КслисЦивикаддресс:

  - Поставщик услуг LIS может быть недоступен. Вы можете получить URL-адрес поставщика услуг LIS, выполнив командлет Get-Кслисконфигуратион:
    
        Get-CsLisConfiguration 
    
    Затем вы можете проверить связь с этим URL-адресом, чтобы убедиться, что поставщик услуг доступен.

</div>

</div>

<span> </span>

</div>

</div>

</div>

