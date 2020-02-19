---
title: 'Lync Server 2013: конфигурация тестовой базы данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c1698d576188a8bd87f94e5c61060267bf0fab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Тестирование конфигурации базы данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-07-07_


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
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins и иметь права администратора на SQL Server.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsDatabase</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsDatabase** проверяет возможность подключения к одной или нескольким базам данных Lync Server 2013. При запуске командлет **Test-CsDatabase** считывает топологию Lync Server, пытается подключиться к соответствующим базам данных, а затем сообщает об успехе или неудаче каждой попытки. Если подключение возможно, командлет также сообщит о такой информации, как имя базы данных, сведения о версии SQL Server, а также расположение любых установленных зеркальных баз данных.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда в примере 1 проверяет конфигурацию базы данных центрального хранилища управления.

    Test-CsDatabase -CentralManagementDatabase

В примере 2 проверяется все базы данных Lync Server, установленные на компьютере atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

В примере 3 проверка проводится только для базы данных Archiving (Архив), установленной на компьютере atl-sql-001.litwareinc.com. Обратите внимание, что здесь используется параметр SqlInstanceName, который указывает экземпляр SQL Server (Archinst), где расположена база данных Archiving.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

Команда, рассматриваемая в примере 4, проверяет базу данных, установленную на локальном компьютере.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если подключение к базе данных настроено правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство "успешно", помеченное как **true**:

SqlServerFqdn: atl-sql-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

DatabaseName: XDS

Данных

Склсерверверсион:

Експектедверсион: 10.13.2

Инсталледверсион:

Успешно: true

SqlServerFqdn: atl-sql-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

DatabaseName: LIS

Данных

Склсерверверсион:

Експектедверсион: 3.1.1

Инсталледверсион:

Успешно: true

Если база данных настроена правильно, но по-прежнему доступна, в поле успешно отображается **значение false**, а также предоставляются дополнительные предупреждения и сведения:

SqlServerFqdn: atl-sql-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

DatabaseName: XDS

Данных

Склсерверверсион:

Експектедверсион: 10.13.2

Инсталледверсион:

Успешно: false

SqlServerFqdn: atl-cs-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

DatabaseName: LIS

Данных

Склсерверверсион:

Експектедверсион: 3.1.1

Инсталледверсион:

Успешно: false

Предупреждение: при выполнении Test-CsDatabase возникли ошибки. Обратитесь к файлу журнала для

подробный анализ и проверка того, что устранены все ошибки (2) и предупреждения (0)

перед продолжением.

Предупреждение: подробные результаты можно найти по адресу:

"C:\\пользователи\\\\тестовая\\папка\\AppData\\Local\\Temp 2 Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. HTML ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsDatabase** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Эта команда завершится с ошибками, если база данных неправильно настроена или еще не развернута.

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get — CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get — CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

