---
title: 'Lync Server 2013: проверка Exchange на уведомления Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a>Проверка Exchange для уведомлений Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневно</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксексстораженотификатион</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-ксексстораженотификатион** используется для подтверждения того, что служба уведомлений сервера Microsoft Exchange Server 2013 может уведомлять Lync Server 2013 о внесении обновлений в список контактов пользователя. Этот командлет действует только в том случае, если вы используете единое хранилище контактов.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в примере 1, проверяет, может ли служба хранилища Lync Server подключиться к службе уведомлений почтового ящика сервера Microsoft Exchange Server для пользователя sip:kenmyer@litwareinc.com. В этом примере Нетнамедпипе используется в качестве привязки WCF.

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если интеграция с Exchange настроена правильно, вы получите вывод примерно так, чтобы свойство Result пометило " **успешно**".

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успех

Задержка: 00:00:00

Сообщение об ошибке:

Диагностик

Если указанный пользователь не может получать уведомления, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона

не отвечает на запросы в течение определенного периода времени или

не удалось установить соединение, так как подключенный узел имеет

не удалось ответить на 10.188.116.96:5061

Внутреннее исключение: сбой при попытке подключения из-за того, что

связь с абонентом завершилась неправильно после определенного периода

время или соединение не удалось установить, так как подключенный узел

не удалось ответить 10.188.116.96:5061

Диагностик

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксексстораженотификатион** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем. Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.

  - Эта команда завершится сбоем, если сервер Microsoft Exchange неправильно настроен или еще не развернут.

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

