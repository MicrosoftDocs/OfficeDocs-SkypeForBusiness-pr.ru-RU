---
title: 'Lync Server 2013: учетные записи пользователей, включенные для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="10341-102">Учетные записи пользователей, включенные для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10341-103">_**Тема последнего изменения:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="10341-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="10341-104">В этой статье приведены пошаговые инструкции по настройке параметров пользователей, которые можно выполнить с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10341-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="10341-105">Вы не можете использовать панель управления Lync Server для управления пользователями, которые являются членами группы администраторов домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10341-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="10341-106">Для пользователей, которые являются администраторами домена, можно использовать панель управления Lync Server только для выполнения операций поиска, предназначенных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="10341-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="10341-107">Для выполнения операций записи на пользователей администраторов домена (например, включить или отключить для панели управления Lync Server, изменить параметры пула или политики, настройки телефонной связи, адрес SIP) необходимо использовать командлеты Windows PowerShell, войдя в систему как пользователь с учетной записью администратора домена.</span><span class="sxs-lookup"><span data-stu-id="10341-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="10341-108">Подробнее об использовании командлетов Windows PowerShell для управления пользователями можно узнать в разделе <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="10341-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="10341-109">При выполнении любой административной задачи Lync Server 2013, которая включает в себя поиск пользователя или фильтрацию результатов поиска пользователей, в доменных службах Active Directory используются некоторые свойства пользователя, которые не реплицируются в глобальный каталог. пока не будет выполнено развертывание сервера Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="10341-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="10341-110">Microsoft Exchange, а не Lync Server, помечает следующие атрибуты репликации в глобальный каталог после установки.</span><span class="sxs-lookup"><span data-stu-id="10341-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10341-111">Сведения о пользователе</span><span class="sxs-lookup"><span data-stu-id="10341-111">User Information</span></span></th>
<th><span data-ttu-id="10341-112">Адрес и номер телефона</span><span class="sxs-lookup"><span data-stu-id="10341-112">Address and Phone</span></span></th>
<th><span data-ttu-id="10341-113">Организация</span><span class="sxs-lookup"><span data-stu-id="10341-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10341-114">Инициалы</span><span class="sxs-lookup"><span data-stu-id="10341-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="10341-115">Почтовый адрес</span><span class="sxs-lookup"><span data-stu-id="10341-115">Street address</span></span></p>
<p><span data-ttu-id="10341-116">Страна или регион</span><span class="sxs-lookup"><span data-stu-id="10341-116">Country/region</span></span></p>
<p><span data-ttu-id="10341-117">Оператора</span><span class="sxs-lookup"><span data-stu-id="10341-117">Pager</span></span></p>
<p><span data-ttu-id="10341-118">Сообщений</span><span class="sxs-lookup"><span data-stu-id="10341-118">Fax</span></span></p>
<p><span data-ttu-id="10341-119">Мобильный</span><span class="sxs-lookup"><span data-stu-id="10341-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="10341-120">Название</span><span class="sxs-lookup"><span data-stu-id="10341-120">Title</span></span></p>
<p><span data-ttu-id="10341-121">Между</span><span class="sxs-lookup"><span data-stu-id="10341-121">Company</span></span></p>
<p><span data-ttu-id="10341-122">Отдел</span><span class="sxs-lookup"><span data-stu-id="10341-122">Department</span></span></p>
<p><span data-ttu-id="10341-123">Office</span><span class="sxs-lookup"><span data-stu-id="10341-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="10341-124">Содержание</span><span class="sxs-lookup"><span data-stu-id="10341-124">In This Section</span></span>

  - [<span data-ttu-id="10341-125">Просмотр сведений об учетных записях пользователей, включенных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="10341-126">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="10341-127">Управление корпоративной голосовой связью для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="10341-128">Изменение свойств учетной записи пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="10341-129">Управление политикой внешнего доступа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="10341-130">Назначение политик для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10341-131">См. также</span><span class="sxs-lookup"><span data-stu-id="10341-131">See Also</span></span>


[<span data-ttu-id="10341-132">Командлеты управления пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="10341-133">Управление пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10341-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

