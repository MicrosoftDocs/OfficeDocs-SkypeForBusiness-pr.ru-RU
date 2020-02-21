---
title: 'Lync Server 2013: тестирование обмена сообщениями Exchange с уведомлениями Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d186a41c8997f7e05a9bc9be93b44ff7b675b907
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a>Тестирование Exchange в уведомления Lync в Lync Server 2013

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
<td><p>Daily (Ежедневный)</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExStorageNotification</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsExStorageNotification** используется для проверки того, что служба уведомлений Microsoft Exchange Server 2013 может уведомлять Lync Server 2013 о внесении обновлений в список контактов пользователя. Это командлет доступен только при использовании единого хранилища контактов.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в примере 1, проверяет, может ли служба хранилища Lync Server подключаться к службе уведомлений почтовых ящиков Microsoft Exchange Server для пользователя sip:kenmyer@litwareinc.com. В данном примере в качестве привязки WCF используется NetNamedPipe.

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если интеграция Exchange настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное**:

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если указанный пользователь не может получать уведомления, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

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

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExStorageNotification** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Эта команда завершится с ошибками, если сервер Microsoft Exchange неправильно настроен или еще не развернут.

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

