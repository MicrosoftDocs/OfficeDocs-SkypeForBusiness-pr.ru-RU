---
title: 'Lync Server 2013: Управление доступом на основе ролей (RBAC)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df625272214867148190e479fc198a520219fa9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511306"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="4c462-102">Управление доступом на основе ролей (RBAC) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c462-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c462-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="4c462-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="4c462-104">Microsoft Lync Server 2013 содержит группы управления доступом Role-Based (RBAC), позволяющие делегировать административные задачи, сохраняя при этом высокие стандарты безопасности.</span><span class="sxs-lookup"><span data-stu-id="4c462-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="4c462-105">Эти группы создаются во время подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="4c462-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="4c462-106">Подробнее о подготовке леса можно узнать в статье [Domain Services Active Directory для Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c462-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="4c462-107">Сведения об отдельных группах, созданных при подготовке леса, приведены в статье [изменения, внесенные в ходе подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4c462-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4c462-108">С помощью RBAC административные привилегии назначаются путем назначения пользователям предварительно определенных административных ролей, включая 11 предопределенных ролей, охватывающих многие общие задачи администрирования.</span><span class="sxs-lookup"><span data-stu-id="4c462-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="4c462-109">Каждая роль связана с определенным списком командлетов командной консоли Lync Server, которые разрешено запускать пользователям этой роли.</span><span class="sxs-lookup"><span data-stu-id="4c462-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="4c462-110">С помощью RBAC можно придерживаться принципа "минимальных прав", в котором пользователям предоставляются только административные возможности, необходимые для работы этих заданий.</span><span class="sxs-lookup"><span data-stu-id="4c462-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="4c462-111">Дополнительные сведения приведены в статье [Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4c462-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

