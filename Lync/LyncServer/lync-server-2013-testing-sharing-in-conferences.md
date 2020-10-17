---
title: 'Lync Server 2013: Проверка общего доступа в конференциях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36cf05d0d3d5cce13a100d23cb541eb5aa186ef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530496"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Тестирование общего доступа в конференциях в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-11-01_


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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsDataConference</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

В Lync Server 2013 конференц-связи с данными — это любая конференция, в которой используются операции сотрудничества, такие как доска или заметки. Командлет **Test-CsDataConference** позволяет проверить, могут ли две пользователи принять участие в конференции с данными.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в примере 1, проверяет, может ли конференция для совместной работы с данными проводиться в пуле atl-cs-001.litwareinc.com. Перед выполнением команды необходимо предварительно настроить пару тестовых пользователей для указанного пула. Если эти тестовые пользователи не существуют, команда завершится сбоем.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Команды, показанные в примере 2, проверяют возможность использования пользователями двух пользователей (litwareinc \\ Pilar и litwareinc \\ kenmyer) для входа в Lync Server 2013 и проведения Конференции с данными. Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman. (Так как имя для входа, litwareinc \\ Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1. Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.

Если у вас есть объекты учетных данных в наличии, третья команда определяет, могут ли эти два пользователя войти в Lync Server 2013 и провести конференц-передачу данных. Для выполнения этой задачи вызывается командлет **Test-CsDataConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); SenderSipAddress (SIP-адрес для первого тестового пользователя); SenderCredential (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ReceiverSipAddress (SIP-адрес для другого тестового пользователя); и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Конференц-связь с данными настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если указанные пользователи не могут использовать общий доступ к данным, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона

не ответил должным образом по истечении определенного периода времени или

не удалось установить подключение, так как у подключенного узла есть

не удалось ответить на \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944: \] 5061

Внутреннее исключение: сбой попытки подключения, так как

подключенная сторона не ответила должным образом после периода

время или установленное подключение не выполнено, так как подключенный узел

не отвечает

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061

Диагност

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsDataConference** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Возможность проведения Конференции с данными зависит от политики конференц-связи, назначенной пользователю, который организует конференцию (в случае командлета **Test-CsDataConference** , который является "отправителем"). Если организатор не может включать в свое собрание действия для совместной работы (например, если для свойства Енабледатаколлаборатион в политике конференц-связи задано значение false), командлет **Test-CsDataConference** завершится с ошибками.

  - Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.

</div>

</div>

<span> </span>

</div>

</div>

</div>

