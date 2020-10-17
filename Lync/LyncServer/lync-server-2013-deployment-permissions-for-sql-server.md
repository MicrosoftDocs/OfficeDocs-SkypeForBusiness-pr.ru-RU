---
title: 'Lync Server 2013: разрешения развертывания для SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab8628859d5bcb4306cb745509d572a77a21851e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522656"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Разрешения развертывания для SQL Server в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

При установке и развертывании Lync Server 2013 в Microsoft SQL Server 2012 предъявляются определенные требования. Так как Windows и SQL Server определяют свои системы безопасности по-разному, вход в систему в качестве администратора в домене Active Directory не предоставляет неявным образом разрешения для SQL Server. Кроме того, необходимо быть членом сущности sysadmin на сервере SQL Server, который вы настраиваете.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Разрешения, необходимые для установки базы данных и Lync Server

Следующие параметры заключают три разрешения и сопоставления членства в группах для установки файлов Lync Server 2013 и баз данных SQL Server. Выберите сценарий, который наилучшим образом соответствует требованиям вашей организации.

### <a name="permissions-and-group-membership-associations"></a>Сопоставления разрешений и членства в группах

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Роль сервера SQL Server или Lync Server 2013</th>
<th>Role-Typical разрешений SQL Server и членства в группах</th>
<th>Роль — типичные разрешения и членство в группах для Lync Server 2013</th>
<th>Результат разрешений</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013, администратор</p></td>
<td><p>Должно быть выдано членство в группе безопасности sysadmin SQL Server и членом группы локальных администраторов SQL Server.</p></td>
<td><p>Должен быть членом группы RTCUniversalServerAdmins</p></td>
<td><p>Lync Server 2013 имеет соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Администратор SQL Server</p></td>
<td><p>Участник группы администраторов SQL Server (или аналогичный) и член группы локальных администраторов SQL Server</p></td>
<td><p>Должен быть членом группы Рткуниверсалсерверреадонли</p></td>
<td><p>У администратора SQL Server есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Оба администратора совместно отменяют обязанности по установке</p></td>
<td><p>Администратор SQL Server является участником группы администраторов (или аналогичной группы) и членом группы локальных администраторов SQL Server.</p></td>
<td><p>Lync Server 2013 администратор является участником RTCUniversalServerAdmins</p></td>
<td><p>Администратор Lync Server 2013 может устанавливать Lync Server 2013, но не может устанавливать базы данных. Для установки баз данных администратор SQL Server использует командную консоль Lync Server и командлеты Windows PowerShell, предоставляемые администратором Lync Server 2013. Управляющая Командная консоль Lync Server 2013, используемая администратором SQL Server, установлена на сервере переднего плана. Это избавляет от необходимости устанавливать средства администрирования Lync Server 2013 на сервере SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

