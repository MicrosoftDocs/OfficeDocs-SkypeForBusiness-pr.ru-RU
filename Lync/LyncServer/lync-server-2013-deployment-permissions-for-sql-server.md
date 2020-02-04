---
title: 'Lync Server 2013: разрешения на развертывание для SQL Server'
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
ms.openlocfilehash: 393e293dfc7e20fa1e990d9f87c17c6e72776be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Разрешения на развертывание для SQL Server в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

При установке и развертывании Lync Server 2013 Microsoft SQL Server 2012 имеет особые требования. Поскольку Windows и SQL Server определяют их безопасность по-разному, вход в качестве администратора в домене Active Directory не приводит к косвенному предоставлению разрешений для SQL Server. Кроме того, вы должны быть участником сущности sysadmin на сервере SQL Server, который вы настраиваете.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Разрешения, необходимые для установки базы данных и Lync Server

Ниже описаны три разрешения и сопоставления членства в группах для установки файлов Lync Server 2013 и баз данных SQL Server. Выберите сценарий, который наилучшим образом соответствует требованиям вашей организации.

### <a name="permissions-and-group-membership-associations"></a>Разрешения и сопоставления членства в группах

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Роль SQL Server или Lync Server 2013</th>
<th>Role (роль) — типичные разрешения SQL Server и членство в группах</th>
<th>Роль — типичные разрешения и членство в группах для Lync Server 2013</th>
<th>Результат разрешений</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Администратор Lync Server 2013</p></td>
<td><p>Необходимо предоставить доступ к группе безопасности sysadmin SQL Server и входить в группу локальных администраторов SQL Server.</p></td>
<td><p>Должен быть членом группы Рткуниверсалсерверадминс</p></td>
<td><p>У администратора Lync Server 2013 есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Администратор SQL Server</p></td>
<td><p>Участник группы системного администратора SQL Server (или аналогичный) и участник группы локальных администраторов SQL Server</p></td>
<td><p>Должен быть членом группы Рткуниверсалсерверреадонли</p></td>
<td><p>У администратора SQL Server есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Оба администратора совместно применяют обязанности по установке</p></td>
<td><p>Администратор SQL Server входит в группу "Администраторы" (или аналогичную) и входит в группу локальных администраторов SQL Server.</p></td>
<td><p>Администратор Lync Server 2013 входит в состав Рткуниверсалсерверадминс</p></td>
<td><p>Администратор Lync Server 2013 может установить Lync Server 2013, но не может установить базу данных. Администратор SQL Server использует командную консоль Lync Server Management Shell и командлеты Windows PowerShell, предоставленные администратором Lync Server 2013 для установки баз данных. Управляющая оболочка Lync Server 2013, используемая администратором SQL Server, установлена на сервере переднего плана. Это избавляет от необходимости устанавливать средства администрирования Lync Server 2013 на сервере SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

