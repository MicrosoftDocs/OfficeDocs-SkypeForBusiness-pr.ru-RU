---
title: 'Lync Server 2013: учетные записи пользователей, включенные для Lync Server'
description: 'Lync Server 2013: учетные записи пользователей, включенные для Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569875"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="14678-103">Учетные записи пользователей, включенные для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-103">User accounts enabled for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14678-104">_**Последнее изменение темы:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="14678-104">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="14678-105">В подразделах этого раздела приводятся пошаговые процедуры для настройки пользовательских параметров, которые можно выполнить с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14678-105">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14678-106">Вы не можете использовать панель управления Lync Server для управления пользователями, которые являются участниками группы администраторов домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14678-106">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="14678-107">Для пользователей домена Администраторы могут использовать панель управления Lync Server только для выполнения операций поиска, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="14678-107">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="14678-108">Для выполнения операций записи для пользователей "Администраторы домена" (например, включить или отключить для панели управления Lync Server, изменить параметры пула или политики, параметры телефонии, SIP-адрес), необходимо использовать командлеты Windows PowerShell, войдя в систему как пользователь "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="14678-108">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="14678-109">Для получения дополнительных сведений об использовании командлетов Windows PowerShell для управления пользователями обратитесь к статье <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="14678-109">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="14678-110">При выполнении любой административной задачи Lync Server 2013, которая включает поиск пользователя или фильтрацию результатов поиска пользователей, существуют некоторые свойства пользователя, которые существуют в качестве атрибутов в доменных службах Active Directory, но не реплицируются в глобальный каталог до развертывания Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="14678-110">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="14678-111">Microsoft Exchange, а не Lync Server, помечает следующие атрибуты репликации в глобальном каталоге при его установке:</span><span class="sxs-lookup"><span data-stu-id="14678-111">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14678-112">Сведения о пользователе</span><span class="sxs-lookup"><span data-stu-id="14678-112">User Information</span></span></th>
<th><span data-ttu-id="14678-113">Адрес и телефон</span><span class="sxs-lookup"><span data-stu-id="14678-113">Address and Phone</span></span></th>
<th><span data-ttu-id="14678-114">Организация</span><span class="sxs-lookup"><span data-stu-id="14678-114">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14678-115">Initials</span><span class="sxs-lookup"><span data-stu-id="14678-115">Initials</span></span></p></td>
<td><p><span data-ttu-id="14678-116">Адрес (улица, дом)</span><span class="sxs-lookup"><span data-stu-id="14678-116">Street address</span></span></p>
<p><span data-ttu-id="14678-117">Страна или регион</span><span class="sxs-lookup"><span data-stu-id="14678-117">Country/region</span></span></p>
<p><span data-ttu-id="14678-118">Пейджер</span><span class="sxs-lookup"><span data-stu-id="14678-118">Pager</span></span></p>
<p><span data-ttu-id="14678-119">Fax</span><span class="sxs-lookup"><span data-stu-id="14678-119">Fax</span></span></p>
<p><span data-ttu-id="14678-120">Mobile</span><span class="sxs-lookup"><span data-stu-id="14678-120">Mobile</span></span></p></td>
<td><p><span data-ttu-id="14678-121">Название</span><span class="sxs-lookup"><span data-stu-id="14678-121">Title</span></span></p>
<p><span data-ttu-id="14678-122">Company</span><span class="sxs-lookup"><span data-stu-id="14678-122">Company</span></span></p>
<p><span data-ttu-id="14678-123">Отдел</span><span class="sxs-lookup"><span data-stu-id="14678-123">Department</span></span></p>
<p><span data-ttu-id="14678-124">Кабинет</span><span class="sxs-lookup"><span data-stu-id="14678-124">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="14678-125">Содержание</span><span class="sxs-lookup"><span data-stu-id="14678-125">In This Section</span></span>

  - [<span data-ttu-id="14678-126">Просмотр сведений об учетных записях пользователей, включенных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-126">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="14678-127">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-127">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="14678-128">Управление корпоративной голосовой связью для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-128">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="14678-129">Изменение свойств учетной записи пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-129">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="14678-130">Управление политикой внешнего доступа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-130">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="14678-131">Назначение политик для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-131">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14678-132">См. также</span><span class="sxs-lookup"><span data-stu-id="14678-132">See Also</span></span>


[<span data-ttu-id="14678-133">Командлеты управления пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-133">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="14678-134">Управление пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14678-134">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

