---
title: 'Lync Server 2013: тестирование подключения пользователя к голосовой почте Exchange единой системы обмена сообщениями'
description: 'Lync Server 2013: тестирование подключения пользователя к голосовой почте Exchange единой системы обмена сообщениями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b887b5b0df02a5864e0a39f2b62893d20105a86a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552615"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Тестирование подключения пользователя к голосовой почте Exchange единой системы обмена сообщениями в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExUMVoiceMail</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsExUMVoiceMail** позволяет администраторам убедиться в том, что пользователь может получить доступ к службе единой системы обмена сообщениями Microsoft Exchange Server 2013 и использовать ее. Для этого командлет подключается к службе единой системы обмена сообщениями и оставляет голосовое сообщение в нужном почтовом ящике. Это может быть системное голосовое сообщение или WAV-файл, записанный самим пользователем.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

В следующем примере показано, как проверить подключение голосовой почты единой системы обмена сообщениями Exchange для пула atl-cs-001.litwareinc.com. Эта команда будет работать только в том случае, если тестовые пользователи были определены для пула atl-cs-001.litwareinc.com. В этом случае команда определит, может ли первый тестовый пользователь использовать голосовую почту единой системы обмена сообщениями. Если тестовые пользователи не были настроены для пула, команда завершится с ошибками.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

Команды, показанные в следующем примере, проверяют подключение голосовой почты единой системы обмена сообщениями Exchange для пользователя litwareinc \\ kenmyer. Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell для пользователя litwareinc \\ kenmyer. Обратите внимание, что для этой учетной записи необходимо указать пароль, чтобы создать допустимый объект учетных данных и убедиться, что командлет **Test-CsExUMVoiceMail** может выполнить его проверку.

Вторая команда в примере использует предоставленный объект учетных данных ($x) и SIP-адрес пользователя litwareinc kenmyer, \\ чтобы определить, может ли этот пользователь подключиться к голосовой почте единой системы обмена сообщениями Exchange.

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

Команда, показанная в следующем примере, является вариантом команды, показанной в примере 1; в этом случае параметр OutLoggerVariable включается для создания подробного журнала каждого шага, выполняемого с помощью **Test-CsExUMVoiceMail** , кмдлетанд успешное или неуспешное выполнение каждого из этих действий. Для этого параметр OutLoggerVariable добавляется вместе со значением параметра Ексумтекст; Это приводит к тому, что подробные сведения о ведении журнала хранятся в переменной с именем $ExumTest. В завершающей команде в примере метод ToXML () используется для преобразования данных журнала в формат XML. После этого XML-данные записываются в файл с именем C: \\ Logs \\VoicemailTest.xml с помощью командлета Out-File.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если интеграция Exchange настроена правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:02.9911345

Сообщение об ошибке:

Диагност

Если указанный пользователь не может подключаться к голосовой почте, результат будет отображаться как **сбой**, а в свойствах диагностики ошибок и диагностики будет записана дополнительная информация:

Предупреждение: не удалось считать номер порта регистратора для данного полного имени

доменное имя (FQDN). Использование номера порта регистратора по умолчанию. Возникновения

System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.

в

Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри

Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)

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

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExUMVoiceMail** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Эта команда завершится с ошибками, если сервер Exchange неправильно настроен или еще не развернут.

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

