---
title: 'Lync Server 2013: Проверка конфигурации магистрали по номеру телефона'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b67831b6dbcd7dae12f9b19dd71f2512a8807189
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Проверка конфигурации магистрали по номеру телефона в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-20_


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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsTrunkConfiguration. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Магистральные линии SIP соединяют внутреннюю корпоративную сеть Lync Server с одним из следующих способов:

  - Телефонная сеть общего пользования (PSTN).

  - УАТС (IP-открытая ветвь).

  - Пограничный контроллер сеансов (SBC).

Командлет Test-CsTrunkConfiguration проверяет, может ли телефонный номер (набираемый пользователем) быть преобразован в сеть E. 164 и маршрутизироваться по указанной магистральной линии SIP.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Для запуска командлета Test-CsTrunkConfiguration сначала необходимо использовать командлет Get-CsTrunkConfiguration, чтобы получить экземпляр параметров конфигурации магистральной сети SIP; Затем этот экземпляр передается в командлет Test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Выполнение Test-CsTrunkConfiguration без первого запуска Get-CsTrunkConfiguration не будет работать. Например, эта команда завершится с ошибками, не возвращая никаких данных:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Если у вас есть несколько семейств параметров конфигурации магистрали SIP, вы можете использовать следующую команду для проверки каждой из них с одним и тем же номером телефона:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Дополнительные сведения можно найти в справочной документации по командлету Test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsTrunkConfiguration может позвонить на набранный номер, переведенный номер телефона (в формате E. 164) и правило, используемое для перевода этого номера телефона, будут отображаться на экране.

Транслатеднумбер Матчингруле

\---------------- ------------

\+12065551219 Global/Redmond

Если проверка завершилась неудачно, Test-CsTrunkConfiguration возвратит пустые значения свойств:

Транслатеднумбер Матчингруле

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если Test-CsTrunkConfiguration не возвращает соответствующее значение, которое обычно означает, что тестируемые параметры конфигурации магистрали не имеют правила преобразования исходящих вызовов для преобразования набранных номеров в формат E. 164. Чтобы получить правила преобразования, назначенные для коллекции параметров конфигурации магистрали, можно использовать следующий синтаксис:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Для каждого правила преобразования возвращаются сведения, аналогичные приведенным ниже.

Описание: номера телефонов без кода страны или города.

Шаблон: ^\\+ (\\d\*) $

`Translation : $1`

Name: Ноареакоде

На этом шаге необходимо проверить значение свойства Pattern (это строка [регулярного выражения](http://go.microsoft.com/fwlink/?linkid=400464) ), чтобы проверить, настроены ли какие-либо правила преобразования для обработки набора номера. В противном случае необходимо изменить одно из существующих правил (Set-CsOutboundTranslationRule) или использовать командлет New-CsOutboundTranslationRule для добавления нового правила в коллекцию.

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

