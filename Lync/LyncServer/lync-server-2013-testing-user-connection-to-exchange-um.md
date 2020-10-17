---
title: 'Lync Server 2013: тестирование подключения пользователя к единой системе обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6fd59ed0efb3a775017af1effd7bd022071fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503876"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Тестирование подключения пользователя к единой системе обмена сообщениями Exchange в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExUMConnectivity</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsExUMConnectivity** проверяет, может ли указанный пользователь подключаться к службе единой системы обмена сообщениями Microsoft Exchange Server 2013. Обратите внимание, что этот командлет проверяет только то, что для службы можно установить подключение. Он не проверяет саму службу. Чтобы протестировать службу единой системы обмена сообщениями (запустив командлет искусственной транзакции, который оставляет сообщение голосовой почты в почтовом ящике пользователя), используйте командлет Test-CsExUMVoiceMail.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

В следующем примере показано, как проверить подключение единой системы обмена сообщениями Exchange для пула atl-cs-001.litwareinc.com. Эта команда будет работать только в том случае, если тестовые пользователи были определены для пула atl-cs-001.litwareinc.com. В этом случае команда определит, может ли первый тестовый пользователь подключаться к единой системе обмена сообщениями. Если тестовые пользователи не были настроены для пула, команда завершится с ошибками.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

Команды, показанные в следующем примере, проверяют подключение единой системы обмена сообщениями Exchange для пользователя litwareinc \\ kenmyer. Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell для пользователя litwareinc \\ kenmyer. Обратите внимание, что для этой учетной записи необходимо указать пароль, чтобы создать допустимый объект учетных данных и убедиться, что командлет **Test-CsExUMConnectivity** может выполнить его проверку.

Вторая команда в примере использует предоставленный объект учетных данных ($x) и SIP-адрес пользователя litwareinc kenmyer, \\ чтобы определить, может ли этот пользователь подключиться к единой системе обмена сообщениями Exchange.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Команда, показанная в следующем примере, является вариантом только что показанной команды. В этом случае параметр OutLoggerVariable включается для создания подробного журнала каждого шага, выполняемого с помощью **Test-CsExUMConnectivity** , кмдлетанд успешное или неуспешное выполнение каждого из этих действий. Для этого параметр OutLoggerVariable добавляется вместе со значением параметра Ексумтекст; Это приводит к тому, что подробные сведения о ведении журнала хранятся в переменной с именем $ExumTest. В завершающей команде в примере метод ToXML () используется для преобразования данных журнала в формат XML. После этого XML-данные записываются в файл с именем C: \\ Logs \\ExumTest.xml с помощью командлета Out-File.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если интеграция Exchange настроена правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если указанный пользователь не может получать уведомления, результат будет отображаться как **сбой**, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона

не ответил должным образом по истечении определенного периода времени или

не удалось установить подключение, так как у подключенного узла есть

не удалось ответить на 10.188.116.96:5061

Внутреннее исключение: сбой попытки подключения, так как

подключенная сторона не ответила должным образом после периода

время или установленное подключение не выполнено, так как подключенный узел

не удалось ответить на 10.188.116.96:5061

Диагност

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExUMConnectivity** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Эта команда завершится с ошибками, если сервер Exchange неправильно настроен или еще не развернут.

  - Если сервер Exchange недостижим по сети, эта команда завершится с ошибками.

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

