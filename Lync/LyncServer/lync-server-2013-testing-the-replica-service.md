---
title: 'Lync Server 2013: Тестирование службы реплики'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ad585ab12d874b7689aab6442ac913a06c8792f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Тестирование службы реплики в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-11-03_


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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsReplica</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsReplica** проверяет, запущена ли служба реплики Lync Server 2013 на локальном компьютере. Командлет **Test-CsReplica** выполняет такие задачи, как:

  - Проверка состояния агента Replicator и служб централизованного ведения журналов

  - Проверка того, что требуемые порты были открыты в брандмауэре Windows

  - Убедитесь, что у вас есть необходимые группы безопасности Active Directory и локального компьютера.

Обратите внимание, что этот командлет должен выполняться локально. То есть он должен выполняться на том же компьютере, на котором запущена служба реплики. Нет параметров для запуска командлета **Test-CsReplica** на удаленном сервере.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в примере 1, тестирует службу реплики Lync Server 2013 на локальном компьютере. В этом примере подробный параметр используется для гарантии того, что сведения о тесте, в том числе выработку результата теста, а также расположение отчета, созданного тестом, отображаются на экране.

    Test-CsReplica -Verbose

Пример 2 представляет собой видоизмененную команду из примера 1. В этом случае параметр Report включается для указания пути к папке и имени для отчета, созданного тестом. Если путь к отчету не указан, ему будет присвоено автоматически созданное имя, которое выглядит следующим образом:

C:\\Users\\администратор.\\litwareinc\\AppData\\Local\\temp\\1 Test-CS-реплика-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. HTML

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Вставьте сюда основную часть.

VERBOSE: создание\\нового файла журнала "C: пользователи\\тестовая\\папка\\AppData\\Local\\Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c. XML".

VERBOSE: создание\\нового файла журнала "C: пользователи\\тестовая\\папка\\AppData\\Local\\Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c. XML".

VERBOSE: обработка "Test-CsReplica" успешно завершена.

VERBOSE: подробные результаты можно найти по адресу "C:\\пользователи\\\\тестовая\\папка\\AppData\\Local Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c. XML".

VERBOSE: создание нового файла журнала

"C:\\пользователи\\\\тестовая\\папка\\AppData\\Local\\Temp 2 Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. XML ".

VERBOSE: создание нового файла журнала

"C:\\пользователи\\\\тестовая\\папка\\AppData\\Local\\Temp 2 Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. HTML ".

Предупреждение: сбой Test-CsReplica.

Предупреждение: подробные результаты можно найти по адресу:

"C:\\пользователи\\\\тестовая\\папка\\AppData\\Local\\Temp 2 Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. HTML ".

Test-CsReplica: ошибка выполнения команды: запрошенный доступ к реестру не

разрешенных.

В строке: 1 символ: 1

\+Test-CsReplica-verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+Категоринфо: Инвалидоператион: (:) \[Test-CsReplica\], Security

Exception

\+Фулликуалифиедеррорид: Процессингфаилед, Microsoft. RTC. Management. deploy

чения. тестрепликакмдлет

PS C:\\тестирование\\пользователей\>

PS C:\\пользователи\\тестирование\> Test-CsUcwaConference-TargetFqdn "Линктест. селфхост. Corp. M

icrosoft.com "

Предупреждение: не удалось считать номер порта регистратора для данного полного имени

доменное имя (FQDN). Использование номера порта регистратора по умолчанию. Возникновения

System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.

в

Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри

Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)

Test-CsUcwaConference: нет тестового пользователя, назначенного для

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Проверьте конфигурацию тестовой учетной записи пользователя.

В строке: 1 символ: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+Категоринфо: Ресаурцеунаваилабле: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор

Етиктрансактионс. Тестукваконференцекмдлет

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsReplica** :

  - Может возникнуть больше проблем с агентом Replicator и службами централизованного ведения журналов

  - Не удается открыть требуемые порты в брандмауэре Windows

  - Необходимые группы безопасности "Active Directory" и "локальный компьютер" могут не существовать.

</div>

</div>

<span> </span>

</div>

</div>

</div>

