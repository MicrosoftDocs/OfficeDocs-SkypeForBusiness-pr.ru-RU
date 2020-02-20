---
title: 'Lync Server 2013: Проверка правил нормализации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cf48022fc62f959bbddcd3cb6978e2e668a9334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Проверка правил нормализации голосовой связи в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsVoiceNormalizationRule. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Правила нормализации голосовой связи используются для преобразования телефонного номера, набранного пользователем (например, 2065551219), в формат E. 164, используемый Lync Server (+ 12065551219). Например, если пользователь набирает номер телефона, не включая код страны или код города (например, 5551219), необходимо создать правило нормализации голосовой связи, которое может преобразовать этот номер в формат E. 164: + 12065551219. Без такого правила пользователь не сможет вызвать 555-1219.

Командлет Test-CsVoiceNormalizationRule проверяет, может ли указанное правило нормализации голоса успешно преобразовывать указанный номер телефона. Например, эта команда проверяет, можно ли нормализовать глобальное правило нормализации Ноареакоде и конвертировать строку набора 5551219.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Для запуска командлета Test-CsVoiceNormalizationRule сначала необходимо использовать командлет Get-CsVoiceNormalizationRule для извлечения экземпляра тестируемого правила, а затем передать этот экземпляр в Test-CsVoiceNormalizationRule. Синтаксис, похожий на этот, не работает:

Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "Global/prefix ALL"

Вместо этого используйте синтаксис, аналогичный приведенному ниже, который сочетает командлеты Get-CsVoiceNormalizationRule и Test-CsVoiceNormalizationRule:

Get-CsVoiceNormalizationRule-Identity "Global/prefix ALL" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . Кроме того, вы также можете использовать этот подход, чтобы получить экземпляр правила, а затем проверить это правило по указанному номеру телефона:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Введите значение параметра DialedNumber в точности так, как ожидается набираемый номер. Например, если указанное правило нормализации голосовой связи должно автоматически добавлять код страны (первый 1 в значении 12065551219), то не следует оставлять код страны:

`-DialedNumber "2065551219"`

Если правило настроено правильно, оно автоматически добавляет код страны при преобразовании номера в формат E. 164, используемый Lync Server.

Дополнительные сведения можно найти в справочной документации по командлету Test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанное правило нормализации голосовой связи может переводить предоставленный номер, переведенный номер будет отображаться на экране:

транслатеднумбер

\----------------

\+12065551219

Если тест завершается неудачей, возвращается пустой переведенный номер:

транслатеднумбер

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если Test-CsVoiceNormalizationRule возвращает переведенный номер, который означает, что указанное правило нормализации голосовой связи не смогло преобразовать предоставленный телефонный номер в формат E. 164, используемый Lync Server. Чтобы убедиться в этом, сначала убедитесь, что номер телефона введен правильно. Например, вы ожидаете, что правило нормализации голоса будет иметь проблемы при преобразовании числа, аналогичного следующему:

`-DialedNumber "1"`

Если номер введен правильно, необходимо убедиться, что указанное правило нормализации предназначено для обработки этого номера телефона. Например, одно правило нормализации может быть предназначено для обработки формата 12065551219, но второе правило может быть предназначено для обработки числа 2065551219. (Это тот же номер телефона, но не код страны 1 в самом начале). Чтобы получить подробные сведения о правиле нормализации голосовой связи, выполните следующую команду:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Чтобы получить подробные сведения о всех правилах нормализации голосовой связи, выполните следующую команду:

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

