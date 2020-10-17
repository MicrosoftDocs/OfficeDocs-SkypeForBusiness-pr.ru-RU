---
title: Тестирование конфигурации учетной записи Kerberos, назначенной сайту
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08477e9902a1410a98516a79fe5fdd01c5e94214
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504126"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Тестирование конфигурации учетной записи Kerberos, назначенной сайту, в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>Ежедневное</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsKerberosAccountAssignment. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-CsKerberosAccountAssignment позволяет убедиться, что учетная запись Kerberos связана с определенным сайтом, что эта учетная запись настроена правильно, а учетная запись работает должным образом. Учетные записи Kerberos — это учетные записи компьютеров, которые могут выступать в качестве субъекта проверки подлинности для всех компьютеров сайта, на котором работает сервер IIS. Так как эти учетные записи используют протокол проверки подлинности Kerberos, учетные записи называются учетными записями Kerberos, а новый процесс проверки подлинности называется проверкой подлинности Kerberos. Это позволяет управлять всеми серверами IIS с помощью одной учетной записи.

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

По умолчанию на экране Test-CsKerberosAccountAssignment отображаются очень мелкие выходные данные. Вместо этого сведения, возвращаемые командлетом, записываются в HTML-файл. Из-за этого мы рекомендуем включить параметр Verbose и параметр отчета каждый раз при запуске test-CsKerberosAccountAssignment. Параметр verbose предоставит немного более подробный вывод на экран при выполнении командлета. Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-CsKerberosAccountAssignment. Если не включить параметр отчета, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь имя, аналогичное следующему: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

Кроме того, при выполнении командлета Test-CsKerberosAccountAssignment необходимо указать удостоверение сайта. Учетные записи Kerberos назначаются в области сайта.

Следующая команда выполняет Test-CsKerberosAccountAssignment и сохраняет выходные данные в файл с именем C: \\ Logs \\KerberosTest.html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Дополнительные сведения можно найти в справочной документации по командлету [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Командлет Test-CsKerberosAccountAssignment не возвращает простой индикатор успешного или неудачи. Вместо этого необходимо просмотреть созданный HTML-файл с помощью Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsKerberosAccountAssignment:

  - Возможно, вы указали неправильное удостоверение сайта. Чтобы получить список допустимых идентификаторов сайтов, используйте следующую команду:
    
        Get-CsSite | Select-Identity Identity
    
    Как правило, идентификатор сайта выглядит следующим образом:
    
    site: Redmond

  - Для указанного сайта может быть не назначена учетная запись Kerberos. Вы можете определить, назначена ли учетная запись Kerberos сайту, выполнив следующую команду:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Учетная запись Kerberos может иметь Недействительный пароль. Если в отчете отображается следующее сообщение об ошибке, вероятно, вам потребуется сбросить пароль учетной записи Kerberos:
    
    Инвалидкерберосконфигуратион: Недопустимая конфигурация Kerberos.
    
    Инвалидкерберосконфигуратион: Конфигурация Kerberos в atl-cs001.litwareinc.com является недопустимой. Предполагаемая назначенная учетная запись — litwareinc \\ kerberostest. Убедитесь, что срок действия учетной записи не истек, а пароль, настроенный на компьютере, соответствует паролю учетной записи Active Directory.
    
    Вы можете задать пароль с помощью командлета [Set – кскерберосаккаунтпассворд](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

