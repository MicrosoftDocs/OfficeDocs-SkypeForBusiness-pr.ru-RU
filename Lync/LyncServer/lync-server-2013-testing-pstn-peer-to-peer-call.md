---
title: 'Lync Server 2013: тестирование однорангового вызова PSTN'
description: 'Lync Server 2013: тестирование однорангового вызова PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf8726c46374e3a799b986e071566d0ae1de138
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552685"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Тестирование однорангового звонка PSTN в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsPstnPeerToPeerCall. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsPstnPeerToPeerCall проверяет возможность, с помощью которого пользователи могут выполнять одноранговые вызовы через шлюз телефонной сети общего пользования (PSTN). При вызове командлета Test-CsPstnPeerToPeerCall командлет сначала попытается выполнить вход двух тестовых пользователей на Lync Server. При условии, что входы выполняются успешно, в командлете пользователь 1 пытается позвонить пользователю 2 по шлюзу PSTN. Test-CsPstnPeerToPeerCall сделает этот вызов с помощью абонентской группы, политики голосовой связи, а также других параметров политики и конфигурации, назначенных тестовому пользователю. Если тест проходит запланированно, командлет проверяет, чтобы пользователь 2 мог ответить на звонок, а затем выйдите из системы как тестовые учетные записи из системы.

Test-CsPstnPeerToPeerCall выполняет фактический телефонный звонок, который проверяет, можно ли выполнить подключение, а также передает коды DTMF по сети, чтобы определить, можно ли отправлять мультимедиа по подключению. На вызов отвечает сам командлет, и нет необходимости вручную завершать вызов. (То есть, ни один из них не должен отвечать, а затем прервать вызов.)

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsPstnPeerToPeerCall можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей (см. Настройка тестовых учетных записей для запуска тестов Lync Server) или учетных записей двух пользователей, для которых включен Lync Server. Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи. Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsPstnPeerToPeerCall:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанные пользователи могут выполнить одноранговый вызов, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.8630376

Ошибкой

Диагност

Если указанные пользователи не могут выполнить одноранговый звонок, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:0182361

Ошибка: 403, запрещено

Диагностика: ErrorCode = 12001, Source = ATL – CS – 001.litwareinc.com,

Reason = политика пользователя не содержит использования маршрута по телефону

В предыдущих выходных данных говорится, что тест завершился ошибкой, так как политика голосовой связи, назначенная по крайней мере одному из указанных пользователей, не включает использование телефона. (Использование телефона применяет политики голосовой связи для маршрутов голосовой связи. Без политики голосовой связи и соответствующего голосового маршрута нельзя совершать звонки по протоколу PSTN.

Если Test-CsPstnPeerToPeerCall завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Если включен параметр Verbose, Test-CsPstnPeerToPeerCall будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например, эти выходные данные показывают, что неполадки в сети препятствуют подключению с помощью PSTN:

Установка голосового видеозвонка в "SIP: + 12065551219@litwareinc. com; user = Phone".

Из сети получено исключение "ответ 404 (не найдено"); операция завершилась неудачно.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsPstnPeerToPeerCall:

  - Указана недопустимая учетная запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.

  - Политика голосовой связи, назначенная указанному пользователю, не имеет действительного использования PSTN. Вы можете определить политику голосовой связи, назначенную пользователю, с помощью следующей команды:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Затем вы можете определить использование PSTN (если они есть), назначенные этой политике, с помощью следующей команды, которая получает сведения о политике голосовой связи "на пользователя" RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

