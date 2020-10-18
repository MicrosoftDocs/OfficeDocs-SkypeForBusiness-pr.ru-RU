---
title: 'Lync Server 2013: разрешения развертывания для SQL Server'
description: 'Lync Server 2013: разрешения развертывания для SQL Server.'
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
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575725"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="66e6a-103">Разрешения развертывания для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e6a-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e6a-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="66e6a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="66e6a-105">При установке и развертывании Lync Server 2013 в Microsoft SQL Server 2012 предъявляются определенные требования.</span><span class="sxs-lookup"><span data-stu-id="66e6a-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="66e6a-106">Так как Windows и SQL Server определяют свои системы безопасности по-разному, вход в систему в качестве администратора в домене Active Directory не предоставляет неявным образом разрешения для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="66e6a-107">Кроме того, необходимо быть членом сущности sysadmin на сервере SQL Server, который вы настраиваете.</span><span class="sxs-lookup"><span data-stu-id="66e6a-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="66e6a-108">Разрешения, необходимые для установки базы данных и Lync Server</span><span class="sxs-lookup"><span data-stu-id="66e6a-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="66e6a-109">Следующие параметры заключают три разрешения и сопоставления членства в группах для установки файлов Lync Server 2013 и баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="66e6a-110">Выберите сценарий, который наилучшим образом соответствует требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="66e6a-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="66e6a-111">Сопоставления разрешений и членства в группах</span><span class="sxs-lookup"><span data-stu-id="66e6a-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66e6a-112">Роль сервера SQL Server или Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e6a-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="66e6a-113">Role-Typical разрешений SQL Server и членства в группах</span><span class="sxs-lookup"><span data-stu-id="66e6a-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="66e6a-114">Роль — типичные разрешения и членство в группах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e6a-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="66e6a-115">Результат разрешений</span><span class="sxs-lookup"><span data-stu-id="66e6a-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66e6a-116">Lync Server 2013, администратор</span><span class="sxs-lookup"><span data-stu-id="66e6a-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="66e6a-117">Должно быть выдано членство в группе безопасности sysadmin SQL Server и членом группы локальных администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="66e6a-118">Должен быть членом группы RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66e6a-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="66e6a-119">Lync Server 2013 имеет соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e6a-120">Администратор SQL Server</span><span class="sxs-lookup"><span data-stu-id="66e6a-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="66e6a-121">Участник группы администраторов SQL Server (или аналогичный) и член группы локальных администраторов SQL Server</span><span class="sxs-lookup"><span data-stu-id="66e6a-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="66e6a-122">Должен быть членом группы Рткуниверсалсерверреадонли</span><span class="sxs-lookup"><span data-stu-id="66e6a-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="66e6a-123">У администратора SQL Server есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e6a-124">Оба администратора совместно отменяют обязанности по установке</span><span class="sxs-lookup"><span data-stu-id="66e6a-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="66e6a-125">Администратор SQL Server является участником группы администраторов (или аналогичной группы) и членом группы локальных администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="66e6a-126">Lync Server 2013 администратор является участником RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66e6a-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="66e6a-127">Администратор Lync Server 2013 может устанавливать Lync Server 2013, но не может устанавливать базы данных.</span><span class="sxs-lookup"><span data-stu-id="66e6a-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="66e6a-128">Для установки баз данных администратор SQL Server использует командную консоль Lync Server и командлеты Windows PowerShell, предоставляемые администратором Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66e6a-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="66e6a-129">Управляющая Командная консоль Lync Server 2013, используемая администратором SQL Server, установлена на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="66e6a-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="66e6a-130">Это избавляет от необходимости устанавливать средства администрирования Lync Server 2013 на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66e6a-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

