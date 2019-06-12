---
title: Проверка конфигурации учетной записи Kerberos, назначенной сайту
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Проверка конфигурации учетной записи Kerberos, назначенной сайту, в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-06-05_


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
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кскерберосаккаунтассигнмент. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет Test-Кскерберосаккаунтассигнмент позволяет удостовериться, что учетная запись Kerberos связана с данным сайтом, что эта учетная запись настроена правильно, а учетная запись работает должным образом. Учетные записи Kerberos — это учетные записи компьютеров, которые могут служить субъектом проверки подлинности для всех компьютеров на сайте, на котором запущен сервер IIS. Поскольку эти учетные записи используют протокол проверки подлинности Kerberos, учетные записи известны как учетные записи Kerberos, а новый процесс проверки подлинности известен как веб-проверка подлинности Kerberos. Это позволяет управлять всеми серверами IIS с помощью одной учетной записи.

Дополнительные сведения можно найти в справочной документации по командлету [Test-кскерберосаккаунтассигнмент](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

По умолчанию в режиме Test-Кскерберосаккаунтассигнмент отображается очень мало вывода на экран. Вместо этого данные, возвращаемые командлетом, записываются в HTML-файл. По этой причине мы рекомендуем включать параметр подробных данных и параметр отчета каждый раз при запуске test-Кскерберосаккаунтассигнмент. Параметр verbose обеспечивает немного более подробный вывод на экран во время выполнения командлета. Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-Кскерберосаккаунтассигнмент. Если параметр отчета не указан, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь такое имя, как: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.

Кроме того, необходимо указать удостоверение сайта при запуске test-Кскерберосаккаунтассигнмент. Учетные записи Kerberos назначаются на уровне сайта.

Следующая команда запускает команду Test-Кскерберосаккаунтассигнмент и сохраняет выходные данные в файл с именем C:\\Logs\\керберостест. HTML:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Дополнительные сведения можно найти в справочной документации по командлету [Test-кскерберосаккаунтассигнмент](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Командлет Test-Кскерберосаккаунтассигнмент не возвращает простой индикатор успеха или сбоя. Вместо этого вы должны просмотреть созданный HTML-файл с помощью Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кскерберосаккаунтассигнмент:

  - Возможно, вы указали неверный идентификатор сайта. Чтобы возвратить список допустимых идентификаторов сайта, используйте следующую команду:
    
        Get-CsSite | Select-Identity Identity
    
    Идентификатор сайта обычно выглядит следующим образом:
    
    сайт: Redmond

  - Возможно, для указанного сайта не назначена учетная запись Kerberos. Вы можете определить, назначена ли учетная запись Kerberos сайту, выполнив следующую команду:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Ваша учетная запись Kerberos может иметь Недействительный пароль. Если в отчете появляется следующее сообщение об ошибке, возможно, потребуется сбросить пароль учетной записи Kerberos.
    
    Инвалидкерберосконфигуратион: Недопустимая конфигурация Kerberos.
    
    Инвалидкерберосконфигуратион: Недопустимая конфигурация Kerberos на atl-cs001.litwareinc.com. Ожидаемой назначенной учетной\\записи является плана litwareinc керберостест. Убедитесь в том, что срок действия учетной записи не истек, и настроенный пароль для компьютера совпадает с паролем учетной записи Active Directory.
    
    Вы можете установить пароль с помощью командлета [Set-кскерберосаккаунтпассворд](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

