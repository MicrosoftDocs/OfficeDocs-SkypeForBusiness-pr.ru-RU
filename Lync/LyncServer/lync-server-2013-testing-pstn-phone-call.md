---
title: 'Lync Server 2013: тестирование телефонного звонка PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc46703118d27533ac2afd2b4b448ad9516bdd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503976"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Тестирование телефонного звонка PSTN в Lync Server 2013

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsPstnOutboundCall тестирует возможность пользователя совершать вызовы на телефонный номер, находящийся в PSTN. При выполнении командлета Test-CsPstnOutboundCall сначала выполняется попытка входа тестового пользователя в Lync Server. Если вход выполнен успешно, командлет попробует позвонить через шлюз PSTN. Этот телефонный звонок будет выполняться с помощью абонентской группы, политики голосовой связи и других политик и параметров, назначенных тестовой учетной записи. При ответе на вызов командлет отправляет Многочастотные коды многочастотного набора (DTMF) через сеть для проверки возможности подключения к мультимедиа.

При проведении проверки Test-CsPstnOutboundCall будет совершать фактический телефонный звонок: целевой телефон будет звонить, и для успешного выполнения проверки должен быть получен ответ. Этот вызов также должен закончить администратором вручную.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-CsPstnOutboundCall можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server. Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула Lync Server и вызываемый телефонный номер PSTN. Например:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи. Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь может совершать вызов, и при ответе на него будет получено сообщение о том, что свойство Result помечено как **успешное:**

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.8630376

Ошибкой

Диагност

Если указанный пользователь не может выполнить вызов или ответ на него не получен, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:0987365

Ошибка: 403, запрещено

Диагностика: ErrorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User

Политика не содержит использования маршрута по телефону

В предыдущих выходных данных говорится, что тест завершился ошибкой, так как политика голосовой связи, назначенная указанному пользователю, не включает использование телефона. (Использование телефона применяет политики голосовой связи для маршрутов голосовой связи. Без политики голосовой связи и соответствующего маршрута голосовой связи вы не можете совершать звонки по протоколу PSTN.

В случае сбоя Test-CsPstnOutboundCall вы можете повторно выполнить тест, на этот раз включая параметр verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Если включен параметр Verbose, Test-CsPstnOutboundCall будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например, эти выходные данные показывают, что неполадки в сети препятствуют подключению с помощью PSTN:

Установка голосового видеозвонка в "SIP: + 12065551219@litwareinc. com; user = Phone".

Из сети получено исключение "ответ 404 (не найдено"); операция завершилась неудачно.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsPstnOutboundCall:

  - Вы указали недопустимую учетную запись пользователя. Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server. Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Если для свойства Enabled задано значение false, то в настоящее время у пользователя не включена поддержка Lync Server.

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

