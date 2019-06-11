---
title: 'Lync Server 2013: Управление доступом на основе ролей (RBAC)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75287cd418d22418f8de2c1a1b018eab8cca4e49
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="eb725-102">Управление доступом на основе ролей (RBAC) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb725-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb725-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="eb725-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="eb725-104">Microsoft Lync Server 2013 включает в себя группы управления доступом на основе ролей (RBAC), позволяющие делегировать задачи администрирования, обеспечивая высокий стандарт безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb725-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="eb725-105">Эти группы создаются в процессе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="eb725-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="eb725-106">Подробнее о подготовке леса можно узнать в статьях [доменных служб Active Directory для Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb725-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="eb725-107">Подробные сведения о конкретных группах, созданных с помощью подготовки леса, приведены в разделе [изменения, внесенные в процессе подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="eb725-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eb725-108">С помощью RBAC права администратора предоставлены путем назначения пользователей предварительно определенным административным ролям, включая 11 предопределенных ролей, которые охватывают многие общие задачи администрирования.</span><span class="sxs-lookup"><span data-stu-id="eb725-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="eb725-109">Каждая роль связана с определенным списком командлетов командной консоли для Lync Server, для которых разрешено выполнение пользователей этой роли.</span><span class="sxs-lookup"><span data-stu-id="eb725-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="eb725-110">Можно использовать RBAC для выполнения принципа "наименьших привилегий", в котором пользователям предоставляются только возможности администрирования, необходимые для работы.</span><span class="sxs-lookup"><span data-stu-id="eb725-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="eb725-111">Подробности можно найти [в разделе Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="eb725-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

