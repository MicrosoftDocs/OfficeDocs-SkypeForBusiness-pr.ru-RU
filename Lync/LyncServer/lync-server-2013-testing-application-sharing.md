---
title: 'Lync Server 2013: тестирование общего доступа к приложениям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb9f5771651f68d36666e039a9af71436ac3635b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a>Тестирование общего доступа к приложениям в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsASConference. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsASConference** проверяет, может ли пользователь, который является членом тестовой конференции, участвовать в интерактивной конференции, включающей общий доступ к приложениям. Для этого командлет регистрирует двух пользователей с помощью Lync Server 2013, а затем использует одну из учетных записей пользователей для создания новой конференции, включающей общий доступ к приложениям. Затем командлет проверяет, может ли второй пользователь присоединиться к конференции.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в примере 1, проверяет, может ли конференция с общим доступом к приложениям проводиться в пуле atl-cs-001.litwareinc.com. Перед выполнением команды необходимо предварительно настроить пару тестовых пользователей для указанного пула. Если эти тестовые пользователи не существуют, команда завершится сбоем.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

В примере 2 проверяется, может ли компонент обеспечения процесса присоединения подключиться к конференции с общим доступом к приложениям в пуле atl-cs-001.litwareinc.com. Обратите внимание на то, что эта команда проверяет только сам компонент. Для ее выполнения мобильные устройства не требуются.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Команды, показанные в примере 2, проверяют возможность использования пользователями (litwareinc\\Pilar и litwareinc\\kenmyer) для входа в Lync Server 2013, а затем выполняют Конференц-связь с приложением. Для этого первая команда в примере использует командлет Get – Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman. (Так как имя для входа,\\litwareinc Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1. Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.

Если у вас есть объекты учетных данных в наличии, третья команда определяет, могут ли эти два пользователя войти в Lync Server 2013 и провести конференц-совместный доступ к приложениям. Для выполнения этой задачи вызывается командлет **Test-CsASConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); SenderSipAddress (SIP-адрес для первого тестового пользователя); SenderCredential (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ReceiverSipAddress (SIP-адрес для другого тестового пользователя); и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если общий доступ к приложениям настроен правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:01

Сообщение об ошибке:

Диагност

Если указанные пользователи не могут совместно использовать приложения, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:

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

Например, в примере выше приведена заметка "подключенная сторона не ответила", которая обычно указывает на проблему с пограничным сервером.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsASConference** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Эта команда завершится с ошибками, если тестовым пользователям была назначена политика конференц-связи, которая не позволяет использовать общий доступ к приложениям.

  - Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

