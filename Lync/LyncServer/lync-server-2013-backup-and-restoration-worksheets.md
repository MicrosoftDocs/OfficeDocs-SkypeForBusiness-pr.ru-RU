---
title: 'Lync Server 2013: листы резервного копирования и восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Таблицы резервного копирования и восстановления для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-18_

План резервного копирования и восстановления в Организации должен содержать сведения о том, как и когда выполняется резервное копирование данных и параметров. Вы можете использовать приведенные здесь листы, чтобы задокументировать эти сведения для конкретных развертываний, а также требования к резервному копированию и восстановлению в вашей организации.

Используйте следующие листы для записи сведений, необходимых для резервного копирования и восстановления базы данных, хранилища файлов и сведений о параметрах для пула Lync Server или сервера Standard Edition. Сохраните одну или несколько копий этих листов в безопасном расположении, чтобы они были доступны для восстановления Lync Server.

<div>


> [!NOTE]  
> На листах в этом разделе рассматриваются только те сведения, которые необходимы для восстановления данных и параметров баз данных и серверов Lync Server. Если вам необходимо задокументировать другие сведения о восстановлении, например сведения для переустановки операционных систем и другого программного обеспечения, воспользуйтесь планами развертывания и резервным копированием Организации, чтобы устранить эти требования.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Таблица резервного копирования и восстановления базы данных

Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления баз данных Lync Server.

### <a name="database-information-for-backup-and-restoration"></a>Сведения о базе данных для резервного копирования и восстановления

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>Имя сервера (полное доменное имя)</th>
<th>Расписание резервного копирования</th>
<th>Средство резервного копирования баз данных</th>
<th>Резервный набор данных</th>
<th>Назначение резервного копирования</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>База данных RTC на внутреннем сервере для данных пользователя</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Командлет <strong>Export — CsUserData</strong></p></td>
<td><p>Расширением</p>
<p>Срока действия</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>База данных LcsLog (имя по умолчанию) на архивном сервере баз данных</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Средство управления SQL Server</p></td>
<td><p>Расширением</p>
<p>Срока действия</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>База данных LcsCdr на сервере мониторинга базы данных для записей сведений о вызовах (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Средство управления SQL Server</p></td>
<td><p>Расширением</p>
<p>Срока действия</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>База данных QoEMetrics на сервере мониторинга для данных качества взаимодействия (QoE)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Средство управления SQL Server</p></td>
<td><p>Расширением</p>
<p>Срока действия</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>База данных сохраняемого чата</p></td>
<td></td>
<td></td>
<td><p>Средство управления SQL Server или командлет <strong>Export — CsPersistentChatData</strong></p></td>
<td><p>Расширением</p>
<p>Срока действия</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Резервное копирование и восстановление для следующих баз данных не требуются:

  - Журнал RTCDyn. Временные данные пользователя в этой базе данных не являются обязательными для восстановления службы.

  - Rtcab. База данных адресной книги автоматически воссоздается в глобальном списке адресов (GAL) в доменных службах Active Directory.

  - Ргсдин. Временные данные службы группы ответа в этой базе данных не являются обязательными для восстановления службы.

  - Кпсдин. Динамическая информация для приложения парковки вызовов не требуется для восстановления службы.

  - MgcComp. База данных соответствия для сохраняемого чата не требуется для восстановления службы.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Таблица резервного копирования и восстановления хранилища файлов

Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления хранилищ файлов. Хранилища файлов содержат данные, такие как метаданные контента собраний, журналы соответствия требованиям к собранию, журналы обновлений для обновлений устройств и звуковые файлы для группы ответа, приостановки вызовов и приложений оповещений.

### <a name="file-store-information-for-backup-and-restoration"></a>Сведения о хранении файлов для резервного копирования и восстановления

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Контентная</th>
<th>Имя сервера (полное доменное имя)</th>
<th>Расписание резервного копирования</th>
<th>Средство резервного копирования файловой системы</th>
<th>Резервное копирование общего файлового ресурса *</th>
<th>Назначение резервного копирования</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Хранилище файлов Lync Server</p></td>
<td></td>
<td></td>
<td><p>Стандартный инструмент резервного копирования, например, Robocopy</p></td>
<td><p>На файловом сервере для Enterprise Edition. В стандартном выпуске по умолчанию для развертывания Standard Edition. Как правило, по одному на сайт.</p></td>
<td></td>
<td><p>Невозможно создать резервную копию файлов с именем <strong>Meeting. Active</strong> . Эти файлы используются и заблокированы, пока выполняется собрание.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Таблица резервного копирования и восстановления параметров

Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления параметров.

### <a name="settings-information-for-backup-and-restoration"></a>Сведения о параметрах для резервного копирования и восстановления

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>Имя сервера (полное доменное имя)</th>
<th>Расписание резервного копирования</th>
<th>Средство резервного копирования</th>
<th>Имя файла конфигурации (XML)</th>
<th>Расположение резервной копии</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>База данных XDS в центральном хранилище управления для конфигурации топологии (Глобальная)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Командлет <strong>Export — CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>База данных LIS в центральном хранилище управления для сведений о расположении E9-1-1 (Глобальная)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Командлет <strong>Export — CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>База данных RgsConfig на внутреннем сервере для настройки группы ответа (пул)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Командлет <strong>Export — CsRgsConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

