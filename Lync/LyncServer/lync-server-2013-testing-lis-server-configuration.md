---
title: 'Lync Server 2013: тестирование конфигурации сервера LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50b2908b3f2403cc59f4cb7ce26f176d366ce2e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Тестирование конфигурации сервера LIS в Lync Server 2013

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
<td><p>Daily (Ежедневный)</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsLisConfiguration. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsLisConfiguration проверяет возможность связи с веб-службой LIS. Если вы можете связаться с веб-службой, тест будет считаться успешным, независимо от того, можно ли найти какие-либо конкретные расположения.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Командлет Test-Кслисконфгуратион можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server. Чтобы выполнить эту проверку с помощью тестовой учетной записи, достаточно указать полное доменное имя тестируемого пула Lync Server. Например:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи. Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsLisConfiguration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если LIS настроен правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/

лисервице. svc

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.1616913

Ошибкой

Диагност

Если указанный пользователь не может войти в систему или выйти из нее, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Ошибка: 11004, запрошенное имя является допустимым, но данные запрошенного

обнаружен тип

Диагност

Test-CsLisConfiguration: в топологии не обнаружены подходящие кластеры.

Например, в предыдущем выходе включается заметка "в топологии не обнаружены подходящие кластеры". Как правило, это свидетельствует о проблеме с пограничным сервером: LIS, использующий пограничный сервер, для подключения к поставщику услуг и проверки адресов.

Если не удается выполнить команду Test-CsLisConfiguration, вам может потребоваться повторить проверку, в том числе параметр verbose:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Если включен параметр Verbose, командлет Test-CsLisConfiguration возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например:

Служба сведений о расположении звонков.

Путь к службе =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

Чассисид =

Портид =

Портидсубтипе = неопределенный тип

Mac

Ошибка запроса веб-службы сведений о расположении с кодом отклика Item400. возникла во время выполнения рабочего процесса Microsoft. RTC. Синсетиктрснактионс. Workflows. Стлисконфигуратионворкфлов.

Если вы изучите предыдущие выходные данные, вы увидите, что командлет завершился с ошибкой после попытки вызова службы сведений о местоположении. Один из параметров, которые использовались в этом вызове:

BssId = 5

Это значение не является допустимым для базового идентификатора набора служб (BssID). Вместо этого BssID должен выглядеть примерно так:

12-34-56-78-90 – AB

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsLisConfiguration:

  - Предоставлено неправильное значение параметра. Как показано в предыдущем примере, необязательные параметры должны быть настроены правильно, иначе тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

</div>

</div>

<span> </span>

</div>

</div>

</div>

