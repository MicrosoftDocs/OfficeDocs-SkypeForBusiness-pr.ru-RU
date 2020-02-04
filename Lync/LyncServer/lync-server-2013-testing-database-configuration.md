---
title: 'Lync Server 2013: Проверка конфигурации базы данных'
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Проверка конфигурации базы данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-07-07_


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
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс и должны иметь права администратора на сервере SQL Server.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксдатабасе</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-ксдатабасе** проверяет подключение к одной или нескольким базам данных Lync Server 2013. При запуске командлет **Test-ксдатабасе** считывает топологию Lync Server, пытается подключиться к соответствующим базам данных, а затем сообщает об успешном завершении или сбое каждой попытки. Если подключение может быть установлено, командлет также сообщит такую информацию, как имя базы данных, сведения о версии SQL Server и расположение установленных зеркальных баз данных.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в примере 1, проверяет конфигурацию базы данных Центрального управления.

    Test-CsDatabase -CentralManagementDatabase

Пример 2: проверка всех баз данных Lync Server, установленных на компьютере atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

В примере 3 Проверка выполняется только для архивной базы данных, установленной на компьютере atl-sql-001.litwareinc.com. Обратите внимание, что параметр Склинстанценаме включает экземпляр SQL Server (Арчинст), в котором находится база данных архивации.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

Команда, показанная в примере 4, проверяет базы данных, установленные на локальном компьютере.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Если подключение к базам данных настроено должным образом, вы получите такие данные, как, например, свойство успешно, помеченное как **Истина**:

Склсерверфкдн: atl-sql-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

DatabaseName: XDS

Источников

Склсерверверсион:

Експектедверсион: 10.13.2

Инсталледверсион:

Успешно: истина

Склсерверфкдн: atl-sql-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

Имя базы: LIS

Источников

Склсерверверсион:

Експектедверсион: 3.1.1

Инсталледверсион:

Успешно: истина

Если база данных настроена правильно, но по-прежнему доступна, поле "успешно" будет отображаться как " **ложь**", а также будут указаны дополнительные предупреждения и сведения.

Склсерверфкдн: atl-sql-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

DatabaseName: XDS

Источников

Склсерверверсион:

Експектедверсион: 10.13.2

Инсталледверсион:

Успешно: ложь

Склсерверфкдн: atl-cs-001.litwareinc.com

Склинстанценаме: RTC

Миррорсклсерверфкдн:

Миррорсклинстанценаме:

Имя базы: LIS

Источников

Склсерверверсион:

Експектедверсион: 3.1.1

Инсталледверсион:

Успешно: ложь

Предупреждение: при выполнении теста-Ксдатабасе возникли ошибки. Просмотрите файл журнала для

подробный анализ и проверка того, что все ошибки (2) и предупреждения (0) рассмотрены.

перед продолжением.

Предупреждение: подробные результаты можно найти по адресу

"C:\\пользователи\\\\проверяют\\каталог\\AppData\\Local\\Temp 2 Test-ксдатабасе-b18d488a-8044-4679-bbf2-

04d593cce8e6. HTML ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксдатабасе** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем. Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.

  - Эта команда завершается сбоем, если база данных неправильно настроена или еще не развернута.

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

