---
title: 'Lync Server 2013: тестирование входа в Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce22e6c7f5fb48132f3f67c79c33daaa568d93ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Тестирование входа в Lync Phone Edition в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксфонебутстрап. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-Ксфонебутстрап позволяет администраторам выполнять вход в систему с устройства, совместимого с Lync 2013 Phone Edition, с помощью номера телефона и ПИН-кода, назначенного ему. (На самом деле не требуется никаких устройств для выполнения теста.)

Чтобы командлет Test-CsPhoneBootstrap мог выполнить проверку, пул регистратора, в котором размещается учетная запись проверяемого пользователя, должен обнаруживаться по протоколу DHCP. Чтобы определить, может ли регистратор быть обнаруживаемым таким образом, используйте командлет Get-CsRegistrarConfiguration и проверьте значение свойства Енабледхкпсервер. Если для этого свойства задано значение false, необходимо использовать Set-CsRegistrarConfiguration, чтобы задать для свойства значение true и сделать регистратор обнаруживаемым с помощью DHCP. Это также можно сделать с помощью корпоративного DHCP-сервера и настройки параметров, относящихся к Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Для запуска командлета Test-Ксфонебутстрап необходимо, как минимум, указать номер телефона и личный идентификационный номер клиента (ПИН-код) для допустимого пользователя Lync Server. Например, эта команда проверяет возможность входа в систему для пользователя с номером телефона 12065551219 и ПИН-кодом 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Для более полной проверки можно также включить SIP адрес пользователя. В этом случае телефонный номер, ПИН-код клиента и SIP-адрес должны быть действительными для успешного выполнения проверки:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Дополнительные сведения можно найти в справочной документации по командлету [Test-ксфонебутстрап](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если указанный пользователь мог подключаться к Lync Server, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

Цертпровисионингсервице. svc

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:06.3981276

Ошибкой

Диагност

Если указанный пользователь не смог установить соединение, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:04.1993845

Ошибка: ошибка — не получен ответ для службы веб-билета.

Диагност

Предыдущие выходные данные подействовали, так как служба веб-билета не ответила. Это может быть вызвано проблемой с самой службой или из-за того, что адрес SIP, номер телефона или ПИН-код клиента передается в Test-Ксфонебутстрап. Вы можете проверить SIP адрес и номер телефона пользователя с помощью следующей команды:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Вы также можете убедиться, что у пользователя есть действительный ПИН-код, выполнив команду следующим образом:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Если Test-Ксфонебутстрап завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Если включен параметр Verbose, командлет Test-Ксфонебутстрап возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server. Например, ниже приведена часть выходных данных для неудачного входа в сеанс, в котором был включен неправильный ПИН-код:

Использование проверки подлинности\\ПИН-кода с телефонным телефоном: 12065551219 PIN: 0712

Не удалось получить веб-билет

ПРОВЕРЯТЬ

\-URL-адрес веб-службы является допустимым, а веб-службы функционируют

\-Если для проверки\\подлинности используется ПИН-код фонено, убедитесь, что они совпадают с URI пользователя.

\-При использовании проверки\\подлинности NTLM Kerberos убедитесь, что вы предоставили действительные учетные данные.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-Ксфонебутстрап:

  - Возможно, указан недопустимый SIP-адрес. Для проверки правильности SIP-адреса можно использовать следующую команду:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Возможно, указан недопустимый ПИН-код. Несмотря на то, что вы не можете получить PIN-код пользователя, вы можете убедиться, что у пользователя по крайней мере есть PIN-код, с помощью следующей команды:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Возможно, указан недопустимый номер телефона. Вы можете проверить телефон пользователя, выполнив команду следующего вида:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Для пула регистратора не включена поддержка DHCP. Чтобы определить, включен ли для пула регистратора DHCP, выполните командлет Get-CsRegistrarConfiguration и проверьте значение свойства Енабледхкпсервер. Пример:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

