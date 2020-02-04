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
ms.openlocfilehash: 7932e4cb7a7a9d74b945dcd60c2a1211ca5af694
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Проверка конфигурации магистрали по номеру телефона в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-20_


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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsTrunkConfiguration. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Магистральные магистрали SIP соединяют внутреннюю корпоративную сеть Lync Server с одним из указанных ниже способов.

  - Коммутируемая коммутируемая телефонная сеть (КТСОП).

  - IP-адрес общедоступной ветви (УАТС).

  - Контроллер границ сеанса (SBC).

Командлет Test-CsTrunkConfiguration подтверждает, что номер телефона (установленный пользователем) может быть преобразован в сеть E. 164 и находился на указанной магистральной магистрали SIP.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы запустить командлет Test-CsTrunkConfiguration, необходимо сначала использовать командлет Get-CsTrunkConfiguration для получения экземпляра параметров конфигурации магистральной магистрали SIP; Затем этот экземпляр передается в Test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Выполнение Test-CsTrunkConfiguration без первого запуска Get-CsTrunkConfiguration не работает. Например, эта команда завершится сбоем, не возвращая никаких данных:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Если у вас несколько семейств параметров конфигурации магистральной магистрали SIP, вы можете использовать одну из следующих команд для проверки каждой из них по одному и тому же номеру телефона.

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Дополнительные сведения можно найти в справочной документации по командлету Test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если функция "тест-CsTrunkConfiguration" может позвонить на номер телефона, на экране будут отображены переведенный номер (в формате E. 164) и правило, используемое для перевода этого номера телефона.

Транслатеднумбер Матчингруле

\---------------- ------------

\+12065551219 Global/Redmond

Если тест не проходит проверку, CsTrunkConfiguration будет возвращать пустые значения свойств.

Транслатеднумбер Матчингруле

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если "Test-CsTrunkConfiguration" не возвращает соответствие, которое обычно означает, что проверяемые параметры конфигурации канала не имеют правила трансляции номеров исходящих вызовов для преобразования набора номера в формат E. 164. Чтобы получить правила перевода, назначенные коллекции параметров конфигурации канала, можно использовать синтаксис, подобный приведенному ниже.

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

, Возвращающий подобные данные для каждого правила трансляции.

Описание: номера телефонов без кода страны или города.

Шаблон: ^\\+ (\\d\*) $

`Translation : $1`

Name (имя): Ноареакоде

На этом этапе необходимо проверить значение свойства Pattern (строка [регулярного выражения](http://go.microsoft.com/fwlink/?linkid=400464) ), чтобы проверить, настроены ли какие-либо правила трансляции для обработки номера набора. Если это не так, вам придется изменить одно из существующих правил (Set-Ксаутбаундтранслатионруле) или использовать командлет New-Ксаутбаундтранслатионруле, чтобы добавить новое правило в коллекцию.

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

