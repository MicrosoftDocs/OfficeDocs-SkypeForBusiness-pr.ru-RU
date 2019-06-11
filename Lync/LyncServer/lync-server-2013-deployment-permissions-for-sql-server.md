---
title: 'Lync Server 2013: разрешения на развертывание для SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="368e9-102">Разрешения на развертывание для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368e9-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="368e9-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="368e9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="368e9-104">При установке и развертывании Lync Server 2013 Microsoft SQL Server 2012 имеет особые требования.</span><span class="sxs-lookup"><span data-stu-id="368e9-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="368e9-105">Поскольку Windows и SQL Server определяют их безопасность по-разному, вход в качестве администратора в домене Active Directory не приводит к косвенному предоставлению разрешений для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="368e9-106">Кроме того, вы должны быть участником сущности sysadmin на сервере SQL Server, который вы настраиваете.</span><span class="sxs-lookup"><span data-stu-id="368e9-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="368e9-107">Разрешения, необходимые для установки базы данных и Lync Server</span><span class="sxs-lookup"><span data-stu-id="368e9-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="368e9-108">Ниже описаны три разрешения и сопоставления членства в группах для установки файлов Lync Server 2013 и баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="368e9-109">Выберите сценарий, который наилучшим образом соответствует требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="368e9-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="368e9-110">Разрешения и сопоставления членства в группах</span><span class="sxs-lookup"><span data-stu-id="368e9-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="368e9-111">Роль SQL Server или Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368e9-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="368e9-112">Role (роль) — типичные разрешения SQL Server и членство в группах</span><span class="sxs-lookup"><span data-stu-id="368e9-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="368e9-113">Роль — типичные разрешения и членство в группах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368e9-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="368e9-114">Результат разрешений</span><span class="sxs-lookup"><span data-stu-id="368e9-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="368e9-115">Администратор Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368e9-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="368e9-116">Необходимо предоставить доступ к группе безопасности sysadmin SQL Server и входить в группу локальных администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="368e9-117">Должен быть членом группы Рткуниверсалсерверадминс</span><span class="sxs-lookup"><span data-stu-id="368e9-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="368e9-118">У администратора Lync Server 2013 есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="368e9-119">Администратор SQL Server</span><span class="sxs-lookup"><span data-stu-id="368e9-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="368e9-120">Участник группы системного администратора SQL Server (или аналогичный) и участник группы локальных администраторов SQL Server</span><span class="sxs-lookup"><span data-stu-id="368e9-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="368e9-121">Должен быть членом группы Рткуниверсалсерверреадонли</span><span class="sxs-lookup"><span data-stu-id="368e9-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="368e9-122">У администратора SQL Server есть соответствующие разрешения на установку баз данных Lync Server 2013 и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="368e9-123">Оба администратора совместно применяют обязанности по установке</span><span class="sxs-lookup"><span data-stu-id="368e9-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="368e9-124">Администратор SQL Server входит в группу "Администраторы" (или аналогичную) и входит в группу локальных администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="368e9-125">Администратор Lync Server 2013 входит в состав Рткуниверсалсерверадминс</span><span class="sxs-lookup"><span data-stu-id="368e9-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="368e9-126">Администратор Lync Server 2013 может установить Lync Server 2013, но не может установить базу данных.</span><span class="sxs-lookup"><span data-stu-id="368e9-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="368e9-127">Администратор SQL Server использует командную консоль Lync Server Management Shell и командлеты Windows PowerShell, предоставленные администратором Lync Server 2013 для установки баз данных.</span><span class="sxs-lookup"><span data-stu-id="368e9-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="368e9-128">Управляющая оболочка Lync Server 2013, используемая администратором SQL Server, установлена на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="368e9-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="368e9-129">Это избавляет от необходимости устанавливать средства администрирования Lync Server 2013 на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="368e9-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

