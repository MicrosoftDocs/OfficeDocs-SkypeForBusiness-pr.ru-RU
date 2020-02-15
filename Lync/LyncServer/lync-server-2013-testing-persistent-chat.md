---
title: 'Lync Server 2013: тестирование сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee9869d5e7a5e3a48451478de334ee656543f6f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Тестирование сохраняемого чата в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsPersistentChatMessage</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsPersistentChatMessage** проверяет, может ли пользователь, выполняющий проверку, обмениваться сообщениями с помощью службы сохраняемого чата. Для этого командлет записывает два пользователя в Lync Server 2013, подключает пользователей к комнате сохраняемого чата, обменивается с другими сообщениями, а затем выходит из комнаты чата и выходит из системы двух пользователей. Обратите внимание на то, что вызовы этого командлета завершатся неуспешно, если вы не создали комнаты чата или две тестовых учетных записей пользователей не назначены политике сохраняемого чата, которая предоставляет им доступ к службе сохраняемого чата.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команды, показанные в следующем примере, проверяют способность пользователей (litwareinc\\Pilar и litwareinc\\kenmyer) войти в Lync Server 2013, а затем обмениваться сообщениями с помощью службы сохраняемого чата. Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman. (Так как имя для входа,\\litwareinc Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1. Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.

Если у вас есть объекты учетных данных в наличии, третья команда определяет, могут ли эти два пользователя входить в Lync Server 2013 и обмениваться сообщениями с помощью сохраняемого чата. Для выполнения этой задачи командлет **Test-CsPersistentChatMessage** вызывается с использованием следующих параметров: TargetFqdn (полное доменное имя пула регистратора); SenderSipAddress (SIP-адрес для первого тестового пользователя); SenderCredential (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ReceiverSipAddress (SIP-адрес для другого тестового пользователя); и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь имеет действительную политику расположения, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:00

Сообщение об ошибке:

Диагност

Если указанные пользователи не могут обмениваться сообщениями с помощью службы сохраняемого чата, результат будет отображаться как **сбой**, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения.

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

не удалось ответить \[на 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061

Внутреннее исключение: сбой попытки подключения, так как

подключенная сторона не ответила должным образом после периода

время или установленное подключение не выполнено, так как подключенный узел

не отвечает

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Диагност

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsPersistentChatMessage** :

  - Предоставлено неправильное значение параметра. Возможно, необходимые тестовые учетные записи не существуют или созданы неправильно.

  - Возможно, возникла проблема с сетью, которая привела к непредвиденной задержке, при которой истекло время ожидания проверки.

</div>

<div>

## <a name="see-also"></a>См. также


[Granting — CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New — CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set — CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

