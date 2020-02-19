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
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="da04a-102">Разрешения развертывания для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da04a-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da04a-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="da04a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="da04a-104">При установке и развертывании Lync Server 2013 в Microsoft SQL Server 2012 предъявляются определенные требования.</span><span class="sxs-lookup"><span data-stu-id="da04a-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="da04a-105">Так как Windows и SQL Server определяют свои системы безопасности по-разному, вход в систему в качестве администратора в домене Active Directory не предоставляет неявным образом разрешения для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="da04a-106">Кроме того, необходимо быть членом сущности sysadmin на сервере SQL Server, который вы настраиваете.</span><span class="sxs-lookup"><span data-stu-id="da04a-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="da04a-107">Разрешения, необходимые для установки базы данных и Lync Server</span><span class="sxs-lookup"><span data-stu-id="da04a-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="da04a-108">Следующие параметры заключают три разрешения и сопоставления членства в группах для установки файлов Lync Server 2013 и баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="da04a-109">Выберите сценарий, который наилучшим образом соответствует требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="da04a-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="da04a-110">Сопоставления разрешений и членства в группах</span><span class="sxs-lookup"><span data-stu-id="da04a-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da04a-111">Роль сервера SQL Server или Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da04a-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="da04a-112">Role — типичные разрешения SQL Server и членство в группах</span><span class="sxs-lookup"><span data-stu-id="da04a-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="da04a-113">Роль — типичные разрешения и членство в группах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da04a-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="da04a-114">Результат разрешений</span><span class="sxs-lookup"><span data-stu-id="da04a-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da04a-115">Lync Server 2013, администратор</span><span class="sxs-lookup"><span data-stu-id="da04a-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="da04a-116">Должно быть выдано членство в группе безопасности sysadmin SQL Server и членом группы локальных администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="da04a-117">Должен быть членом группы RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="da04a-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="da04a-118">Lync Server 2013 имеет соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da04a-119">Администратор SQL Server</span><span class="sxs-lookup"><span data-stu-id="da04a-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="da04a-120">Участник группы администраторов SQL Server (или аналогичный) и член группы локальных администраторов SQL Server</span><span class="sxs-lookup"><span data-stu-id="da04a-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="da04a-121">Должен быть членом группы Рткуниверсалсерверреадонли</span><span class="sxs-lookup"><span data-stu-id="da04a-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="da04a-122">У администратора SQL Server есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da04a-123">Оба администратора совместно отменяют обязанности по установке</span><span class="sxs-lookup"><span data-stu-id="da04a-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="da04a-124">Администратор SQL Server является участником группы администраторов (или аналогичной группы) и членом группы локальных администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="da04a-125">Lync Server 2013 администратор является участником RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="da04a-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="da04a-126">Администратор Lync Server 2013 может устанавливать Lync Server 2013, но не может устанавливать базы данных.</span><span class="sxs-lookup"><span data-stu-id="da04a-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="da04a-127">Для установки баз данных администратор SQL Server использует командную консоль Lync Server и командлеты Windows PowerShell, предоставляемые администратором Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da04a-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="da04a-128">Управляющая Командная консоль Lync Server 2013, используемая администратором SQL Server, установлена на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="da04a-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="da04a-129">Это избавляет от необходимости устанавливать средства администрирования Lync Server 2013 на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da04a-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

