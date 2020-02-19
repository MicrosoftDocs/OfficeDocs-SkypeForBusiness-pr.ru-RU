---
title: 'Lync Server 2013: требования к резервному копированию и восстановлению: средства и разрешения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b273674d1f2ad20a0379c65e35e85ae0300df3dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Требования к резервному копированию и восстановлению в Lync Server 2013: инструменты и разрешения

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-17_

В этом разделе описываются средства, которые можно использовать для резервного копирования и восстановления Lync Server 2013, необходимые разрешения, а также возможность удаленного или локального запуска команд. В частности, этот раздел посвящен средствам, предоставляемым Lync Server для резервного копирования и восстановления.

<div>

## <a name="backups"></a>Резервные копии

Для резервного копирования Lync Server используйте средства, указанные в приведенной ниже таблице. Все команды, необходимые для резервного копирования Lync Server, можно создавать с помощью скриптов и могут быть запущены удаленно.

### <a name="tools-for-backing-up-lync-server"></a>Средства резервного копирования Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Чтобы выполнить резервное копирование, выполните следующие действия.</th>
<th>Используйте это средство или командлет:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Данные конфигурации топологии (XDS. mdf)</p></td>
<td><p>Export — CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Data Information Service (E9-1-1) Data (LIS. mdf)</p></td>
<td><p>Export — CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Данные конфигурации группы ответа (RgsConfig. mdf)</p></td>
<td><p>Export — CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Постоянные данные пользователя (база данных Rtcxds. mdf)</p>
<p>Идентификаторы конференций</p></td>
<td><p>Export — CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Архивная база данных (LcsLog. mdf)</p></li>
<li><p>Отслеживание базы данных записи сведений о вызовах (LcsCDR. mdf)</p></li>
<li><p>Мониторинг базы данных QoE (QoEMetrics. mdf)</p></li>
</ul></td>
<td><p>Средство для баз данных SQL Server, например SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>База данных сохраняемого чата (MGC. mdf)</p></td>
<td><p>Процедуры резервного копирования SQL Server или Export — CsPersistentChatData. Export — CsPersistentChatData экспортирует данные сохраняемого чата в виде файла.</p></td>
</tr>
<tr class="odd">
<td><p>Все хранилища файлов: хранилище файлов Lync Server, архивирование хранилища файлов</p>
<div>

> [!NOTE]  
> Невозможно создать резервную копию файлов с именем <STRONG>Meeting. Active</STRONG> . Эти файлы используются и заблокированы во время собрания.


</div></td>
<td><p>Стандартное средство управления файловой системой, например Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Оно

Для восстановления Lync Server воспользуйтесь средствами, приведенными в следующей таблице. Все команды, необходимые для восстановления Lync Server, могут быть внесены в скрипт. Некоторые из них можно запускать удаленно, но другие необходимо запускать локально, как указано в следующей таблице.

### <a name="tools-for-restoring-lync-server"></a>Средства для восстановления Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Для этого сделайте следующее:</th>
<th>Используйте это средство или командлет:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Создание нового или чистого компьютера</p></td>
<td><ul>
<li><p>Программное обеспечение для установки операционной системы Windows</p></li>
<li><p>Программное обеспечение для установки SQL Server</p></li>
<li><p>Оснастка "сертификаты" консоли управления (MMC), если вы восстанавливаете сертификаты с закрытым ключом</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Восстановление данных из хранилища файлов</p></td>
<td><p>Стандартное средство управления файловой системой, например Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Повторно создайте пустые базы данных и установите разрешения для следующих параметров:</p>
<ul>
<li><p>Центральное хранилище управления</p></li>
<li><p>Сервер переднего план</p></li>
<li><p>база данных мониторинга;</p></li>
<li><p>база данных архивации;</p></li>
</ul></td>
<td><p>Install — CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Восстановление указателя доменных служб Active Directory в центральном хранилище управления</p>
<div>

> [!NOTE]  
> Если вы потеряете точку подключения службы в любое время, вы можете повторно запустить этот командлет.


</div></td>
<td><p>Set — CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Импорт топологии, политик и параметров конфигурации в центральное хранилище управления (XDS. mdf)</p></td>
<td><p>Import — CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Публикация и включение топологии</p></td>
<td><p>Построитель топологий</p>
<p>-или-</p>
<p>Publish — CsTopology и Enable — CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Включение последней опубликованной топологии</p></td>
<td><p>Enable — CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Переустановка компонентов Lync Server</p></td>
<td><p>Установка Lync Server</p>
<div>

> [!NOTE]  
> Размещается в папке установки Lync Server или на носителе по адресу \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Восстановление сведений о расположении (E9-1-1) Data (LIS. mdf)</p></td>
<td><p>Import — CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Восстановление постоянных пользовательских данных (Rtcxds. mdf)</p></td>
<td><p>Import — CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Восстановление данных конфигурации группы ответа (RgsConfig. mdf)</p></td>
<td><p>Import — CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Если конфигурация восстанавливается в новом развернутом пуле, в базе данных которого нет данных группы ответа, следует использовать параметр – Овервритеовнер. Используйте этот параметр, даже если восстанавливаемые данные находятся в пуле с таким же полным доменным именем (FQDN). В противном случае импорт завершится неудачно из-за объектов Contact в группы ответа, уже существующие в Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Восстановите следующие базы данных:</p>
<ul>
<li><p>Архивная база данных (LcsLog. mdf)</p></li>
<li><p>Мониторинг баз данных: база данных записей сведений о вызовах (LcsCDR. mdf) и база данных QoE (QoEMetrics. mdf)</p></li>
</ul></td>
<td><p>Средства управления базами данных SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>База данных сохраняемого чата (МГС. mdf)</p></td>
<td><p>Процедуры восстановления SQL Server или импорт — CsPersistentChatData. Вы можете использовать import – CsPersistentChatData с файлом, созданным с помощью Export – CsPersistentChatData, и данные будут импортированы в базу данных сохраняемого чата.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Требуемые разрешения

Для выполнения всех команд, описанных в этом разделе, пользователи должны быть членами группы **RTCUniversalServerAdmins** . Большинство команд резервного копирования и восстановления не поддерживают управление доступом на основе ролей (RBAC). Два исключения — командлеты сохраняемого чата Export-CsPersistentChatData и Import-CsPersistentChatData, которые должны выполняться пользователем, который является членом группы CsPersistentChatAdministrator. Для запуска мастера развертывания Lync Server пользователь также должен быть членом локальной группы Администраторы.

</div>

</div>

<span> </span>

</div>

</div>

</div>

